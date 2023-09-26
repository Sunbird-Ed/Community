# Data Model

### DB Schema

The schema serves as a blueprint for creating and maintaining the database that supports the ML Core Services data storage and retrieval operations.

![ML-Core Service](https://ml-services-uploads.s3.ap-south-1.amazonaws.com/DBSchema/ML-Core.png)



#### Here are examples of sample data for each collection

#### [program](https://github.com/shikshalokam/ml-core-service/blob/master/DBSchema/programs.json)

Programs collection is tasked with housing high-level program information, encompassing program specifics, resource listings, and program categorizations.

#### [programUser](https://github.com/shikshalokam/ml-core-service/blob/master/DBSchema/programUsers.json)

The programUsers Collection holds user data of those who have become part of the program and have provided their consent status.

#### [certificateBaseTemplates](https://github.com/shikshalokam/ml-core-service/blob/master/DBSchema/certificateBaseTemplates.json)

The certificateBaseTemplates collection is utilized to store URLs and file paths indicating the storage location of certificate files, along with their corresponding certificate types.

#### [certificateTemplates](https://github.com/shikshalokam/ml-core-service/blob/master/DBSchema/certificateTemplates.json)

The certificateTemplates collection will be established for solutions and associated with certificate templates to facilitate the generation of certificates, incorporating predefined criteria.

#### [solutions](https://github.com/shikshalokam/ml-core-service/blob/master/DBSchema/solutions.json)

The solutions collection will serve as a repository for various types of resources, encompassing observations, improvement projects, and surveys, among others.

#### [userExtension](https://github.com/shikshalokam/ml-core-service/blob/master/DBSchema/userExtension.json)

The userExtension collection will be responsible for storing user information, including associated solutionsId and programId, indicating their roles as program managers or designers.

[Click here](https://ml-services-uploads.s3.ap-south-1.amazonaws.com/DBSchema/ML-Core.pdf) for DB schema and corresponding examples in a PDF format.
