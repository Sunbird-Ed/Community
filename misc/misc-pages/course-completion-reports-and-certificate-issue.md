# Course completion, reports and certificate issue

Process Flow for course completion and certificate issuance

* Once a user completes a lesson the content state update (in lms service) API is called to mark the lesson as complete
* Each lesson completed by the user has a row in the sunbird\_courses.user\_content\_consumption cassandra table. As the user completes the lesson, the status & progress in the row gets updated
* The LMS service generates events in the dev.coursebatch.job.request topic
* Events from this topic are consumed by the activity-aggregate-updater job to mark the course completion. Both lesson progress and course completion events are generated in this topic
* The activity-aggregate-updater job updates the overall course progress in the sunbird\_courses.user\_activity\_agg cassandra table and sends an event to the dev.issue.certificate.request topic for certificate generation
* The course-certificate-generator-v2\_1 Samza job uses events from dev.issue.certificate.request topic to generate & issue the certificate to the user. The certificate issuance is also stored in the sunbird\_courses.user\_activity\_agg cassandra table
  * In Sunbird 4.2 this samza job has been moved to a Flink job

### Reports

All reports need the user cache in redis populated. This is done by the flink-dev/user-cache-updater-v2 job. The cache update can also me manually triggered by the ETLUserCacheIndexer Jenkins job

The progress exhaust report uses data from sunbird\_courses.user\_activity\_agg to generate the report. The progress exhaust also needs the user cache to be populated, otherwise this report may be empty

The user info report will work as long as the cache is populated

For the response exhaust, the assessment-aggregator job needs to be running and stable

Usually the reports are generated using a cronjob. Use the below commands to manually run the jobs. Run it from the DP VM, as analytics user

```bash
/mount/data/analytics/scripts/run-job.sh progress-exhaust
/mount/data/analytics/scripts/run-job.sh response-exhaust
/mount/data/analytics/scripts/run-job.sh userinfo-exhaust
```

### FAQs if certificate is failing

1. The certificate needs to have [issuer.name](http://issuer.name) and issuer.url set
2. The certificate needs to have signatoryList array with 1 child having
