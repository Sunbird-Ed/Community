# Contribute to Sunbird ED

### **Contribution guidelines overview**

Contributions to the Sunbird building blocks can be in any form. One can contribute by:

1. Actively engaging with the community on the discussion forum.
2. Identifying the needs, i.e. bugs, documentation and installation issues, proposing new features and proposing enhancements to existing features.
3. Developing new features, enhancements or fixing bugs
4. Identifying and filling documentation gaps
5. Enhancing installation-related changes, release testing or any other area of interest.

​Any contribution proposal - it could be fixes for bugs, documentation issues, installation issues, new feature ideas or enhancements, etc. should ideally be brought in via a discussion forum post for alignment with the community.​​

**Contribution Workflow**

<figure><img src="https://1497159047-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F4ZKyfmmhMWpPkD6iYvKF%2Fuploads%2FjIvkMn7b8Dvg2BZyMLqs%2FScreenshot%202023-01-27%20at%201.03.59%20PM.png?alt=media&#x26;token=7d0c15f2-e724-4288-87f7-ffbe16c5de33" alt=""><figcaption></figcaption></figure>

An item is added to the issue tracker only after there is clarity about what needs to be done and alignment with the community/working group in terms of the approach or the design, as the case may be.

{% hint style="info" %}


* Any RFC or Enhancement issues created in the issue tracker should have high-level details of what is expected in the feature.
* If an issue (Bug/documentation/installation) requires a change in another building block, then the corresponding issue should be created in the other building block and linked (as - depends on) across the issue trackers
* The complexity and priority should be discussed in the discussion forum and, ideally, should be updated when the issue is created.
{% endhint %}

Once an item is picked up for contribution, it is important for the contributor to update the status of the issue in the tracker so that the community can see the progress being made. Once the contributor completes the development, the changes are finally validated and tested by the community QA team to sign off the changes for inclusion in the latest version of the building block. Any issues found during this testing have to be fixed by the contributor and validated by the QA team within the published release timelines.&#x20;

Further details on contribution issue statuses and workflows are available in the [**Sunbird Community Practices**](https://community.sunbird.org/) document.​ Some important points to keep in mind while making contributions:

* The test cases and results will be shared with the building block QA community. The test cases must be shared before creating a review and merge request. The test result should be documented and shared before the issue can be submitted for validation.
* The contributor QA team should also plan to contribute towards the release testing of the changes developed by them as per the release testing process.
* The contributor has to ensure that the code merge and the defect fixes happen as per the release timeline. In case the issue is not completed as per the release timeline, then the changes need to be reverted back, and a fresh PR request needs to be raised to revert the code changes

The issue will be tested by the community QA Team for the release sign-off as well, and its status will be updated as “Done” post the successful completion of release testing.​
