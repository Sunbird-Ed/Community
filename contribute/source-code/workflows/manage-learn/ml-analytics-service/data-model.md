# Data Model

## Druid Data Sources

## sl-project

| Dimensions                      | Datatype | Description                                                                                  |
| ------------------------------- | -------- | -------------------------------------------------------------------------------------------- |
| program\_name                   | String   | Name of the program to which the project is mapped to                                        |
| project\_updated\_date          | Date     | Project last updated date                                                                    |
| project\_evidence               | String   | Link of the attachment uploaded at the in a project                                          |
| tasks\_status                   | String   | Status of the Task attached to project                                                       |
| district\_externalId            | String   | Unique identifier of the District mapped to the user                                         |
| task\_evidence\_count           | Long     | Total attachment count uploaded for Task                                                     |
| board\_name                     | String   | Name of the board mapped to the user                                                         |
| sub\_task\_deleted\_flag        | Boolean  | Indicates True or False which tells whether the sub-task is deleted by the user from the app |
| school\_name                    | String   | Name of the School declared by the User                                                      |
| state\_code                     | Long     | Unique identifier of the State code                                                          |
| private\_program                | String   | boolean value that defines program type                                                      |
| createdBy                       | String   | User keycloak id on the sunbrid platform                                                     |
| channel                         | String   | Root organisation of user                                                                    |
| status\_of\_project             | String   | Status of the Project created or mapped                                                      |
| project\_description            | String   | Summary of the project                                                                       |
| state\_name                     | String   | Name of the State mapped to the user                                                         |
| task\_assigned\_to              | String   | Provides the username or email to which user the task is assigned to                         |
| sub\_task\_date                 | String   | Last sync date of the sub task                                                               |
| district\_name                  | String   | Name of the District mapped to the user                                                      |
| project\_completed\_date        | String   | Date of completion of the project                                                            |
| task\_id                        | String   | Unique identifier of Task attached to the Project                                            |
| task\_remarks                   | String   | Remarks of the task                                                                          |
| organisation\_name              | String   | Organisation Name of the user belongs to                                                     |
| project\_title\_editable        | String   | Edited name of the Project                                                                   |
| project\_duration               | String   | Duration of the project taken to complete                                                    |
| block\_code                     | Long     | Unique identifier of the Block code                                                          |
| school\_externalId              | String   | Unique identifier of the School mapped to the user                                           |
| project\_goal                   | String   | Goal of the Project created or mapped                                                        |
| program\_externalId             | String   | Unique identifier of the program to which the project is mapped to                           |
| project\_deleted\_flag          | String   | Indicates True or False which tells whether the projects is deleted by the user from the app |
| tasks                           | String   | Name of the Task attached to Project                                                         |
| certificate\_id                 | String   | Unique identifier of the Certificate                                                         |
| certificate\_status\_customised | String   | Customised Certificate Status Data as Issued or not                                          |
| block\_externalId               | String   | Unique identifier of the Block                                                               |
| block\_name                     | String   | Name of the Block mapped to the user                                                         |
| task\_evidence\_status          | String   | Indicates true or false of evidence attached or not at the task level                        |
| tasks\_date                     | Date     | Last sync date of the task                                                                   |
| organisation\_id                | String   | Unique Identifier for the organisation                                                       |
| project\_terms\_and\_condition  | String   | boolean value that defines terms and condition                                               |
| district\_code                  | Long     | Unique identifier of the District code                                                       |
| parent\_channel                 | String   | Column with constant value - "SHIKSHALOKAM"                                                  |
| user\_type                      | String   | User Role                                                                                    |
| certificate\_issued\_on         | date     | certificate issued date to user                                                              |
| designation                     | String   | Sub role of the user                                                                         |
| task\_end\_date                 | String   | End date of Task attached to Project                                                         |
| project\_remarks                | String   | Remarks of the projects                                                                      |
| certificate\_status             | String   | Status of the project ceritificate                                                           |
| school\_code                    | Long     | Unique identifier of the school code                                                         |
| state\_externalId               | String   | Unique identifier of the State                                                               |
| project\_title                  | String   | Name of the Project                                                                          |
| sub\_task\_end\_date            | String   | End date of Sub task attached to task                                                        |
| solution\_id                    | String   | Unique identifier of the Solution in an Project generated by system                          |
| task\_deleted\_flag             | String   | Indicates True or False which tells whether the task is deleted by the user from the app     |
| certificate\_template\_url      | String   | Url of the Ceritificate generated for the projects                                           |
| project\_created\_type          | String   | Type of the project either Imported from library (or) created by the user                    |
| task\_evidence                  | String   | Link of the attachment uploaded at the task level in a project                               |
| task\_sequence                  | int      | sequence of the tasks                                                                        |
| project\_id                     | String   | Unique identifier of the Project created or mapped                                           |
| program\_id                     | String   | Unique identifier of the program to which the project is mapped to                           |
| project\_last\_sync             | String   | Last sync date of the project                                                                |
| sub\_task\_id                   | String   | Unique identifier of Sub task attached to the task                                           |
| sub\_task\_status               | String   | Status of Sub task attached to the task                                                      |
| area\_of\_improvement           | String   | Category of the project created or assigned or imported                                      |
| task\_count                     | Long     | Total count of tasks in project                                                              |
| sub\_task                       | String   | Name of Sub task attached to the task                                                        |
| project\_created\_date          | Date     | Date of creation of the project                                                              |
| project\_evidence\_count        | Long     | Total attachment count uploaded for Project                                                  |

