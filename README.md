**This repository is tutorial created by [Spring.pleiades.io](https://spring.pleiades.io/guides/gs/accessing-data-mysql/).**

# accessing-data-mysql
## Development

Follow this guide to set up your environment etc.

## Install
1. Clone this repository
```bash
$ git clone https://github.com/kooooichi24/accessing-data-mysql.git
```

2. Go into the repository
```bash
$ cd accessing-data-mysql
```

## Usage
### Building a MySQL environment with docker
1. Installing a MySQL image from Docker-hub
```bash
$ docker pull mysql
```

2. Starting and creating containers from an installed image
```bash
$ docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d -p 3306:3306 mysql:latest
$ docker exec -it some-mysql bash
```

3. Login to the MySQL container
```bash
$ mysql -u root -p -h 127.0.0.1
```

### Database environment
1. Creates the new database

```bash
mysql> create database db_example; -- Creates the new database
```

2. Creates the user
```bash
mysql> create user 'springuser'@'%' identified by 'ThePassword'; -- Creates the user
```

3. Gives all privileges to the new user on the newly created database
```bash
mysql> grant all on db_example.* to 'springuser'@'%'; -- Gives all privileges to the new user on the newly created database
```

### Run
1. Running the application

```bash
./mvnw clean package
```

2. Testing the application

**POST Request**

The following curl command adds a user.
```bash
$ curl localhost:8080/demo/add -d name=First -d email=someemail@someemailprovider.com
```
The reply is as follows.
```bash
Saved
```

**GET Request**

The following command shows all users.
```bash
$ curl 'localhost:8080/demo/all'
```

The reply is as follows.
```bash
[{"id":1,"name":"First","email":"someemail@someemailprovider.com"}]
```
