# SSO Identity

## Development Environment
- Visual Studio Code
- IdentityServer4
- SQL Server

## Setup

#### To run the demo:

**1.** Clone/Fork this repository.

**2.** Create the database on your SQL Server by using the dotnet cli to run the migrations from within the command:

<pre><code>dotnet ef database update --context AppIdentityDbContext</code></pre>
<pre><code>dotnet ef database update --context PersistedGrantDbContext</code></pre>


 

