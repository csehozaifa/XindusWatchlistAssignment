# Xindus wishlist backend project
Welcome to the Xindus Assignment repository! This backend application manages wishlists in an e-commerce platform, utilizing Spring Boot, Spring Security with JWT authentication, and Spring Data JPA.
## Features
- his backend solution provides secure user authentication (signup and login) through Spring Security with JWT.
- It offers RESTful API endpoints for wishlist management, enabling users to create and delete wishlist items. 
- The application integrates seamlessly with a relational database using Spring Data JPA for storing user information and wishlist items.


### Prerequisites
- JDK version 17 or higher
- Maven

### Configuration
Step1:- Database Configuration:
- Open the src/main/resources/application.properties file.
- server.port=9094
- spring.datasource.url=jdbc:mysql://localhost:3306/WishListt?createTableIfNotExists=true
- spring.datasource.username=root
- spring.datasource.password=Moz@0786
- spring.jpa.hibernate.ddl-auto=update


Step2:- Spring Security Configuration:
- Customize security configurations, including JWT token expiration time and secret key, within the SecurityConfig.java file.

### Running the Application
1. Run the application using Maven:
- mvn spring-boot:run



### API Usage
1. Sign Up:
- Open Postman or any HTTP client application.
- Send a POST request to http://localhost:9094/auth-api/sign-up with JSON body containing user details:
  - {
    - "firstName": "firstname",
    - "lastName": "lastname",
    - "email": "email",
    - "password": "password"
  - }

2. Login:
- Send a POST request to http://localhost:9094/auth-api/login with JSON body containing user credentials:
  - {
    - "email": "email",
    - "password": "password"
   - }

#### Note: Save the JWT token received in the response.

3. Accessing Other APIs:

-Ensure authentication by incorporating the JWT token into the Authorization header of your requests:
-When using Postman, select the Authorization type as "Bearer Token" and insert the JWT token acquired during login.
-Employ the subsequent endpoints for additional API functionalities:
     - Wishlistproject Manage: http://localhost:9094/api-product-wishlist/wishlists
     - Products: http://localhost:9094/api-product-wishlist/products
