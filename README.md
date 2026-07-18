# Azure-Container-App

STAGE ONE

1. FIRST STEP: Creation and configuration of the Container App Environment. choose subscription, create Resource group and name your App. Choose Region

![1st screenshot](Images/1.png)


2. SECOND STEP: Select container App Environment and create new. Choose container image

![2nd screenshot](Images/2.png)

3. THIRD STEP: Configure container Image Source, set it to Docker Hub and image type as public

![3rd Screenshot](Images/3.png)
![4th screenshot](Images/4.png)

4. FOURTH STEP: Alocate appropriate memory for the container

![5th screenshot](Images/5.png)

5. FIFTH STEP: Enable ingress and set port to 4173, and allow traffic from anywhere

![6th screenshot](Images/6.png)
![7th screenshot](Images/7.png)

6. SIXTH STEP: Review and deploy the container app

![8th screenshot](Images/8.png)
![8th screenshot](Images/9.png)

7. FINAL RESULT: You should see the container app details as the image  if deploymentment is successful

![8th screenshot](Images/10.png)


STAGE TWO

Configure PostgresSQL Database

STEP ONE: Navigate to Azure Database for postgreSQL Flexible servers, Create Resource.
create resource group and enter a server name. choose latest version of postgresSQL

For Workload, choose Dev/Test because the resources are low compared to production.

![screenshot1](Images/p1.png)
![screenshot2](Images/p2.png)

compute+storage, we can choose from the various option from compute tiers and compute size can also be increase
storage size can be increase up to 32TB depending on the type of workload being managed.
Storage type is set at premium SSD

![screenshot3](Images/p6.png)
![screenshot4](Images/p7.png)
![screenshot5](Images/p8.png)

Business critical - 99.9% SLA should be enable to ensure that database is highly available, but the version that is selected here does not allow thisoption because this for test purpose. for production purpose this should be avoided in case of disaster

![screenshot6](Images/p3.png)
![screenshot7](Images/p9.png)

BACKUPS - by default azure backs up all operation for 7 days, data can be backed up for maximum of 35 days. 

Geo reducdancy is enabled for data preservation and recovery in case of disaster

![screenshot8](Images/p9.png)

AUTHENTICATION
PostgresSQL Authentication is used to secure and allow access into the database. Here admin login password and username is set

![screenshot9](Images/p5.png)

NETWORKING

This determines the connectivity method, either private or public depending on who is to be allowed access. Firewalls rules is usually set for this on production 

![screenshot10](Images/p10.png)
![screenshot11](Images/p11.png)

SECURITY AND TAGS are left as default

![screenshot12](Images/p12.png)
![screenshot13](Images/p13.png)

REVIEW AND CREATE
The prompt is thrown up to indicate no one would be able to access the server without a specific address, however this can always be done anytime.

![screenshot14](Images/p14.png)

When deployment is successful this should be seen
![screenshot15](Images/p15.png)

STEP 4 : CREATE DATABASE demo_db

From overview section, go to settings and select Databases. the default database is PostgresSQL add a second database called demo_db.

![screenshot16](Images/db.png)

To get the connection stream from the database, go to Connect under the same settings and change the database parameters to demo_db that was created.
There are various connection options availble but in this task we chose 'connect from browser or locally' and copy the connection link 

![screenshot17](Images/db2.png)
![screenshot18](Images/db3.png)

Open cloud shell to access the terminal and past the link.
The ip address must be added to allow connectivity at this stage
Remember to provide azure password to be able to proceed

![screenshot19](Images/db4.png)
![screenshot20](Images/db5.png)

FINAL STEP: The information below will indicate a successful access into the demo_db, it shows the db version and other details.

![screenshot21](Images/db6.png)
