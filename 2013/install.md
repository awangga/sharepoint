# Microsoft Share Point 2013 Installation

## Pre requisite

### Server Side
#### 3 tier Model
 1. Domain Controller server
	Windows Server 2012
 2. SQL Server
	Join Domain
	Create User
	* spSql
		SQL Server Database Engine and SQL Agent Service Account
	* spAdmin
		For SharePoint Setup and Configuration Wizard
			Domain User Account
			Local Administrator deployment server
			SQL Server login with securityadmin and dbcreator roles,public,sysadmin
	* spFarm
		Configure and manage server farm, application pool identity for central administration and run microsoft foundation workflow timer service
			Domain User Account
			SQL Server Login with securityadmin,dbcreator, and db_owner for sharepoint databases in server farm
		
	
 3. Share Point Server
	Join Domain
	Internet Connection

#### Join domain
Setting DNS to your Active Directory Server
 1. Go to System Properties
 2. klik Change...
 3. fill Computer Name and Member of Domain


#### Add spadmin account in your server
Right klik my computer > manage
open server manager>configuration>local users and Groups>Groups
Right clik Administrator>properties
klik add enter spadmin>check names > OK > OK
Close server Manager

#### Create DB user 
Open SQL Server Management Studio from start button.
Fill Server Type, SErver Name, Authentication>Windows Authentication>TEST01\Administrator>connect
open SQL Server>Security>logins and then right click on login>new login
Open New Windows click search>Location>entire directory>Domain01.local>ok
spadmin > check names > ok
klik Server Roles Page> tick dbcreator and securityadmin>ok

Right click SQL Server>Properties>Advanced page>Max Degree of Parallelism>1>ok

### Share Point Installation
Open file directori of installation, open splash.hta
Install SOftware Prerequisite

Open splash.hta again and select Install SharePOint Server
Select Complete for server type
thick the Sharepoint products configuration wizard now.
Next > Create A new Server Farm
Database Server : test01
Database Name : SharePoint_COnfig
Username : domain01\spFarm
Password : ***

Specify Port Number : 8181
Sec Setting  : NTLM
Next>Successful

open browser






