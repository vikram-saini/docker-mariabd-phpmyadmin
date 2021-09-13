# MariadDB with 10.3 and PhpMyAdmin
This is the MariaDB 10.3 Docker Container which contains PhpMyAdmin for MariaDB management.

- MySQL is running on port 3306
- PhpMyAdmin is running on port 8080

# Requirement
- Make sure that the latest version of Docker Desktop is installed
- Install any updates if you already have Docker Desktop installed
- Port 3306 and 8080 are available for use

# Environment File
The configuration for the container can be found insite the `.env` file inside the mariadb folder.
The configuration values can be altered based on your development environment.

| Variable | Notes | Windows | UNIX |
| ------ | ------ | ------ | ------ |
| MYSQL_DATA_DIR | Directory to store MySQL data locally | C:\\mysql\\data | /var/mysql/data |
| MYSQL_LOGS_DIR | Directory to store MySQL logs locally | C:\\mysql\\logs | /var/mysql/logs |
| DB_NAME | Creates a custom database with the name | demodb | demodb |
| DB_USER | Creates a user with the username | demouser | demouser |
| DB_PW | Set the password for the above username  | demopassword | demopassword |
| DB_ROOT_PW | Set the root password | password | password |

# Building Your Container
After you've configured the `.env` file, navigate to the `mariadb` folder in your terminal. You will now need to build your image using:
```
docker-compose build
```
Start your container once the image is built. We use the `-d` option to run the container detached from your terminal
```
docker-compose up -d
```
PhpMyAdmin can now be accessed from:
```
http://localhost:8080
```
If you have not changed the `DB_ROOT_PW` in the `.env` file, your login details should be:

| Input | Value |
| ------ | ------ |
| Server | Leave this empty |
| Username | root |
| Password | password |

## License
GPL-3.0 License

**Free Software, Hell Yeah!**