A CRUD application is a type of application that consists of four basic operations: create, read, update, and delete. These applications usually consist of a database, user interface, and APIs.

The database, obviously, is where the data is stored. It is managed by a [[DBMS|database management system]]. The user interface is what users interact with, usually a GUI but sometimes a command line. Finally, APIs are how the application informs the database of the functions to perform.

The CRUD functions each allow a user to manipulate or view a database:

| Operation | SQL function | HTTP protocol | Description                                |
| --------- | ------------ | ------------- | ------------------------------------------ |
| Create    | Insert       | POST          | Add new records                       |
| Read      | Select       | GET           | Query the database and display the records |
| Update    | Update       | PUT           | Modify existing records            |
| Delete    | Delete       | DELETE        | Remove records from a table                                           |
