# .NET

#### Pokretanje projekta
     dotnet run
 
#### Pokretanje projekta s praćenjem izmjena
     dotnet watch run

# Razor

#### Stvaranje novog projekta
     dotnet new webapp -n NazivProjekta --no-https

#### Stvaranje Git ignore datoteke
     dotnet new gitignore

#### Instalacija potrebnih alata
     dotnet tool uninstall --global dotnet-aspnet-codegenerator
     dotnet tool install --global dotnet-aspnet-codegenerator
     dotnet tool uninstall --global dotnet-ef
     dotnet tool install --global dotnet-ef
     
#### Instalacija paketa za scaffolding
     dotnet add package Microsoft.EntityFrameworkCore.Design
     dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
     dotnet add package Microsoft.EntityFrameworkCore.SqlServer
     dotnet add package Microsoft.EntityFrameworkCore.Tools

#### Scaffolding modela
     dotnet aspnet-codegenerator razorpage -m Model -dc AppDbContext -udl -outDir Pages/Model --referenceScriptLibraries
     dotnet aspnet-codegenerator razorpage -m Todo -dc TodoAppDbContext -udl -outDir Pages/Todos --referenceScriptLibraries

#### Izrada migracije
     dotnet ef migrations add NazivMigracije

#### Ažuriranje baze podataka
     dotnet ef database update

#### Konekcijski string
     (pronaći ga na stranicama predmeta)

# MVC

#### Stvaranje novog projekta
     dotnet new mvc -n NazivProjekta --no-https

#### Stvaranje novog projekta s autentifikacijom
     dotnet new mvc -n NazivProjekta --no-https -uld -au Individual

#### Instalacija paketa za scaffolding
     dotnet add package Microsoft.EntityFrameworkCore.Design -v 8.0.10
     dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design -v 8.0.6
     dotnet add package Microsoft.EntityFrameworkCore.SqlServer -v 8.0.10
     dotnet add package Microsoft.EntityFrameworkCore.Tools -v 8.0.10

#### Scaffolding modela
     dotnet aspnet-codegenerator controller -name NazivKontrolera -m NazivModela -dc AppDbContext --relativeFolderPath Controllers --useDefaultLayout --referenceScriptLibraries
     
#### Unos rola
     INSERT INTO [dbo].[AspNetRoles]
           ([Id]
           ,[Name]
           ,[NormalizedName]
           ,[ConcurrencyStamp])
     VALUES
           ('1'
           ,'Admin'
           ,'ADMIN'
           ,'1');

#### Dodjela rola
     INSERT INTO [dbo].[AspNetUserRoles]
           ([UserId]
           ,[RoleId])
     VALUES
           ('8651f840-1462-45d2-8b96-dcde067a9531'
           ,'1');

# API

#### Stvaranje novog API projekta
     dotnet new webapi --use-controllers -o ProjektAPI

#### Instalacija paketa za scaffolding
     dotnet add package Microsoft.EntityFrameworkCore.Design
     dotnet add package Microsoft.EntityFrameworkCore.SqlServer
     dotnet add package Microsoft.EntityFrameworkCore.Tools
     dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design

#### Scaffolding modela
     dotnet aspnet-codegenerator controller -name NazivKontroler -async -api -m NazivModela -dc NazivDbContexta -outDir Controllers

#### CORS
     builder.Services.AddCors(options =>
     {
          options.AddPolicy("AllowAll", builder => builder.AllowAnyOrigin().AllowAnyMethod().AllowAnyHeader());
     });

     ...

     app.UseCors("AllowAll");
