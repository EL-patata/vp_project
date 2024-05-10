# TodoList App

**TodoList App** is a desktop application that helps you organize your tasks and achieve your goals. With a simple and intuitive user interface, you can easily create, delete, search, and filter tasks by status, priority, or due date.

*TodoList App is built with **WPF**, a powerful framework for creating user interfaces with .NET. It uses data binding and **MVVM pattern** for separation of concerns, and **MS SQL Server** for data storage and retrieval.*


 
1. Create a databse `TodoList` with a `Tasks` table in MS SQL Server:
	```
	> CREATE DATABASE TodoList;

	> USE TodoList;

	> CREATE TABLE TASKS (
		Id INT IDENTITY(1,1) PRIMARY KEY,
		Content VARCHAR(MAX) NOT NULL,
		Priority CHAR(10) CHECK (Priority IN ('Priority 1', 'Priority 2', 'Priority 3', 'Priority 4')) NOT NULL,
		Date DATETIME DEFAULT SYSDATETIME()
	);
	```

2. Create an `App.config` in the root of the project and set the connection string of the database, e.g.
   ```
   <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
    	<connectionStrings>
    		<add name="TodoListDB" connectionString="Server=.\SQLEXPRESS;Database=TodoList;Integrated Security=True;" providerName="System.Data.SqlClient"/>
    	</connectionStrings>
    </configuration>
   ```

3. Run the application:
    ```
    # Install dependencies
  	dotnet restore
  
  	# Run the application
  	dotnet run
    ```
