# Functional Configurations

To configure Sunbird Ed platform based on your use case, you will need to use the Postman tool. You can download and install the Postman tool by visiting the following link: https://www.postman.com/downloads/.

Please refer the below mentioned postman collection to setup minimal functional configuration for content creation workflow. Download the postman collection of Sunbird-Ed functional configuration from [here](https://github.com/project-sunbird/sunbird-ed-installer/blob/release-6.0.0/postman-collection/collectionrelease600.json)

Download the postman environment variable file from [here](https://github.com/project-sunbird/sunbird-ed-installer/blob/release-6.0.0/terraform/azure/template/postman.env.json) and replace the place holder values with actual values.

​Import postman collection and environment variables to postman tool

refer: ​[https://learning.postman.com/docs/getting-started/importing-and-exporting-data/#importing-postman-data](https://learning.postman.com/docs/getting-started/importing-and-exporting-data/#importing-postman-data)

* Once the import is done, click on the "Collections" tab located in the upper-left corner. From the dropdown menu in the upper-right corner, select the desired environment name.
* Right click on the collection and choose `Run collection`. In `Run Configuration` section update `Delay` to `500ms` and then run the collection. This will trigger all the apis in the collection.
