# To-do List web application using Hibernate and Tomcat

## Overview
This exercise uses a web application that allows a user to create, update, and delete to-do items that are stored to and retrieved from a MySQL database.

## What does this program do?
The program is a web application using Tomcat, which allows the user to view, add, edit, and delete to-do items. The to-do items are saved to a MySQL database.

## System requirements
The application uses version 11 of Amazon's distribution of the Open Java Development Kit (OpenJDK) [Corretto 11](https://aws.amazon.com/corretto/), Tomcat for deployment, and Hibernate and persistence to perform JDBC operations on a MySQL database.

## Database connection defaults
The program assumes that a database named `module_07_db` exists in the local MySQL database and a user with all database privileges exists with username/password: `module07user`/`module07pass`. It also assumes that it will connect to localhost using default port 3306. 

The user may change these initial configuration options by editing lines 16, 20, and 24 in the hibernate configuration file: 

```
/src/model/hibernate.cfg.xml

16    jdbc:mysql://localhost:3306/module_07_db?serverTimezone=America/New_York
...
20    module07user
...
24    module07pass
```

## How to use this program.
The web application opens to a list of all to-do items in the database. The user may add, edit, or delete new items. The web application will run until the user stops the Tomcat server within the IDE. Closing the browser window will not stop the application.

## Installation.
Clone the repo and import it into Eclipse IDE. Make sure that:
 1. The project SDK is Java 8 with project language level 8, and
 2. Hibernate and the Oracle [JDBC Driver](https://dev.mysql.com/downloads/connector/j/) for MySQL are installed in your system.
 3. The latest version of Tomcat is installed in your system.

## Known Issues
This application was developed using Eclipse IDE. When generating the WAR exploded artifact for deployment, not all dependencies were included by the IDE. There are two ways to solve this issue. The first requires copying the required dependencies to the Tomcat/lib folder. The second relies on adding the required dependencies to the WEB-INF/lib folder. I prefer the second option, as the dependencies will stay with the project as opposed to having them in folders outside the project structure, limiting its portability. Files located in lib folders are not typically included in version control systems, but I have included the required jars in this repo, nonetheless. 
