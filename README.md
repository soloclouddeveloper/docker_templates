docker_templates
===============

## Eclipse-Temurin JDK21 / Alpine 3.41 / SQLite 3
**2025-02-22**

Have SQLite available for Java projects

---

Docker templates for different programming languages

## Angular
Move Dockerfile, docker-compose.yml and .dockerignore into top level Angular 
app directory (my_angular_app/ and not my_angular_app/src)

Make the following changes in `package.json` 

```json
"scripts": {
   ...
   "start": "ng serve --host 0.0.0.0",
   ...
 }
 ```

Ref answer by Hans Kilian on S.O.:
https://stackoverflow.com/questions/74467776/problem-connecting-to-angular-app-in-docker    

Ref Docker / Angular live-reload ...
https://www.freecodecamp.org/news/how-to-enable-live-reload-on-docker-based-applications/   

```bash
docker volume create nodemodules
docker build -t MY_IMAGE_NAME
docker run --name app -p 4200:4200 -v nodemodules:/src/node_modules  -v .:/src  MY_IMAGE_NAME
```
----

## Python

For the local version of docker compose, the environment variables 
shown are required if the app needs to use GCP client libraries.

For production, there may be additional permissions that are required to run
the application on GCP.


## Docker / Docker Compose Notes

### Start via Docker compose

```bash
docker compose up
```

and to shut down

```bash
docker compose down
```

### Build 

```bash
docker build -t <TAG_NAME> -f <DOCKERFILE_NAME> .
```

```bash
docker compose -f <DOCKER_COMPOSE_FILENAME> {up | down}
```