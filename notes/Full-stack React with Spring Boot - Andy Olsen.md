# Full-stack React with Spring Boot - Andy Olsen

### Lesson 1: Setting the Scene
#### 1.1 Overview of Full-Stack Applications
- Overview
    - Typical technologies on 
        - ![](img/01001.jpg)
            - web ui
                - HTML / CSS / JS / framework(ie. React)
            - REST service
                - standard and open communication protocol
            - Web Server
                - logic for the service
                    - Spring Boot / ASP.NET / Python / Node.js
            - Persistence
                - Persist data
                    - Relational database
                        - MySQL
                    - NoSQL database
                        - MongoDB
                    - Cloud database
                        - AWS S3
                    - Mainframe storage
                        - IBM Z
        - ![](img/01002.jpg)
            - Web UI
                - React
            - WebApp
                - Spring Boot
            - Persistence
                - H2
                    - for in-memory storage

#### 1.2 Understanding REST Services
- Definition of REST
    - ![](img/01003.jpg)
        - user interacts with a website
        - website needs to change state
        - website react with new state after user interacts
    - ![](img/01004.jpg)
        - ![](img/01005.jpg)
            - HTTP actions
                - GET, POST, PUT, DELETE
                - ![](img/01006.jpg)
            - ![](img/01007.jpg)
            - ![](img/01008.jpg)
        - ![](img/01009.jpg)
            - Parts of the HTTP response
                - location - lets you know where change was made
                - ![](img/01010.jpg)
            - Status Codes
                - ![](img/01011.jpg)

#### 1.3 Creating Client-side Content
- ![](img/01012.jpg)
    - Frontend that will communicate with backend VIA rest
- HTML
    - ![](img/01013.jpg)
- CSS
    - ![](img/01014.jpg)
- Javascript
    - ![](img/01015.jpg)
        - ![](img/01016.jpg)
        - ![](img/01017.jpg)
        - ![](img/01018.jpg)

### Lesson 2: Creating and Running Spring Boot Applications
#### 2.1 Creating a Simple Application Using Spring Boot CLI
- Getting Started
    - ![](img/01019.jpg)
- Creating a spring boot app
    - ![](img/02001.jpg)
- Maven project
    - ![](img/02002.jpg)
        - `pom.xml` manifest of all dependencies
            - ![](img/02005.jpg)
            - ![](img/02006.jpg)
                - Parent for common dependencies
    - ![](img/02003.jpg)
        - `src` holds all the application 
            - ![](img/02007.jpg)
            - ![](img/02008.jpg)
            - 
    - ![](img/02004.jpg)
- To run...
    - ![](img/02009.jpg)

#### 2.2 Creating a Web Application Using Spring Boot CLI
- Getting Started
    - ![](img/02010.jpg)
        - ![](img/02011.jpg)
    - create a maven dependency web app (dweb)
        - ![](img/02012.jpg) 
            - ![](img/02013.jpg)
    - Maven web project includes `static` and `template`
        - ![](img/02014.jpg)
    - static files go into static folder
        - ![](img/02015.jpg)
    - Run the app after filling up static folder
        - ![](img/02016.jpg)
    - Test
        - ![](img/02017.jpg)

#### 2.3 Creating a Web Application Using IntelliJ
- Static Web App
    - new project
        - ![](img/02018.jpg)
            - ![](img/02021.jpg)
    - select spring initializer
        - ![](img/02019.jpg)
    - artifact is the project name
        - ![](img/02020.jpg)
    - observe created project
        - ![](img/02022.jpg)
        - ![](img/02023.jpg)
            - ![](img/02024.jpg)
    - build --> run
        - ![](img/02025.jpg)

#### 2.4 Implementing a Simple REST Service
- Overview
    - ![](img/02026.jpg)
        - 
    - ![](img/02027.jpg)
        - ![](img/02028.jpg)
        - ![](img/02029.jpg)

#### 2.5 Understanding Application Properties
- OVerview
    - ![](img/02030.jpg)
        - ![](img/02031.jpg)
    - 
        - 
- 
    - 
        - 
    - 
        - 


### Lesson 3: Spring Boot Components and Beans
#### 3.1 Defining Component Classes and Accessing Beans
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 

#### 3.2 Understanding Bean Scope and Initialization
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 

#### 3.3 Autowiring
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 

#### 3.4 Using Spring Expression Language (SpEL)
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 

#### 3.5 Working with Command-Line Arguments
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 

### Lesson 4: Configuration Classes
#### 4.1 Defining a Configuration Class and Beans
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 4.2 Locating Configuration Classes and Bean Methods
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 4.3 Configuration Techniques
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 4.4 Configuring Bean Dependencies
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
### Lesson 5: Spring Boot Techniques
#### 5.1 Setting Application Properties at the Command Line
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 5.2 Specifying which Properties File to Use
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 5.3 Defining YAML Properties Files
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 5.4 Using Spring Profiles
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 5.5 Using Spring Boot Actuator
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
### Lesson 6: Integrating with Data Sources
#### 6.1 Understanding Spring Data
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 6.2 Getting Started with JPA
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 6.3 Configuring JPA in Spring Boot
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 6.4 Defining JPA Entity Classes
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 6.5 Seeding the Database with Sample Data
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 6.6 Viewing Database Data
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 6.7 Introducing the EntityManager Class
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 6.8 Using Query Methods in the EntityManager Class
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 6.9 Modifying Entities
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
### Lesson 7: Working with Spring Data Repositories
#### 7.1 Understanding Spring Data Repositories
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 7.2 Defining a Spring Data Repository Interface
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 7.3 Using a Spring Data Repository Interface  
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 7.4 Getting Started with MongoDB   
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 7.5 Working with Collections in MongoDB
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 7.6 Defining a MongoDB Data Layer in Spring Boot
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 7.7 Using a MongoDB Data Layer in Spring Boot
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
### Lesson 8: Implementing and Consuming REST Services
#### 8.1 Getting Started with REST Services in Spring Boot
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 8.2 Defining a Simple REST Service
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 8.3 Defining a Full REST API
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 8.4 Implementing POST, PUT, and DELETE Endpoints
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 8.5 Defining a REST Client
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 8.6 Consuming REST Endpoints
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
### Lesson 9: Creating a React Front-End
#### 9.1 Creating a Simple React Web App
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 9.2 Defining Components
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 9.3 Creating an Industrial-Strength React Application
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 9.4 Building and Running an Industrial-Strength React Application
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 9.5 A Closer Look at Components
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 9.6 Passing Multiple Properties into a Component
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
### Lesson 10: Consuming a REST API from React
#### 10.1 Implementing a Data Model in a Server Application
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 10.2 Implementing a REST API in a Server Application
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 10.3 Getting Started with a React REST Client Application
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 10.4 Calling a REST Service
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 10.5 Using the async and await Keywords
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
### Lesson 11: Implementing a Compelling UI in React
#### 11.1 Introducing the Example Application
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 11.2 Implementing Routing
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 11.3 Displaying All Destinations
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 11.4 Displaying One Destination
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 
#### 11.5 Displaying and Adding Reviews for a Destination
- 
    - 
        - 
    - 
        - 
- 
    - 
        - 
    - 
        - 