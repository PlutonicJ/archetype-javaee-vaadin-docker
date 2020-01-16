This project includes a setup with docker for a database and a web application with Vaadin 14.1.
An overview route and a detail route is already implemented.

An image of Payara is used to create a new image, which includes the created WAR-File (`mvn install`).
Calling `docker build -t test:latest .` creates the new image, and can be executed with `docker run -p 127.0.0.1:8080:8080 test:latest`.
After the start of Payara the application can be opened in a browser at http:localhost:8080/test/car.

A container with the application on Payara and a container with PostgreSQL can be executed by calling `docker-compose up -d --build`.
To reset the database, you have to determine the name of the volume with `docker volume ls` and then delete it with `docker volume rm <volume name>`.
With the next start of the container the volume is recreated and the SQL scripts are executed.