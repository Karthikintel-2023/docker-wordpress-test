# docker-wordpress-test

***************************************************************
# STEPS TO FOLLOW
***************************************************************


# Create your project directory then go into it:

mkdir -p <DockerWordpress>
go to the above created directory and execute the below mentioned command

# Download the Docker Compose template:
git clone https://github.com/Karthikintel-2023/docker-wordpress-test.git

# New Project
- Run the command `bin/freshWp` and enter the following things:
- Enter your WordPress site name (e.g., mysite): <demo-site-name>
- Enter your WordPress admin username: <admin-name>
- Enter your WordPress admin password: <admin-password>
- Enter your WordPress admin email: <admin-email>
- Please specify a domain name (ex. example.com): <domain-used-local>
- Is this a fresh WordPress installation? (y/n): y

# Existing Project :
- Create the `app` folder take the exisitng project setup into the `app` folder
- If the project has the git setup 
    - git clone <project-repo-url> app
if the project is setup on any-other branch then change to the updated branch and  proceed

After perfoming all the steps please execute the below command :
 -  docker-compose up or docker-compose up --build
 

# After setup done update the url by the following command: 
- bin/setup-domain guswp.local
- `bin/setup-domain <domain-used-local>`

# For Importing the exisiting database :
The Below command is used for importing the db
 - docker-local-wp_mysql_1 - Container name for Mysql. You can use `docker ps`.
 - main_databse -- Database name 
 - ./backups/main_database-20240321-164048.sql -- Location for the backup file.
 - mainRoot@123 --- main root password 
    
- `bin/importDb docker-local-wp_mysql_1 main_databse ./backups/main_database-20240321-164048.sql mainRoot@123`

# For Exporting the exisiting database :
The Below command is used for Exporting the db
 - docker-local-wp_mysql_1 - Container name for Mysql. You can use `docker ps`.
 - main_databse -- Database name 
    
- `bin/exportDb docker-local-wp_mysql_1 main_database`

# For Starting and Stoping the Docker Container
- Start the Current Containter `bin/start`
- Stop the Current Containers `bin/stop`