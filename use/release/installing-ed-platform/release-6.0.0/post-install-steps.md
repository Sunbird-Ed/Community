# Functional configurations

To configure these functionalities, you will need to use the Postman tool. You can download and install the Postman tool by visiting the following link: https://www.postman.com/downloads/.

Please refer the below mentioned postman collection to setup minimal functional configuration for content creation workflow.

Download the postman collection of Sunbird-Ed functional configuration

[https://github.com/project-sunbird/sunbird-devops/blob/oneclickinstaller/oneclickinstaller/collection.json](https://github.com/project-sunbird/sunbird-devops/blob/oneclickinstaller/oneclickinstaller/collection.json)

Download the postman environment variable file

[https://github.com/project-sunbird/sunbird-devops/blob/oneclickinstaller/oneclickinstaller/environment.json](https://github.com/project-sunbird/sunbird-devops/blob/oneclickinstaller/oneclickinstaller/environment.json)

Import postman collection and environment variables to postman tool

[https://learning.postman.com/docs/getting-started/importing-and-exporting-data/#importing-postman-data](https://learning.postman.com/docs/getting-started/importing-and-exporting-data/#importing-postman-data)\\

Update below mentioned environmental variables in postman tool. Please refer global\_values.yaml file for varaible values.

| Environment key name | global\_values.yaml key name                        | Description           |
| -------------------- | --------------------------------------------------- | --------------------- |
| host                 | domain                                              | http://example.co.in/ |
| kong\_api\_key       | Bearer \{{core\_vault\_sunbird\_api\_auth\_token\}} | Bearer xxx.yyy.zzz    |

* Import the Postman collection and environment files. Then, go to the "Environment" section and choose the "sunbird-easeinstall" environment. Update the values of the "host" and "kong\_api\_key" variables, and remember to save the changes.
* Once you have updated the environment variables, click on the "Collections" tab located in the upper-left corner. From the dropdown menu in the upper-right corner, select the desired environment name.
* Now, you can start triggering the APIs in the collection one by one, following the specified sequence. Proceed to the next API only when the response from the current API is a successful "200" status code.
