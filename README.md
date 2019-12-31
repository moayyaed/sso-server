# SSO Identity

## Development Environment
- Visual Studio Code
- IdentityServer4
- SQL Server

## Setup

#### To run the demo:

**1.** Clone/Fork this repository.

**2.** Create the database on your SQL Server by using the dotnet cli to run the migrations from within the command:

#### Force delete all table if need
```
SET FOREIGN_KEY_CHECKS = 0; 
SET @tables = NULL;
SELECT GROUP_CONCAT(table_schema, '.', table_name) INTO @tables
  FROM information_schema.tables 
  WHERE table_schema = 'AuthServer'; -- specify DB name here.
SET @tables = CONCAT('DROP TABLE ', @tables);
PREPARE stmt FROM @tables;
EXECUTE stmt;
DEALLOCATE PREPARE stmt;
SET FOREIGN_KEY_CHECKS = 1; 
```

#### Create EFMigrateHistory table at each databases:
```
CREATE TABLE `__EFMigrationsHistory` ( `MigrationId` nvarchar(150) NOT NULL, 
`ProductVersion` nvarchar(32) NOT NULL, 
PRIMARY KEY (`MigrationId`) );
```

### Migrate database:

<pre><code>dotnet ef database update --context AppIdentityDbContext</code></pre>
<pre><code>dotnet ef database update --context PersistedGrantDbContext</code></pre>


 

