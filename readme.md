# API Integration Example with Keycloak 

> Change application.properties info with current kc installation
> To get Client secret, set it to "confidential", then copy it from the Credentials tab
> The kyecloak.certs-id is the realm key. To get it, go to Realm Settings -> Keys -> Line from table: RS256 RSA, provider "rsa-generated" 


Curls example:

### LOGIN CURL ###
curl --location --request POST 'http://localhost:8082/login' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'username=edwin' \
--data-urlencode 'password=admin'

## TEACHER CURL - GETS ROLES FROM TOKEN ##
curl --location --request GET 'http://localhost:8082/teacher' \
--header 'Authorization:  Bearer <login-token>'

## STUDENT CURL - GETS ROLES FROM ANOTHER CALL TO KC ##
curl --location --request GET 'http://localhost:8082/student' \
--header 'Authorization:  Bearer <login-token>'




Connecting between Java Application with Keycloak for Authentication and Authorization example. 

 ## Tools
 - Java 11
 - Spring Boot
 - Keycloak 4.8.3
 
 ## Keycloak API
 - Login API
 - Logout API
 - User Info API
 - JWK Certs API
 
 ## Application API
 ```
http://localhost:8082/login
http://localhost:8082/logout
http://localhost:8082/student
http://localhost:8082/teacher
http://localhost:8082/valid
```