## ml-project-status | ml-project-programLevel-status

| Dimensions                  | Datatype | Description                                                                                                             |
| --------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------- |
| unique\_projects            | long     | Agg. coloumn in druid - countDistinct of project\_id                                                                    |
| unique\_users               | long     | Agg. coloumn in druid - countDistinct of createdBy                                                                      |
| unique\_solution            | long     | Agg. coloumn in druid - countDistinct of solution\_id                                                                   |
| no\_of\_certificate\_issued | long     | Agg. coloumn in druid - countDistinct of "certificate\_status\_customised" == "Issued" , "project\_id"                  |
| no\_of\_imp\_with\_evidence | long     | Agg. coloumn in druid - countDistinct of "evidence\_status" == True, "status\_of\_project" == "submitted","project\_id" |

## sl-observation

| Dimensions                        | Datatype | Description                                                                                      |
| --------------------------------- | -------- | ------------------------------------------------------------------------------------------------ |
| solutionExternalId                | String   | Unique identifier of the Solution in an observation                                              |
| questionResponseType              | String   | which type of question is - Like text, radio, slider, multiselect, matrix, date, number          |
| instanceParentCriteriaName        | String   | question type has matrix Name of that is instanceParentCriteriaName                              |
| criteriaId                        | String   | Unique identifier of the Criteria in an observation                                              |
| criteriaName                      | String   | Name of the Criteria to which the observation is submitted                                       |
| location\_validated\_with\_geotag | String   | Observe Again location of user after user submitted                                              |
| user\_boardName                   | String   | Board Name of the user belongs to - CBSE, State (Andhra Pradesh), IGOT-Health etc                |
| observationId                     | String   | Unique identifier of the an observation                                                          |
| programName                       | String   | Name of the program to which the observation is submitted                                        |
| blockName                         | String   | Name of the Block mapped to the user                                                             |
| childType                         | String   | Type of sub question in criteria - criteria                                                      |
| organisation\_name                | String   | Organisation Name of the user belongs to -Staging Custodian Organization, Globe etc              |
| user\_clusterName                 | String   | Cluster Name of the user belongs to                                                              |
| solution\_type                    | String   | Defines the type of Solution                                                                     |
| criteriaExternalId                | String   | Unique identifier of the Criteria in an observation                                              |
| questionResponseLabel             | String   | Answers given by User                                                                            |
| instanceParentExternalId          | String   | Matrix question External Id                                                                      |
| domainLevel                       | String   | level label of Domin                                                                             |
| imp\_project\_externalId          | String   | Unique Identifier for the project                                                                |
| organisation\_id                  | String   | Unique Identifier for the organisation                                                           |
| districtName                      | String   | Name of the District mapped to the user                                                          |
| entityName                        | String   | Name of the entity added by the user during observation submission                               |
| instanceParentResponsetype        | String   | which type of question is - Like text, radio, slider, multiselect inside instance question       |
| clusterExternalId                 | String   | Unique identifier of the cluster                                                                 |
| entityExternalId                  | String   | Unique identifier of the entity added by the user during observation submission                  |
| instanceParentId                  | String   | Unique identifier of the instance parent                                                         |
| instanceParentQuestion            | String   | question type has matrix Name of that is                                                         |
| scoringSystem                     | String   | Type of scoring is the question has Ex : pointBasedScoring                                       |
| district\_externalId              | String   | Unique identifier of the District mapped to the user                                             |
| instanceId                        | String   | Unique identifier of the instance                                                                |
| role\_title                       | String   | User sub type                                                                                    |
| observationSubmissionId           | String   | Unique identifier generated by system for each submission                                        |
| district                          | String   | Name of the District mapped to the user                                                          |
| instanceParentEcmSequence         | Long     | sequence order of Questions                                                                      |
| state\_code                       | Long     | Unique identifier of the State code                                                              |
| maxScore                          | String   | Max score can be given for Questions                                                             |
| questionExternalId                | String   | Unique identifier for the Questions                                                              |
| questionName                      | String   | Question label                                                                                   |
| criteriaLevelReport               | Boolean  | Is question criteria level                                                                       |
| submissionNumber                  | String   | how many submission done for observation                                                         |
| stateExternalId                   | String   | Unique identifier of the State mapped to the user                                                |
| evidences                         | String   | Link of the attachment uploaded                                                                  |
| percentageScore                   | String   | percentage of score got for observation                                                          |
| user\_schoolUDISE\_code           | String   | Unique identifier for the school                                                                 |
| question\_response\_number        | String   | Answers for question response type number                                                        |
| completedDate                     | Date     | Observation submission completion date                                                           |
| user\_type                        | String   | User Role                                                                                        |
| childName                         | String   | Name of the criteria                                                                             |
| solutionName                      | String   | Name of the Project                                                                              |
| domainExternalId                  | String   | Unique identifier for the Domian                                                                 |
| programId                         | String   | Unique identifier generated by the system for the observation submitted                          |
| solutionId                        | String   | Unique identifier of the Solution in an observation generated by system                          |
| criteriaDescription               | String   | Description of Criteria                                                                          |
| instanceParentCriteriaExternalId  | String   | question type has matrix Id of that                                                              |
| cluster                           | String   | Name of the Cluster mapped to the user                                                           |
| user\_schoolName                  | String   | Name of the School mapped to the user                                                            |
| observationName                   | String   | Name of the solution to which the observation is submitted                                       |
| questionId                        | String   | Unique identifier for the question                                                               |
| user\_districtName                | String   | Name of the District mapped to the user                                                          |
| entityType                        | String   | Type of entity for the observation submission                                                    |
| questionSequenceByEcm             | String   | Sequenced order of Questions                                                                     |
| createdBy                         | String   | User keycloak id on the sunbrid platform                                                         |
| channel                           | String   | Root organisation of the user                                                                    |
| entityTypeId                      | String   | System generated unique identifier of the entity added by the user during observation submission |
| programExternalId                 | String   | Unique identifier of the observation submitted                                                   |
| ancestorName                      | String   | Name of ancestor                                                                                 |
| isRubricDriven                    | Boolean  | Defines the type of Solution                                                                     |
| state                             | String   | Name of the State mapped to the user                                                             |
| cluster\_externalId               | String   | Unique identifier of the cluster                                                                 |
| isAPrivateProgram                 | String   | Boolean value that defines program type                                                          |
| childExternalid                   | String   | Unique identifier of the criteria                                                                |
| imp\_project\_goal                | String   | Goal of project                                                                                  |
| block\_code                       | Long     | Unique identifier of the Block code                                                              |
| school                            | String   | Name of the School mapped to the user                                                            |
| evidence\_count                   | String   | Total attachment count uploaded                                                                  |
| criteriaLevel                     | String   | level of Criteria                                                                                |
| district\_code                    | Long     | Unique identifier of the District code                                                           |
| cluster\_code                     | Long     | Unique identifier of the Cluster code                                                            |
| parent\_channel                   | String   | Column with constant value - "SHIKSHALOKAM"                                                      |
| programDescription                | String   | description of the Program                                                                       |
| submissionTitle                   | String   | Tittle of Submission                                                                             |
| user\_blockName                   | String   | Name of the Block mapped to the user                                                             |
| isSubmissionDeleted               | Boolean  | is submission deleted or not                                                                     |
| solutionDescription               | String   | Name of the solution to which the observation is submitted                                       |
| domainScore                       | String   | score's of Domin questions                                                                       |
| questionResponseLabel\_number     | String   | Ans for question response type number                                                            |
| entity                            | String   | Name of the entity added by the user during observation submission                               |
| clusterName                       | String   | Name of the Cluster mapped to the user                                                           |
| instanceParentCriteriaId          | String   | matrix question criteria id                                                                      |
| user\_stateName                   | String   | Name of the State mapped to the user                                                             |
| createdAt                         | Date     | Date of creation of the observation                                                              |
| criteriaScore                     | String   | score's of criteria questions                                                                    |
| minScore                          | String   | minimum score's for questions                                                                    |
| stateName                         | String   | Name of the State mapped to the user                                                             |
| total\_evidences                  | Long     | Total attachment count uploaded for observation                                                  |
| updatedAt                         | Date     | observation last updated date                                                                    |
| label                             | String   | Name of the level's - level1, level2                                                             |
| imp\_project\_title               | String   | Title of project in observations                                                                 |
| blockExternalId                   | String   | Unique identifier of the Block                                                                   |
| pointsBasedScoreInParent          | Long     | points based scoring system for parent type question                                             |
| domainName                        | String   | Name of the Domain                                                                               |
| schoolName                        | String   | Name of the School                                                                               |
| remarks                           | String   | Remarks Given By the User                                                                        |
| scoreAchieved                     | String   | Total score achivedBy User                                                                       |
| school\_externalId                | String   | Unique identifier of the School mapped to the user                                               |
| totalScore                        | String   | Total score of observation                                                                       |
| block\_externalId                 | String   | Unique identifier of the Block                                                                   |
| school\_code                      | Long     | Unique identifier of the school code                                                             |
| state\_externalId                 | String   | Unique identifier of the State                                                                   |
| schoolExternalId                  | String   | Unique identifier of the School Id mapped to the user                                            |
| user\_schoolId                    | String   | Unique identifier of the School mapped to the user                                               |

