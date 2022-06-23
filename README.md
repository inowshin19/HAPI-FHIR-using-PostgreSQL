# HAPI-FHIR Starter Project

This project is a complete starter project you can use to deploy a FHIR server using HAPI FHIR JPA.

Note that this project is specifically intended for end users of the HAPI FHIR JPA server module (in other words, it helps you implement HAPI FHIR, it is not the source of the library itself). If you are looking for the main HAPI FHIR project, see here: https://github.com/hapifhir/hapi-fhir

Need Help? Please see: https://github.com/hapifhir/hapi-fhir/wiki/Getting-Help

You can find the Prerequisites and Configuartion details here: https://github.com/hapifhir/hapi-fhir-jpaserver-starter. In this project, I have customized the FHIR Server to meet my requirements. Things I worked with:

 - Configured the app to use PostgreSQL
 - It also contain volumes to persist data even if the container stops
 - Enabled email subscription
 - Set custom server URL


## Getting Started

- Clone the project https://github.com/inowshin19/HAPI-FHIR-using-PostgreSQL.git. 
- In 'docker-compose.yml' file, change '/Users/isratnowshin/Documents/hapi/src/main/resources/newapplication.yaml' to the path of newapplication.yaml in your local machine.
- Run the command:

```
docker compose up
```

## Testing the Database

1. Download DbVisualizer.
2. Create a Postgres Database with the port 5000, username: admin and password: admin.
3. Click Connect to check if the database connects. You can find table information:


PostgreSQL -> Databases -> hapi -> schemas -> public -> tables


You can see that there are tables without any data from HAPI FHIR. We will show how to add data in the next section.

## Testing the Server

1. Download Postman or any other API platform.
2. Use the GET method to see if: localhost:8080/fhir/metadata responses with 200 OK.
3. We will insert some information in the table 'hfj\_resource'.
4. Use the POST method to insert patient.json file into localhost:8080/fhir/Patient
5. The table 'hfj\_resource' will be updated and a new row will be created.
