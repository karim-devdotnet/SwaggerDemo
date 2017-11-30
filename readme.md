# ASP.NET-Web-API-Hilfeseiten mit Swagger

http://wmpratt.com/swagger-and-asp-net-web-api-part-1/

### Adding Swagger to Web Api Project
To add Swagger to an ASP.NET Web Api, we will install an open source project called Swashbuckle via nuget.

PM> Install-Package Swashbuckle -version 5.2.1

### Configuring Swagger
Open SwaggerConfig.cs and check the following code line:
 
GlobalConfiguration.Configuration
  .EnableSwagger(c => c.SingleApiVersion("v1", "A title for your API"))
  .EnableSwaggerUi();

### Calling swagger
Start a new debugging session (F5) and navigate to http://localhost:12345/swagger