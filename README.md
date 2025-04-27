First things first

this is a basic Flask API CRUD with PostgreSQL and Docker

follow the next steps to make it wokr!

(just in case)
git clone

(ssh or https, it's on you!)

$ git clone https://github.com/PerlaGCastillo/rest.git $ cd rest
docker

(here i'm assuming that you already installed docker, if not please go to the (oficial documentation and follow it!)[https://docs.docker.com/engine/install/ubuntu/) )

$ docker compose up -d flask_db

$ docker ps -a

thus would be the result CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES c46521ab5825 postgres:12 "docker-entrypoint.s…" 19 seconds ago Created flask_db

###create a db connection like with dbeaver or whatever tool you prefer but just remember that this password is the worst idea and i'm using it for the example, please assure your data anc create an .env file to avoid expose your db

Host: localhost User: postgres Database: postgres

click on the Test button "Connected (291ms)" if it works you're almost done! click the Connect btn

###build the docker compose image $ docker compose build

$ docker compose up flask_app $ docker ps -a

message "test route" into localhost:4000/test
endpoints postman test

GET localhost:4000/users SEND btn clicked

json response:

{ "users": [] }

POST localhost:4000/users SEND btn clicked

BODY RAW

{ "username":"Per", "email":"myemail@support.com" }

====

RESPONSE

{ "message": "user created" }

====

$ docker ps -a CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES 910ad22bd742 x/rest:1.0.0 "flask run --host=0.…" 15 minutes ago Up 15 minutes 0.0.0.0:4000->4000/tcp, [::]:4000->4000/tcp flask_app eddb7b097bad postgres:12 "docker-entrypoint.s…" 15 minutes ago Up 15 minutes 0.0.0.0:5432->5432/tcp, [::]:5432->5432/tcp flask_db
