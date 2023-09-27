# ENV Variables ( Config.ini)

\[ML\_APP\_NAME]

survey\_app = \{{ ml\_analytics\_survey\_app\_name \}}

// survey application name\


integrated\_app = \{{ ml\_analytics\_integrated\_app\_name \}}

// survey integrated application name\


integrated\_portal = \{{ ml\_analytics\_integrated\_portal\_name \}}

// Domain Name&#x20;



\[API\_HEADERS]

content\_type = application/json

// type of API body has\


authorization = \{{ ml\_analytics\_api\_authorization\_key \}}

// authorization for API call\


internal\_access\_token = \{{ ml\_analytics\_api\_access\_token \}}

// Refresh token for API call\


authorization\_access\_token = \{{ ml\_analytics\_authorization\_access\_token \}}

// Access token for API call\


\[MONGO]\


url = mongodb://\{{ ml\_analytics\_mongodb\_url \}}

// MongoDB IP Address and URL\


database\_name = \{{ ml\_analytics\_mongo\_db\_name \}}

// MongoDB Data Basese Name



\# ------ Mongo Collections ------- #

observation\_sub\_collection = \{{ ml\_analytics\_mongo\_observation\_submission\_collection \}}

// Collection name for observation submission in the database\


solutions\_collection = \{{ ml\_analytics\_mongo\_solution\_collection \}}

// Collection name for solution in the database\


observations\_collection = \{{ ml\_analytics\_mongo\_observation\_collection \}}

// Collection name for observation in the database\


entity\_type\_collection = \{{ ml\_analytics\_mongo\_entity\_type\_collection \}}

// Collection name for entityTypes in the database\


questions\_collection = \{{ ml\_analytics\_mongo\_question\_collection \}}

// Collection name for entityTypes in the database\


criteria\_collection = \{{ ml\_analytics\_mongo\_criteria\_collection \}}

// Collection name for criteria in the database\


entities\_collection = \{{ ml\_analytics\_mongo\_entities\_collection \}}

// Collection name for entities in the database\


programs\_collection = \{{ ml\_analytics\_mongo\_program\_collection \}}

// Collection name for programs in the database\


user\_roles\_collection = \{{ ml\_analytics\_mongo\_userroles\_collection \}}

// Collection name for userRoles in the database\


criteria\_questions\_collection = \{{ ml\_analytics\_mongo\_criteria\_questions\_collection \}}

// Collection name for criteriaQuestions in the database\


projects\_collection = \{{ ml\_analytics\_mongo\_projects\_collection \}}

// Collection name for projects in the database\


survey\_submissions\_collection = \{{ ml\_analytics\_mongo\_survey\_submissions\_collection \}}

// Collection name for surveySubmissions in the database

\


survey\_collection = \{{ ml\_analytics\_mongo\_survey\_collection \}}

// Collection name for surveys in the database\


reports\_log\_collec = \{{ ml\_analytics\_mongo\_reports\_log\_collec \}}

// Collection name for Reportsloger in the database\


\[DRUID]

metadata\_url = http://\{{ ml\_analytics\_druid\_url \}}/druid/coordinator/v1/datasources/

// Druid coordinator URL \


batch\_url = http://\{{ ml\_analytics\_druid\_url \}}/druid/indexer/v1/task

// Druid indexer URL\


metadata\_rollup\_url = http://\{{ ml\_analytics\_druid\_rollup\_url \}}/druid/coordinator/v1/datasources/

// Druid rollup coordinator URL \


batch\_rollup\_url = http://\{{ ml\_analytics\_druid\_rollup\_url \}}/druid/indexer/v1/task

// Druid  rollup indexer URL\


urlQuery = http://\{{ ml\_analytics\_druid\_query\_url \}}/druid/v2?pretty

// Druid Query URL\


observation\_status\_injestion\_spec = \{{ ml\_analytics\_druid\_observation\_status\_injestion\_spec \}}

// Druid ingestion spec for observation status\


project\_injestion\_spec = \{{ ml\_analytics\_druid\_project\_injestion\_spec \}}

// Druid ingestion spec for the project\


ml\_distinctCnt\_obs\_status\_spec = \{{ ml\_analytics\_druid\_distinctCnt\_obs\_injestion\_spec \}}

// Druid ingestion spec for distinct Count observation \


