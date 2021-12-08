# dws-dev-004-database

### Description 

In this task we had to design a database schema for a microservice authentication service.

We considered three entities for this schema that I will explain them.

## Contents

- [General Info](#general-info)
- [Tables](#tables)
    - [users](#users)
    - [roles](#roles)
    - [role_user](#role_user)
    - [projects](#projects)
    - [project_user](#project_user)

    
### General Info

This database is designed based on DWS requirements and have the following conditions:

+ All tables are implemented in Mysql.

+ You can execute it with following command: mysql -u username -p password database < text_file.sql

### Tables

Here we explain the purpose of a table and its columns. It's important to mention that almost all tables have four
following fields excluded from tables unless specified.

+ **id**: the identifier of the table - exists in all tables.:
+ **updated_at**: the time a record being updated - exists in all tables.
+ **deleted_at**: the time a record being deleted - exists in all tables.

---

#### users

It holds information about users.

###### columns:

+ **first_name**: name of the user.
+ **last_name**: surname of the user.
+ **email**: email of the user that should be unique.
+ **username**: username of the user that should be unique.
+ **password**: the password the user should use to log into the application.
+ **status**: the status of the user. Available options are: `inactive`, `pending`, `active`.
+ **address**: address of the user.
+ **setting**: a `JSON` field used for storing user's data like `tour` status or other customized data.

---

#### roles

It holds information about roles.

###### columns:

+ **title**: title of the role.
+ **description**: description of the role.
+ **rules**: rules of the role, for example super_admin access level.
+ **is_active**: status of the role that is active or inactive.

---

#### projects

It holds information about projects.

###### columns:

+ **title**: title of the project.
+ **description**: description of the project.
+ **company_id**: the company that created this project.
+ **category_id**: category of this project for example export.
+ **is_active**: status of the project that is active or inactive.
+ **priority**: priority of the project.
+ **start_at**: What date has this project started which is timestamp.
+ **end_at**: What date has this project ended which is timestamp.

---

There are two other tables named role_user and project_user which are pivot tables between our tables.

---

#End


[@dwsclass](https://github.com/dwsclass) dws-dev-004-database