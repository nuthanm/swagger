# swagger
You will learn how to integrate swagger in C# using Visual studio code for api documentation and as well to test.

Using Swagger
1. Code is maintainable and readable by anyone.
2. Documentation helps consumers to understand the purpose and this way less maintaince cost and support from us.


## To create a new webapi project
dotnet new webapi --name **NameofyourAPI**
  
**Ex:** dotnet new webapi --name SwaggerDemoAPI
  
## To build your webapi project
dotnet build
  
## To run your webapi project
dotnet run
  
## To add a new package
dotnet add package **YourPackageName**
  
**Ex:** dotnet add package Swashbuckle.AspNetCore
  
Once added the package in your webapi project, The following configuration add in Startup.cs file
 
1. Add this namespace: **Microsoft.OpenApi.Models**
2. Add the following code in ConfigureServices method,
    services.AddSwaggerGen(swagger =>{
                swagger.SwaggerDoc("v1", new OpenApiInfo{Title="Weather Forecast", Version="v1"});
    });
 3. Add the following code in Configure Method,
    app.UseSwagger();
    app.UseSwaggerUI(swagger => {
                swagger.SwaggerEndpoint("/swagger/v1/swagger.json", "My Weather Forecast API");
    });
 4. Build and run your code
 5. Url to see the swagger is https://localhost:**yourport**/swagger/index.html
  

## Reference Link
https://docs.microsoft.com/en-us/learn/modules/improve-api-developer-experience-with-swagger/