ml\_distinctCnt\_obs\_domain\_spec = \{{ ml\_analytics\_druid\_distinctCnt\_obs\_domain\_injestion\_spec \}}

// Druid ingestion spec for distinct Count observation domain\


ml\_distinctCnt\_obs\_domain\_criteria\_spec = \{{ ml\_analytics\_druid\_distinctCnt\_obs\_domain\_criteria\_injestion\_spec \}}

// Druid ingestion spec for distinct Count observation domain criteria\


ml\_distinctCnt\_projects\_status\_spec = \{{ ml\_analytics\_druid\_distinctCnt\_projects\_status\_injestion\_spec \}}

// Druid ingestion spec for distinct Count project\


ml\_distinctCnt\_prglevel\_projects\_status\_spec = \{{ ml\_analytics\_druid\_distinctCnt\_prglevel\_projects\_status\_injestion\_spec \}}

// Druid ingestion spec for distinct Count project program level\


observation\_status\_rollup\_injestion\_spec = \{{ ml\_analytics\_druid\_observation\_status\_rollup\_injestion\_spec \}}

// Druid ingestion spec for observation status rollup \


project\_rollup\_injestion\_spec = \{{ ml\_analytics\_druid\_project\_rollup\_injestion\_spec \}}

// Druid ingestion spec for project status rollup\


ml\_survey\_rollup\_spec = \{{ml\_analytics\_druid\_survey\_rollup\_injestion\_spec\}}

// Druid ingestion spec for survey status rollup\


survey\_status\_injestion\_spec = \{{ ml\_analytics\_druid\_survey\_status\_injestion\_spec \}}

// Druid ingestion spec for Survey \


observation\_query\_spec = \{{ ml\_analytics\_druid\_observation\_query\_spec \}}

// Druid query spec for observation\


observation\_injestion\_spec = \{{ml\_analytics\_druid\_observation\_batch\_ingestion\_spec\}}

// Druid spec for observation \


survey\_query\_spec = \{{ml\_analytics\_druid\_survey\_query\_spec\}}

// Druid query spec for survey\


survey\_injestion\_spec = \{{ml\_analytics\_druid\_survey\_batch\_ingestion\_spec\}}

// Druid spec for survey



intervals = \{{ml\_analytics\_druid\_interval\_list\}}

// Druid interval variables \
\


\[KAFKA]

url = \{{ ml\_analytics\_kafka\_url \}}

// Kafka IP address \


observation\_raw\_topic = \{{ ml\_analytics\_kafka\_observation\_topic\_name \}}

// Kafka observation raw topic name\


observation\_druid\_topic = \{{ ml\_analytics\_kafka\_observation\_druid\_topic\_name \}}

// Kafka observation druid topic name



observation\_evidence\_druid\_topic =  \{{ ml\_analytics\_kafka\_observation\_evidence\_topic\_name \}}

// Kafka observation evidence topic name\


survey\_evidence\_druid\_topic = \{{ ml\_analytics\_kafka\_survey\_evidence\_topic\_name \}}

// Kafka survey evidence topic name\


survey\_raw\_topic = \{{ ml\_analytics\_kafka\_survey\_topic\_name \}}

// Kafka survey raw topic name\


survey\_druid\_topic = \{{ ml\_analytics\_kafka\_survey\_druid\_topic\_name \}}

// Kafka survey druid topic name\


\[LOGS]

observation\_streaming\_success\_error = \{{ ml\_analytics\_observation\_log\_folder\_path \}}/

// file path for loggers for observation streaming\


observation\_streaming\_evidence\_success\_error = \{{ ml\_analytics\_observation\_log\_folder\_path \}}/evidence/

// file path for loggers for observation evidence\


observation\_status\_success\_error = \{{ ml\_analytics\_observation\_log\_folder\_path \}}/status/

// file path for loggers for observation status\


project\_success\_error = \{{ ml\_analytics\_project\_log\_folder\_path \}}/

// file path for loggers for project\


survey\_evidence\_streaming\_success\_error = \{{ ml\_analytics\_survey\_log\_folder\_path \}}/evidence/

// file path for loggers for survey evidence\


survey\_streaming\_success\_error = \{{ ml\_analytics\_survey\_log\_folder\_path \}}/

// file path for loggers for survey streaming\


survey\_status\_success\_error = \{{ ml\_analytics\_survey\_log\_folder\_path \}}/status/

// file path for loggers for survey status\
\


\[ORACLE]

