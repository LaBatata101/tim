# T.I.M - Triangle Inventory Management

This project was made as an assignment for my Analysis and Systems Design class. The goal of this project was to make a simple and intuitive
inventory management system.

The project is separated in two parts:
- The [REST API](https://github.com/LaBatata101/tim-api) responsible for all the business logic and interaction with the database.
- And the simple-to-use [user interface](https://github.com/LaBatata101/tim-gui).

## How to Install
Clone the repository:
```bash
$ git clone https://github.com/LaBatata101/tim
```
### Install the dependencies for the backend and frontend
Installing the dependencies for the backend:
```bash
$ cd tim && cd tim-api
```
```bash
$ pip install -r requirements.txt
```
Additional dependency for the backend:
- postgresql >=14.3-3

Installing the dependencies for the frontend:
```bash
$ cd tim && cd tim-gui
```
```bash
$ pip install -r requirements.txt
```

## How to run
### Running the backend
Before starting the REST API we need to export a few enviroment variables for the database: `POSTGRES_USER`, `POSTGRES_PASSWORD`, `POSTGRES_SERVER`, `POSTGRES_DB`.
Here's an example on how to do that:
```bash
$ export POSTGRES_USER=test; export POSTGRES_PASSWORD=12345; export POSTGRES_SERVER=localhost; export POSTGRES_DB=tim
```
After that we need to initialize the database tables using [alembic](https://alembic.sqlalchemy.org/en/latest/), for that just run:
```bash
$ alembic upgrade e82387d4aa0d
$ alembic upgrade 8a1bc31142ab
```
Now we can start the REST API server using:
```bash
$ uvicorn tim.main:app --reload
```

### Running the frontend
