# MSSQL Security Queries

This repository contains the config of Elimity's SQL gateway to query the user access to one or multiple MSSQL databases and/or instances.

The import employs the following data model:

![import data model](/img/sql-server-datamodel.png)

Key points to note:
* **Databases vs. Instances:** A database is a logical entity, and multiple databases can exist within a single **instance** (SQL Server).
* **Permission Levels:** Permissions are managed at two levels: the individual **database level** and the entire **instance level**.
* **Inheritance:** Permissions granted at the instance level apply to all databases within that instance. Because of this, we have linked the instance to all of its constituent databases.
* **Users vs. Logins:** **Users** are accounts defined at the database level, whereas **Logins** are accounts defined at the instance level. Database users can be created for a login, in which case the authentication goes through the login and authorization on database level is granted to the user.