endpoint\_url = \{{ ml\_ORACLE\_endpoint\_url \}}

// ORACLE endpoint url\


access\_key = \{{ ml\_ORACLE\_access\_key \}}

// ORACLE access key\


secret\_access\_key = \{{ ml\_ORACLE\_secret\_access\_key \}}

// ORACLE secret access key\


region\_name = \{{ ml\_ORACLE\_region\_name \}}

// ORACLE region name



bucket\_name = \{{ ml\_ORACLE\_bucket\_name \}}

// ORACLE bucket name\
\


\[GCP]

secret\_data = \{{ ml\_GCP\_secret\_json\_file \}}

// GCP secret json file path



bucket\_name = \{{ ml\_GCP\_bucket\_name \}}

// GCP bucket name\
\


\[AWS]

service\_name = \{{ ml\_AWS\_service\_name \}}

// AWS service name\


access\_key = \{{ ml\_AWS\_access\_key \}}

// AWS access key



secret\_access\_key = \{{ ml\_AWS\_secret\_access\_key \}}

// AWS secret access key

region\_name = \{{ ml\_AWS\_region\_name \}}

// AWS region name

bucket\_name = \{{ ml\_AWS\_bucket\_name \}}

// AWS bucket name\
\


\[AZURE]

account\_name = \{{ ml\_analytics\_azure\_account\_name \}}

// Azure account name\


sas\_token = \{{ ml\_analytics\_azure\_sas\_token \}}

// Azure sas token\


container\_name = \{{ ml\_analytics\_azure\_container\_name \}}

// Azure container name \


account\_key = \{{ ml\_analytics\_azure\_account\_key \}}

// Azure account key \
\


\[OUTPUT\_DIR]

project = \{{ ml\_analytics\_project\_output\_dir \}}

// file path for project\


observation\_status = \{{ ml\_analytics\_observation\_status\_output\_dir \}}

// file path for observation status\


observation\_distinctCount\_status = \{{ ml\_analytics\_obs\_distinctCnt\_output\_dir \}}

// file path for observation distinct Count status\


observation\_distinctCount\_domain = \{{ ml\_analytics\_obs\_distinctCnt\_domain\_output\_dir \}}

// file path for observation distinct Count domain\


observation\_distinctCount\_domain\_criteria = \{{ ml\_analytics\_obs\_distinctCnt\_domain\_criteria\_output\_dir \}}

// file path for observation distinct Count domain criteria\


projects\_distinctCount = \{{ ml\_analytics\_projects\_distinctCnt\_output\_dir \}}

// file path for project distinct Count \


projects\_distinctCount\_prgmlevel = \{{ ml\_analytics\_projects\_distinctCnt\_prglevel\_output\_dir \}}

// file path for project distinct Count program level\


project\_rollup = \{{ ml\_analytics\_project\_rollup\_output\_dir \}}

// file path for project rollup \


observation\_status\_rollup = \{{ ml\_analytics\_observation\_status\_rollup\_output\_dir \}}

// file path for observation status rollup\


survey\_rollup = \{{ ml\_analytics\_survey\_rollup\_output\_dir \}}

// file path for survey rollup\


survey\_status = \{{ ml\_analytics\_survey\_status\_output\_dir \}}

// file path for survey status\


observation\_sub\_ids = \{{ ml\_analytics\_observation\_submission\_id\_filepath \}}

// file path for observation submission ID\


observation\_druid\_data = \{{ ml\_analytics\_observation\_batchupdate\_output\_dir \}}

// file path for observation batch update for druid&#x20;



survey\_sub\_ids = \{{ml\_analytics\_survey\_submission\_id\_filepath\}}

// file path for survey submission ID



survey\_druid\_data = \{{ml\_analytics\_survey\_batchupdate\_output\_dir\}}

// file path for survey druid data&#x20;



program\_text\_file = \{{ml\_analytics\_project\_program\}}

// file path for project program ID\
\


\[VAM]

druid\_query\_url = \{{ ml\_druid\_query\_data \}}

// Druid query URL

program\_dashboard\_data = \{{ ml\_program\_dashboard\_data \}}

// Program Dash board data \


\[COMMON]

cloud\_module\_path = \{{ ml\_analytics\_cloud\_package\_path \}}

// File path for cloud class&#x20;



observation\_blob\_path = \{{ ml\_analytics\_observation\_azure\_blob\_path \}}

