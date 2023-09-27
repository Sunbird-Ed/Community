# Component Diagram

## GitHub Repository

{% embed url="https://github.com/project-sunbird/sunbird-ext-framework" %}

### Plugin - Form service

The form service is built as an plugin for the above extensible framework.

{% embed url="https://github.com/project-sunbird/sunbird-ext-framework/tree/master/demo/plugins/FormService" %}

## Architecture

<figure><img src="../../../../.gitbook/assets/Screenshot 2023-08-11 at 4.20.54 PM.png" alt=""><figcaption><p>Form Service plugin Architecture</p></figcaption></figure>

## [From Service Plugin](https://github.com/project-sunbird/sunbird-ext-framework/blob/master/server/README.md)

It's an extensible framework library to create a server side API endpoint.

### [EXT Framework Server](https://github.com/project-sunbird/sunbird-ext-framework/blob/master/demo/plugins/FormService/server/manifest.ts)

During this phase, the framework tries to read the manifest.ts file under the plugin's home directory.

When it finds the manifest.ts file, it will register the plugin in the "plugin registry" and update the status of the plugin as REGISTERED.

The framework tries to locate if any schema files are defined in the manifest.ts file. If the plugin has not defined any schema file, the framework would skip this step.

If there are schema files, then it would try to create a schema(tables/index) on the corresponding database provided based on the schema definition

### [Framework API /Route](https://github.com/project-sunbird/sunbird-ext-framework/blob/master/demo/plugins/FormService/server/routes.ts)

During this phase, the framework tries to find `routes.ts` files under the plugin home directory. If the file is not found, the plugin fails to load.

The file should export a class named `Router`. The framework registers the routes(endpoint) defined for the plugin with the "prefix" defined in the `manifest.ts` file.

### [Request Validator](https://github.com/project-sunbird/sunbird-ext-framework/blob/master/demo/plugins/FormService/server/RequestValidator/index.ts)

During this phase, the framework will validate the request body that is requested by the client app. If the request doesn't have mandatory data or valid input it will throw the error in response.

### [Server Method](https://github.com/project-sunbird/sunbird-ext-framework/blob/master/demo/plugins/FormService/server/server.ts)

During this phase, the method retrieves data from a Cassandra database based on the provided query parameters.

It tries to find a matching record by gradually relaxing the constraints on the properties. Once a record is found or all attempts are exhausted, the retrieved data is processed and sent back as a response.

###
