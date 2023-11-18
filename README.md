# PA2577_UserData_RESTAPI_MicroServices
Python CRUD REST API Applcation using 
  - Flask (Python web framework)
  - SQLAlchemy (ORM)
  - Postgres (database)
  - Docker (containerization)
  - Docker Compose (to run the application and the database in containers)

Other supported applications to be installed are
- Postman : To perform CRUD Operations
- TablePlus: Authentification to database

## Procedure to build an application
- Create a Flask application using SQLALchemy as an ORM.
- Dockerize the Flask application writing a Dockerfile and a docker-compose.yml file to run the application and the database
- Run the Postgres database in a container using Docker Compose, and test it with TablePlus
- Run the Flask application in a container using Docker Compose, and test it with Postman

## Application Endpoints - 
- Test: just a test route
- ```POST``` a user: create a user with a username and an email
- ```GET``` all users: get all the users in the database
- ```GET``` one user: get one user by id
- ```PUT``` one user: update one user by id
- ```DELETE``` one user: delete one user by id

## Procedure
- Create Python Virtual Environment - ```$python -m venv venv```
- Activate virtual environment - ```$.\venv\Scripts\activate```
- Run python packages - ```$pip install -r .\MicroService\requirements.txt```
- Run the Postgres container - ```docker compose up -d flask_db```
- Show running containers - ```docker ps -a```
- Open TablePlus and Login to postgress database
  - Host: ```localhost```
  - Port: ```5432```
  - User: ```postgres```
  - Password: ```postgres```
  - Database: ```postgres```
- Hit "Test" (at the bottom-right) and Connect
- Build Flask Application - ```docker compose build```
- Run Flask Application - ```docker compose up flask_app```
- Test an application - ```localhost:4000/test``` then should a message: ```{'message': 'test route'}```
- Create a user - 