## sl-observation-status

| Dimensions               | Datatype | Description                                                                                      |
| ------------------------ | -------- | ------------------------------------------------------------------------------------------------ |
| solution\_id             | String   | Unique identifier of the Solution in an observation generated by system                          |
| observed\_district\_code | Long     | Observe Again Submission Entity i,e Districy Code                                                |
| observed\_state\_code    | Long     | Observe Again Submission Entity i,e State Code                                                   |
| state\_name              | String   | Name of the State mapped to the user                                                             |
| solution\_name           | String   | Name of the solution to which the observation is submitted                                       |
| observed\_district\_id   | Long     | Observe Again Submission Entity i,e District Id                                                  |
| observed\_school\_name   | Long     | Observe Again Submission Entity i,e School Id                                                    |
| user\_id                 | String   | User keycloak id on the sunbrid platform                                                         |
| observed\_cluster\_id    | Long     | Observe Again Submission Entity i,e Cluster Id                                                   |
| program\_id              | String   | Unique identifier of the program to which the observaion is mapped to                            |
| program\_externalId      | String   | Unique identifier of the program to which the observation is mapped to                           |
| observed\_cluster\_code  | Long     | Observe Again Submission Entity i,e Cluster Code                                                 |
| app\_name                | String   | Column with constant value - "dikshasurvey"                                                      |
| observed\_school\_code   | Long     | Observe Again Submission Entity i,e School Code                                                  |
| observed\_state\_name    | String   | Observe Again Submission Entity i,e state                                                        |
| ecm\_marked\_na          | String   | Evidence collection method marked as Not Applicable                                              |
| cluster\_name            | String   | Name of the Cluster mapped to the user                                                           |
| observed\_district\_name | String   | Observe Again Submission Entity i,e District                                                     |
| submission\_id           | String   | Unique system generated identifier for each observation submissions                              |
| entity\_type             | String   | Type of entity for the observation submission                                                    |
| observed\_block\_name    | String   | Observe Again Submission Entity i,e Block                                                        |
| status                   | String   | Status of the observation submission                                                             |
| entity\_externalId       | String   | Unique identifier of the entity added by the user during observation submission                  |
| entity\_name             | String   | Name of the entity added by the user during observation submission                               |
| observed\_cluster\_name  | String   | Observe Again Submission Entity i,e Cluster Name                                                 |
| school\_name             | String   | Name of the School declared by the User                                                          |
| solution\_externalId     | String   | Unique identifier of the Solution in an observation                                              |
| block\_name              | String   | Name of the Block mapped to the user                                                             |
| program\_name            | String   | Name of the program to which the observation is submitted                                        |
| observed\_block\_id      | Long     | Observe Again Submission Entity i,e Block Id                                                     |
| observed\_state\_id      | Long     | Observe Again Submission Entity i,e Sate Id                                                      |
| private\_program         | String   | boolean value that defines program type                                                          |
| observed\_block\_code    | Long     | Observe Again Submission Entity i,e Block Code                                                   |
| board\_name              | String   | Name of the board mapped to the user                                                             |
| observed\_school\_id     | Long     | Observe Again Submission Entity i,e School Id                                                    |
| district\_name           | String   | Name of the District mapped to the user                                                          |
| entity\_id               | String   | System generated unique identifier of the entity added by the user during observation submission |

