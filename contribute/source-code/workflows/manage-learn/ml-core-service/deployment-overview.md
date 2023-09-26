# Deployment Overview

### Developing a New Feature

* If you're working on a new feature, create a new branch in your local repository. Ensure that the branch is named descriptively, reflecting the feature's purpose.
* Implement the new feature within this branch, making necessary code changes and additions.
* Regularly commit your changes as you make progress.

### Generate the Latest Build Tag from Jenkins

* Once the PR is reviewed and approved, merge it into the "master" branch.
* Goto Jenkins and trigger tag creation job to generate the latest tag.
* Once a job is completed latest tag will be available in GitHub tag.

### Get Latest Build Tag from GitHub

* Access the GitHub repository.
* Navigate to the "Tags" section of the repository.
* Identify the latest build tag associated with the most recent release.
* This tag typically represents a specific version or build of the project.

The latest tag will be available here

{% embed url="https://github.com/project-sunbird/ml-core-service/tags" %}

### **Build Job with Latest Tag**

* Initiate a build job in Jenkins and provide the latest tag as a parameter.
* The build job compiles the code, runs tests, and prepares the artefacts for deployment.

### **Automatic Deployment Job Trigger (Optional)**

* After the build job successfully completes, an automatic deployment job may be triggered.
* This deployment job takes the compiled code and deploys it to the desired environment.

### **Manual Deployment (If Needed)**

* If the automatic deployment job is not triggered automatically, you can manually initiate the deployment job in Jenkins.
* This ensures that the latest version of the code is deployed.

### **Note About Job Paths**

* Depending on the environment you're working in (development, testing, production, etc.), the paths to these jobs may vary.
* Adjust the job paths according to your specific environment.

\


\
\
