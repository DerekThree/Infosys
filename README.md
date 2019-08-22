# Infosys

"Golden Copy Creation and Access" project made for Infosys

Requirements: MySQL Server 8.0.16
              MySQl Enterprise Backup 8.0.16
              Windows 10
              
Contents: IntelliJ project with the software
          Login.html
          PowerPoint presentation
          
The program consists of UI, controller, utilities, DBMS.
It creates a golden copy of a database and manages user's access to it.

-------------------------------------------------------------------------
UI

Login.html
Login page takes an existing user name and password and logs the user
into installed MySQL Server 8.0.16

Admit.html
Admin dashboard allows for creation and deletion of user accounts,
giving a user permissions to acces a database (by providing him with a GC),
and listing databases the user already has an access to.

User.html
User dashboard lists databases the user has access to.
Other featuers are not working yet.

--------------------------------------------------------------------------
Controller

Saved as an IntelliJ project. Creates a Spring Boot server which maps
GET and POST requests from the UI websites. Most of the code is in
GoldenAPI class and some of it is not finished yet.
Assumes that MySQL Enterprise Backup 8.0.16 is installed and has room
for msqldump expansion. Msqldump will be used by share() and save() methods
when creating a copy of a database under a different name (This feature will
be used to manage ownership and version encoding, instead of originally
planned folder structure encoding).

--------------------------------------------------------------------------
Utilities and DBMS

Program assumes that MySQL Enterprise Backu is installed and its version
matches MySQL Server version.

-------------------------------------------------------------------------
Future Development

Golden copy is created on local machine but this feature can be expanded
to creation on remote severs ussing SSH protocol. Useful examples can be
found in MySQL Enterprise Backup documentation.
Some of the methods in GoldenAPI class need to be written or modified.
Program operates only on file level, without block level functionality.
