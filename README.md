## Compose sample application
### Java Spark application with MySQL database

Project structure:
```
.
├── backend
│   ├── Dockerfile
│   └── ...
├── db
│   └── password.txt
├── docker-compose.yaml
└── README.md

```

[_docker-compose.yaml_](docker-compose.yaml)
```
version: "3.7"
services:
  backend:
    build: backend
    ports:
    - 8080:8080
  db:
    image: mysql:8.0.19
    ...
```
The compose file defines an application with two services `backend` and `db`.
When deploying the application, docker-compose maps port 8080 of the backend service container to port 80 of the host as specified in the file.
Make sure port 8080 on the host is not already being in use.