## ml-obs-status

| Dimensions          | Datatype | Description                                             |
| ------------------- | -------- | ------------------------------------------------------- |
| unique\_entities    | Long     | Agg. coloumn in druid - countDistinct of entity\_id     |
| unique\_submissions | Long     | Agg. coloumn in druid - countDistinct of submission\_id |
| unique\_users       | Long     | Agg. coloumn in druid - countDistinct of createdBy      |
| unique\_solution    | Long     | Agg. coloumn in druid - countDistinct of solution\_id   |

## ml-obs-domain | ml-obs-domain-criteria

| Dimensions          | Datatype | Description                                             |
| ------------------- | -------- | ------------------------------------------------------- |
| domain\_externalId  | String   | Unique identifier of the Domian in an observation       |
| domain\_level       | String   | Level lable of the Domain                               |
| domain\_name        | String   | Name of the Domain                                      |
| unique\_users       | Long     | Agg. coloumn in druid - countDistinct of createdBy      |
| unique\_entities    | Long     | Agg. coloumn in druid - countDistinct of entity\_id     |
| unique\_solution    | Long     | Agg. coloumn in druid - countDistinct of solution\_id   |
| unique\_submissions | Long     | Agg. coloumn in druid - countDistinct of submission\_id |

## MongoDB Schema

## batchLogger collection

```
{
    "_id" : ObjectId,
    "dataSource" : String,  // druid data source
    "taskId" : String, // druid task id
    "taskCreatedDate" : String,
    "statusCode" : Integer,
    "createdAt" : ISODate,
    "updatedAt" : ISODate,
    "status" : String
}
```

## reports\_logger collection

```
{
    "_id": ObjectId,
    "operation": String, // frontend_update, backend_create
    "file": String,   // path of the report config JSON
    "reportId": String, // UUID of report
    "createdAt": ISODate,
    "updatedAt": ISODate,
    "config": Object, // report config
    "status": String // success, failed, duplicate  
}
```
