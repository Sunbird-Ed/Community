# Projects

<figure><img src="../../../.gitbook/assets/9734d044-3220-408a-bc45-ea8a2aca102d (1).png" alt=""><figcaption><p><a href="https://sunbird-ed.github.io/docs/mobile/modules/ProjectModule.html">Project Module</a></p></figcaption></figure>

Read more on the project [here](https://ed.sunbird.org/misc/templates-1/overview/what-is-a-project)

### [List](https://sunbird-ed.github.io/docs/mobile/components/ProjectListingComponent.html)

This page consists of a list of, targeted, non-targetted, and created projects for the logged-in user.

_**Targeted Projects**_ - All the projects which match the user role will be shown to the logged-in user.

_**Non-targeted / Discovered Projects -**_ If the user takes a project which is not targeted for his role but accessed through a link, it is considered a nontargeted or discovered project. All these types will be listed in the Discovered tab of the listing page

_**Created Project**_ - The user will be able to create a project for themself. All the created user-created projects will be listed in this tab.

### [Template Details](https://sunbird-ed.github.io/docs/mobile/modules/ProjectTemplateviewPageModule.html)

Before starting a project user will be taken to the Template page where all the details of the projects will be shown and the user will be able to start a project. On starting the project, the project will be saved into the Local db ie. PouchDb. All the started project will be kept local and only reaches the server on sync action. The user will be redirected to the project details page post starting the project.

### [Project Details](https://sunbird-ed.github.io/docs/mobile/components/ProjectDetailsComponent.html)

The user will be able to do all the actions like share, edit, and sync on the project. Users will also be able to go through tasks and also add new tasks if needed. Once all the mandatory tasks are completed, the user will be able to submit the project. Post submission no actions can be done on the project. All the actions other than sync and Submit are offline

### [Task Details](https://sunbird-ed.github.io/docs/mobile/components/TaskViewPage.html)

Users will be able to change the status of the tasks and also create subtasks for the tasks. Users will also be able to go to the resources listing page and consume the resources. Remarks and evidence can also be attached at the task level

### Working of Sync and Submit flow

Once the user syncs or submit a project, the following are the steps happening in the app

* Checks if there is some evidence to be uploaded to the cloud storage.
* If there is pending evidence, App makes an API call to get the cloud upload URLs from the backend
* On receiving the URLs, Ap uploads the evidence to the cloud storage one after the other
* After completion of all evidence upload. the sync API will be called
