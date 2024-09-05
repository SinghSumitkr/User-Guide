Dynamic Database Connection String in Qlik Sense or QlikView
In QlikView or Qlik Sense, database connections can be made dynamic by creating a flexible connection string that switches between primary and secondary databases based on external inputs. This approach allows for easy management of database connections without the need to hard-code details into scripts.

Overview
The dynamic database connection setup involves the following steps:

Property File for Server Information: A single property file that contains all server-level information as plain text.
Generic Script File (.qvs File): A reusable script file that dynamically generates the connection string based on the property file.
External Control File: An external file that controls the switching of the connection between primary and secondary databases.
Step 1: Property File for Server Information
The first step involves creating a property file that contains all server-level information needed for the connections. This file is stored securely and is not accessible by anyone except Qlik Services. This file contains information such as:

Server Name
Port Number
Service Name
Schema Name
To add or modify a connection, you only need to update this file. All server details are tagged with unique identifiers to ensure easy identification.

Step 2: Generic Script File (.qvs File) for Dynamic Connection String
The connection string creation process is handled by a generic script file (.qvs file) that dynamically generates the connection string. The flow of connection string creation is as follows:

The .qvs file is included in the extract script of QlikView or Qlik Sense.
QlikView or Qlik Sense finds the file from a secured folder.
After finding the .qvs file, QlikView or Qlik Sense pulls the content written in that file into the load script.
Decoding the Connection Script in the .qvs File
Folder Path Variable: A variable (vFolderName) is created to store the folder name where the extract .qvw resides.

File Path Variable: A variable (vFilePath) is assigned the path of the external control file (Excel file) containing DB connection information. This file is kept in a shared location for easy access.

Application Properties File Path: Another variable (vAppPropertiesPath) is assigned the path of the app.properties file, which contains all server-level details.

Loading Server Information: All information from the app.properties file is loaded into the extract .qvw file:

All text before the equal sign is loaded under the field name Parameter.
All text after the equal sign is loaded under the field name Value.
Handling External File for Connection Switching:

The external file mentioned in the app.properties file is used to flip the connection between primary and secondary databases. This file contains the Folder Name and Connection information, which is loaded into QlikView.
The script ensures that only one record (relevant to the vFolderName) is loaded from the external file.
Comparing Connection Values:

The loaded value of the Connection field is compared with the primary and secondary DB names stored in variables (vPrimaryDB and vSecondaryDB).
Depending on the match, the appropriate DB server details (Server Name, Port Number, Service Name) are stored in variables (vDBServer, vDBPort, and vDBService).
Creating the Dynamic Connection String:

Once the required information is determined, a generic connection string is created dynamically using the stored variables:
plaintext
Copy code
OLEDB CONNECT TO ‘Provider=OraOLEDB.Oracle.1;Persist Security Info=False;User ID=[];Data Source=$(vDBServer):$(vDBPort)/$(vDBService);OSAuthent=1`;
Step 3: External Control File for Connection Switching
The external control file allows you to switch the connection between primary and secondary databases easily. By changing the value in this file, the connection string is flipped from one database to another.

The file is placed in a shared location for easy modification.
When the connection feed is set to Primary, the script will connect to the primary DB, and when set to Secondary, it connects to the secondary DB.
Important Notes
Different .qvs Files: Different .qvs files must be created to handle different connection strings.
Limitations: Only text before and after the equal sign in the app.properties file is used for the connection setup.
Security: The app.properties file is stored securely and not accessible to unauthorized users.
Conclusion
By following the steps outlined above, you can create dynamic database connection strings in Qlik Sense or QlikView and control the switching of connections between primary and secondary databases with ease.
