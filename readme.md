Contoso University - Microsoft ASP.NET Core 3
======

Prerequisites
------

* [Visual Studio Code](https://code.visualstudio.com/download)
* [C# for Visual Studio Code (latest version)](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)

Database engines
------

These instructions use [SQLite](https://www.sqlite.org/), a cross-platform database engine. You will need to download and install a third-party tool for managing and viewing a SQLite database such as [DB Browser for SQLite](https://sqlitebrowser.org/).

The App
------

The app is a basic university web site. Users can view and update student, course, and instructor information. Here are a few of the screens:

![Students Index page](https://docs.microsoft.com/en-us/aspnet/core/data/ef-rp/intro/_static/students-index30.png)

![Students Edit page](https://docs.microsoft.com/en-us/aspnet/core/data/ef-rp/intro/_static/student-edit30.png)

To run the app after downloading the project:

* At a command prompt in the project folder, run the following commands:

  ```.NET Core CLI
  dotnet build
  dotnet tool install --global dotnet-ef
  dotnet ef database update
  ```

* In your SQLite tool, run the following SQL statement against the database. The database file `CU.db` is in the root of theproject folder:

  ```SQL
  UPDATE Department SET RowVersion = randomblob(8)
  ```

* Run the project to seed the database and open the site in your default web browser using the keyboard shortcut `Ctrl+Shift+D`. Alternatively you can use the following command and navigate to the site address returned in the command output.

  ```.NET Core CLI
  dotnet run
  ```

* At any time you need to return the database to the default state, stop the app and run the following commands:

  ```powershell
  dotnet ef database drop
  dotnet ef database update
  ```

More information is available from the Microsoft ASP.NET Docs site at the [Razor Pages with Entity Framework Core in ASP.NET Core - Tutorial](https://docs.microsoft.com/en-us/aspnet/core/data/ef-rp/intro?view=aspnetcore-3.1&tabs=visual-studio).