<!-- section start -->

<!-- attr: {id: 'title', class: 'slide-title', hasScriptWrapper: true} -->

# Transact SQL
##  Creating Stored Procedures, Functions and Triggers
<div class="signature">
    <p class="signature-course">Databases</p>
    <p class="signature-initiative">Telerik Software Academy</p>
    <a href="http://academy.telerik.com" class="signature-link">http://academy.telerik.com</a>
</div>

<!-- section start -->
<!-- attr: {id: 'table-of-contents'} -->
# Table of Contents
*   Transact-SQL Programming Language
	*	Data Definition Language
	*	Data Control Language
	*	Data Manipulation Language
	*	Syntax Elements
*	Stored Procedures
	*	Introduction To Stored Procedures
	*	Using Stored Procedures
	*	Stored Procedures with Parameters

 # Table of Contents
*	Triggers
	*	After Triggers
	*	Instead Of Triggers
*	User-Defined Functions
	*	Scalar User-Defined Functions
	*	Multi-Statement Table-Valued Functions
	*	Inline Table-Valued Functions
*	Database Cursors

<!-- section start -->
<!-- attr: {id: 'transact-sql-intro', class: 'slide-section'} -->
# Transact-SQL Language
## Introduction

# What is Transact-SQL
*	`Transact-SQL` (`T-SQL`) is database manipulation language, an extension to SQL
	*	Supported by Microsoft SQL Server and Sybase
	*	Used for stored procedures, functions, triggers
*	Transact-SQL extends SQL with few additional features:
	*	Local variables
	*	Control flow constructs (ifs, loops, etc.)
	*	Functions for strings, dates, math, etc.

# Types of T-SQL Statements
*	There are 3 types of statements in the Transact-SQL (T-SQL) language:
	*	Data Definition Language (DDL) Statements 
	*	Data Control Language (DCL) Statements
	*	Data Manipulation Language (DML) Statements

# Data Definition Language (DDL)
*	Used to create, change and delete database objects (tables and others)
	*	`CREATE &lt;object> &lt;definition>`
	*	`ALTER &lt;object> &lt;command>`
	*	`DROP &lt;object>`
*	The `&lt;object>` can be a table, view, stored procedure, function, etc.
	*	Some DDL commands require specific permissions

# Data Control Language (DCL)
*	Used to set / change permissions
	*	`GRANT` – grants permissions
	*	`DENY` – denies permissions
	*	`REVOKE` – cancels the granted or denied permissions

```sql
USE Northwind
GRANT SELECT ON Products TO Public
GO
```

*	As with DDL statements you must have the proper permissions

# Data Manipulation Language (DML)
*	Used to retrieve and modify table data
	*	`SELECT` – query table data
	*	`INSERT` – insert new records
	*	`UPDATE` – modify existing table data (records)
	*	`DELETE` – delete table data (records)

```sql
USE Northwind

SELECT CategoryId, ProductName, ProductId, UnitPrice 
FROM Products
WHERE UnitPrice BETWEEN 10 and 20
ORDER BY ProductName
```

# T-SQL Syntax Elements
*	Batch Directives
*	Identifiers
*	Data Types
*	Variables
*	System Functions
*	Operators
*	Expressions
*	Control-of-Flow Language Elements

# Batch Directives
*	`USE &lt;database>`
	*	Switch the active database
*	`GO`
	*	Separates batches (sequences of commands)
*	`EXEC(<command>)`
	*	Executes a user-defined or system function stored procedure, or an extended stored procedure
	*	Can supply parameters to be passed as input
	*	Can execute SQL command given as string

# Batch Directives – Examples

```sql
EXEC sp_who – this will show all active users
```
```sql
USE TelerikAcademy
GO
DECLARE @table VARCHAR(50) = 'Projects'
SELECT 'The table is: ' + @table
DECLARE @query VARCHAR(50) = 'SELECT * FROM ' + @table;
EXEC(@query)
GO
-- The following will cause an error because
-- @table is defined in different batch
SELECT 'The table is: ' + @table
```

# Identifiers
*	Identifiers in SQL Server (e.g. table names)
	*	Alphabetical character + sequence of letters, numerals and symbols, e.g. `FirstName`
	*	Identifiers starting with symbols are special
*	Delimited identifiers
	*	Used when names use reserved words or contain embedded spaces and other characters
	*	Enclose in brackets (`[ ]`) or quotation marks (`" "`)
	*	E.g. `[First Name]`, `[INT]`, `"First + Last"`

# Good Naming Practices
*	Keep names short but meaningful
*	Use clear and simple naming conventions
*	Use a prefix that distinguishes types of object
	*	Views – `V_AllUsers`, `V_CustomersInBulgaria`
	*	Stored procedures – `usp_FindUsersByTown(…)`
*	Keep object names and user names unique
	*	Example of naming collision:
		*	`Sales` as table name
		*	`sales` as database role

# Variables
*	Variables are defined by `DECLARE @` statement
	*	Always prefixed by `@`, e.g. `@EmpID`
*	Assigned by `SET` or `SELECT @` statement
*	Variables have local scope (until `GO` is executed)

```sql
DECLARE @EmpID varchar(11),
  @LastName char(20)
SET @LastName = 'King'
SELECT @EmpID = EmployeeId 
 FROM Employees
 WHERE LastName = @LastName
SELECT @EmpID AS EmployeeID 
GO
```

# Data Types in SQL Server
*	Numbers, e.g. `int`
*	Dates, e.g. `datatime`
*	Characters, e.g. `varchar`
*	Binary, e.g. `image`
*	Unique Identifiers (GUID)
*	Unspecified type – `sql_variant`
*	Table – set of data records
*	Cursor – iterator over record sets
*	User-defined types












	

<!-- section start -->
<!-- attr: {id: '', class: 'slide-section'} -->
# 
## 

<!-- section start -->
<!-- attr: {id: '', class: 'slide-section'} -->
# 
## 

<!-- section start -->
<!-- attr: {id: '', class: 'slide-section'} -->
# 
## 

<!-- section start -->
<!-- attr: {id: '', class: 'slide-section'} -->
# 
## 

<!-- section start -->
<!-- attr: {id: 'questions', class: 'slide-section'} -->
# Questions
## Databases
