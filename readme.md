# ASP.NET-Web-API-Hilfeseiten mit Swagger

http://wmpratt.com/swagger-and-asp-net-web-api-part-1/

### Adding Swagger to Web Api Project
To add Swagger to an ASP.NET Web Api, we will install an open source project called Swashbuckle via nuget.
```console
PM> Install-Package Swashbuckle -version 5.2.1
```
### Configuring Swagger
Open SwaggerConfig.cs and check the following code line:
 
GlobalConfiguration.Configuration
  .EnableSwagger(c => c.SingleApiVersion("v1", "A title for your API"))
  .EnableSwaggerUi();

### Calling swagger
Start a new debugging session (F5) and navigate to http://localhost:12345/swagger

### Using based token Authentication
1. Add the following in SwaggerConfig.cs
```c#
// NOTE: You must also configure 'EnableApiKeySupport' below in the SwaggerUI section
c.ApiKey("token")
 .Description("Filling bearer token here!")
 .Name("Authorization")
 .In("header");
```
in SwaggerUI activate the following line
```c#
c.EnableApiKeySupport("Authorization", "header");
```

2. Calling  http://localhost:12345/swagger
3. put **Bearer token** in the textbox *api_key*
4. For example **Bearer LfPuInwk9jFmQziX...-EQ0Qr9U**