// File path for observation in cloud\


projects\_blob\_path = \{{ ml\_analytics\_project\_azure\_blob\_path \}}

// File path for project in cloud \


observation\_distinctCount\_blob\_path = \{{ ml\_analytics\_obs\_distinctCnt\_azure\_blob\_path \}}

// File path for observation distinct Count in cloud\


observation\_distinctCount\_domain\_blob\_path = \{{ ml\_analytics\_obs\_distinctCnt\_domain\_azure\_blob\_path \}}

// File path for observation distinct Count domain in cloud\


observation\_distinctCount\_domain\_criteria\_blob\_path = \{{ ml\_analytics\_obs\_distinctCnt\_domain\_criteria\_azure\_blob\_path \}}

// File path for observation distinct Count domain criteria in cloud\


projects\_distinctCnt\_blob\_path = \{{ ml\_analytics\_projects\_distinctCnt\_azure\_blob\_path \}}

// File path for project distinct Count in cloud\


projects\_distinctCnt\_prgmlevel\_blob\_path = \{{ ml\_analytics\_projects\_distinctCnt\_prglevel\_azure\_blob\_path \}}

// File path for project program level distinct Count in cloud\


projects\_rollup\_blob\_path = \{{ ml\_analytics\_project\_rollup\_azure\_blob\_path \}}

// File path for project rollup in cloud \


observation\_rollup\_blob\_path = \{{ ml\_analytics\_observation\_rollup\_azure\_blob\_path \}}

// File path for observation rollup in cloud \


survey\_rollup\_blob\_path = \{{ ml\_analytics\_survey\_rollup\_azure\_blob\_path \}}

// File path for survey rollup in cloud \


survey\_blob\_path = \{{ ml\_analytics\_survey\_azure\_blob\_path \}}

// File path for survey in cloud \


projects\_program\_csv = \{{ ml\_analytics\_program\_dashboard\_azure\_blob\_path \}}

// File path for project program ID in cloud&#x20;



observation\_batch\_ingestion\_data\_del = \{{ ml\_analytics\_observation\_batchupdate\_azure\_blob\_path \}}

// File path for observation batch data delete in cloud\


survey\_batch\_ingestion\_data\_del = \{{ml\_analytics\_survey\_batchupdate\_azure\_blob\_path\}}

// File path for survey batch data delete in cloud



cname\_url = \{{ ml\_analytics\_cname\_url \}}

// Cname URL



nvsk\_imp\_projects\_data\_local\_path = \{{ ml\_analytics\_nvsk\_imp\_projects\_data\_local\_path \}}

// File path for NVSK in local&#x20;



nvsk\_imp\_projects\_data\_blob\_path = \{{ ml\_analytics\_nvsk\_imp\_projects\_data\_blob\_path \}}

// File path for NVSK in cloud



nvsk\_imp\_projects\_state\_data\_local\_path = \{{ ml\_analytics\_nvsk\_imp\_projects\_state\_data\_local\_path \}}

// File path for NVsK state level data in local&#x20;



nvsk\_imp\_projects\_state\_data\_blob\_path = \{{ ml\_analytics\_nvsk\_imp\_projects\_state\_data\_blob\_path \}}

// File path for NVSK state level data in cloud\


\[API\_CREDENTIALS]

client\_id = \{{ ml\_analytics\_client\_id \}}

// Client ID for Reports Portal HawkEye API's\


client\_secret = \{{ ml\_analytics\_client\_secret \}}

// Client secret ID for Reports Portal HawkEye API's\


grant\_type = \{{ ml\_analytics\_grant\_type \}}

// Grant type for Reports Portal HawkEye API's



username = \{{ ml\_analytics\_username \}}

// User Name for Reports Portal HawkEye API's



password = \{{ ml\_analytics\_password \}}

// Password Reports Portal HawkEye API's\


\[REPORTS\_FILEPATH]

script\_path = \{{ ml\_analytics\_script\_path \}}

// File path for report creation \


\[JSON\_VARIABLE]

createdBy = \{{ ml\_analytics\_createdBy \}}

// report creator user ID&#x20;

container = \{{ ml\_analytics\_reports\_container \}}

// container name for HawkEye reports

store = \{{ ml\_analytics\_reports\_sore \}}

// store name for HawkEye reports

key = \{{ ml\_analytics\_reports\_key \}}

//  key for HawkEye reports

\


\
