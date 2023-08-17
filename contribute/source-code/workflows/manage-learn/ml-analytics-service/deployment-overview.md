# Deployment Overview

## Create RC Tag

* Log in to the Environment VPN.
* Open Jenkins and log in.
* Choose the "Release" option.
* Select the "StagingRCTag" from the available options.
* Opt for the "Build with Parameters" option.
* Choose "Sunbird-Ed/ml-analytics-service."
* Select the latest available release.
* Initiate the build process.

## Deploy Latest Version

* Log in to the Environment VPN.
* Access Jenkins and log in.
* Opt for the "Deploy" option.
* Select the desired environment.
* Choose the "managed-learn" option.
* Then select "ml-analytics-service."
* Select the "Build with Parameters" option.
* Provide the "private\_branch" parameter with the latest DevOps branch.
* In the "branch\_or\_tag" field, enter the latest tag.
* Initiate the build process.
