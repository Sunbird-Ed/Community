# Functional Configurations

To configure Sunbird Ed platform based on your use case, you will need to use the Postman tool. You can download and install the Postman tool by visiting the following link: https://www.postman.com/downloads/.

Please refer the below mentioned postman collection to setup minimal functional configuration for content creation workflow. Download the postman collection of Sunbird-Ed functional configuration from [here](https://github.com/project-sunbird/sunbird-ed-installer/tree/main/postman-collection)

Download the postman environment variable file (`postman.env.json`) from [here](https://github.com/project-sunbird/sunbird-ed-installer/blob/main/terraform/azure/template/postman.env.json) and replace the place holder values with actual values.

> NOTE: The above link points to Azure Postman ENV file from template directory. Depending on the cloud provider, please download the respective file.

​Import postman collection and environment variables to postman tool

refer: ​[https://learning.postman.com/docs/getting-started/importing-and-exporting-data/#importing-postman-data](https://learning.postman.com/docs/getting-started/importing-and-exporting-data/#importing-postman-data)

* Once the import is done, click on the "Collections" tab located in the upper-left corner. From the dropdown menu in the upper-right corner, select the desired environment name.
* Right click on the collection and choose `Run collection`. In `Run Configuration` section update `Delay` to `500ms` and then run the collection. This will trigger all the apis in the collection.

For forms related configurations and customizations, refer to the postman collection [here](https://www.postman.com/sunbird-building-blocks/sunbird-ed-coss/overview)
