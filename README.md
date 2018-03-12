# Azure Cognitive Services API's with SQL Integration Services Packages (SSIS)
A SQL SSIS package which integrates calls to Azure Cognitive Services Translate Text API.  The text translation is part of the ETL data flow to integrate multi-language support into a SQL DW with SQL SSIS ETL solution.  

Please see associated blog post for more information on this application
https://mrfoxsql.wordpress.com/2018/03/13/azure-cognitive-services-apis-with-sql-integration-services-packages/

Instructions;

When you open the solution in VS2017, you will need to update the following...
* Package Variable "TranslateAuthKey" holds the Translator Text API Key.  You need to deploy the Translator Text API service via the Azure Portal into your Subscription (as per the link in the above sevtion), and grab the API Key.
* Package Variable "TranslateFrom" holds the Source Language.  Currently this is set as "en" for English language transaction.
* Package Variable "TranslateTo" holds the Target Language.  Currently this is set as "de" for German language transaction.
* The Connection Manager to point the package to your SQL Server where you want to create the Stage + DW tables as above.  They will be created by the SQL SSIS package in your tempdb database

Once done you can just run the SSIS package and it will connect to your SQL Server, provision the database tables in the SQL tempdb database, create some sample data and call out to the Azure Cognitive API to translate!

NOTE 1: The application code is provided free without any support or warranty of any kind.   The code has not been thoroughly tested and is not considered production ready.   The code is provided free of charge and can be reused in any way you wish.   Please check my the disclaimer in my blog post above to learn more.
