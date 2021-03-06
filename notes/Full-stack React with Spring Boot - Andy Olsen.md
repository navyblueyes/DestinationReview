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
    - it will autocomplete the property names and show the default values
        - ![](img/02032.jpg)
            - don't change it if you like the default value
- Testing
    - ![](img/02033.jpg)

### Lesson 3: Spring Boot Components and Beans
#### 3.1 Defining Component Classes and Accessing Beans
- Basics
    - ![](img/03001.jpg)
        - Class component
            - automatically creates an instance
        - bean
            - an instance
- Components
    - ![](img/03002.jpg)
        - `@Component`
            - used to designate classes that we want an instance of
        - `@Service`
            - used to designate classes that we want an business instance of
        - `@Respository`
            - used to designate classes that we want to have data access
        - `@Controller`
            - used to designate classes that we want to respond to HTTP req/res
        - `@RESTController`
            - used to designate classes that we want to respond to HTTP req/res
- Demo
    - ![](img/03004.jpg)
        - ![](img/03003.jpg)
            - component will create a bean/instance with a name in a lower case
            - `MyComponent` component will create a bean/instance with the name `mycomponent`
    - ![](img/03005.jpg)
        - ![](img/03006.jpg)
            - when this runs... beans are stored in the application context
    - ![](img/03007.jpg)
        - ![](img/03008.jpg)
            - created a reference within main class of the Application...
                - that references the get function of the `ctx` of the running `Application.class`
                    - and gets the `mycomponent` bean of the `MyComponent.class`
    - ![](img/03009.jpg)
        - ![](img/03010.jpg)
            - ![](img/03011.jpg)
            - ![](img/03012.jpg)

#### 3.2 Understanding Bean Scope and Initialization
- Basics
    - Prototype vs Singleton
        - Prototype creates a separate instance with every invocation
        - Single creates only once instance and checks for that instance with every invocation
    - Default
        - singleton
            - ![](img/03013.jpg)
- Singleton-Scope Bean
    - ![](img/03014.jpg)
        - ![](img/03015.jpg)
            - suppose to store the instance value `id` and `printf()` it
            - if another instance is created... `nextId++` should be triggered giving the next instance a new `id`
        - ![](img/03016.jpg)
            - within the `Application.main` class, we call `demoSingleton` with the context of `SpringApplication.run(Application.class)`
            - inside of `demoSingleton` .. we attempt to run `ctx` with `getBean()` three times
        - ![](img/03017.jpg)
    - If you have a tedious bean to generate (20min+)...
        - lazy initiation
            - Purpose
                - Bean generation (unless specified) will always occur during `SpringApplication.run()`
                - if you want to avoid a long application startup and can spare the guilty bean...
                    - you can generate bean later ... aka... lazy load it with `@Lazy`
                        - will be generate ONLY when called
            - implementation
                - ![](img/03018.jpg)
                - ![](img/03019.jpg)
- Different Scope
    - ![](img/03020.jpg)
        - dictate where the data of bean is stored...
            - `"request"` will store data only during request and will be dumped after successful transmission
            - `"session"` storing data only during allotted user time, 
                - banks may limit it to 30 minutes and sign you out
            - `"application"` stores data during the lifetime of webapp
                - if it is restarted... loses that data
- Prototype Bean
    - Application
        - ![](img/03021.jpg)
    - Prototype Class
        - ![](img/03023.jpg)
            - ![](img/03022.jpg)

#### 3.3 Autowiring
- Overview
    - Will setup a dependency between service and repository
        - ![](img/03024.jpg)
    - Will need to qualify the dependency so that the Repo knows where to store data
        - ![](img/03025.jpg)
- Code Breakdown
    - BankRepository
        - ![](img/03028.jpg)
            - `BankRepositoryImpl` implements `BankRepository`, creating a single instance with `@Repository`
            - Interface consist of `createAccount()`, `getBalance()`, `updateBalance()`, and `deleteAccount()`
    - BankService
        - ![](img/03029.jpg)
            - Interface consist of `depositIntoAccount()`, `withdrawFromAccount()`, `transferFunds()`
            - `BankServiceImpl` implements `BankService`, creating a single instance with `@Service`
    - `@Autowired`
        - stored within `BankServiceImpl`
        - connects with `BankRepositoryImpl` bean
- Injecting Dependencies into Fields
    - ![](img/03030.jpg)
        - if you need a bean to run and draw info from (dependency)...
            - `@Autowired` that needed bean within
        - ![](img/03033.jpg)
- Injecting Dependencies into a Constructor
    - ![](img/03031.jpg)
        - ![](img/03032.jpg)
- Qualifying Autowiring
    - ![](img/03026.jpg)
        - ![](img/03034.jpg)
- Optional Autowiring
    - Avoid runtime error by making the maybe-not-there repo optional
        - ![](img/03027.jpg)

#### 3.4 Additional Autowiring Techniques
- If you want a `collection` of repository (ie. a collection of PostgreSQL, MySQL, Oracle)
    - ![](img/03036.jpg)
- If you have a `map` of repository
    - ![](img/03037.jpg)
- If you want to inject the value of a variable, i.e. value of `name`
    - ![](img/03038.jpg)
- If you want to inject the value of a Spring Expression Language   `"#{value}"`
    - ![](img/03039.jpg)

#### 3.5 Using Spring Expression Language (SpEL)
- Basic
    - ![](img/03040.jpg)
- Creating an object
    - ![](img/03041.jpg)
- Calling a static method 
    - Basic of static method
        - method that belongs to a class rather than an instance of a class
        - not part of the objects it creates but is part of a class definition
        - referenced by the class name and can be invoked without creating an object of class
    - ![](img/03042.jpg)
        - 
- Accessing items within `array`s, `collection`s, and `map`s
    - ![](img/03043.jpg)
        - Creating a `list` and `map`
            - ![](img/03044.jpg)
        - Accessing `list` of `cities` and `map` of `currencies`
            - ![](img/03045.jpg)
- Accessing items with operators
    - utilizing ***select all*** with `?[]` operator
        - ![](img/03046.jpg)
    - utilizing ***select first*** with `^[]` operator
        - ![](img/03047.jpg)
    - utilizing ***select last*** with `$[]` operator
        - ![](img/03048.jpg)
    - utilizing ***transform all*** with `![]` operator
        - ![](img/03049.jpg)
- Accessing parameters within an `@Autowire`
    - ![](img/03050.jpg)
        - `@Value` pulls the `user.name` from `systemProperties` and inserts it into method
            - what is `@Autowired`

#### 3.6 Working with Command-Line Arguments
- Overview of CLI arguments and Spring Boot startup up
    - ![](img/03051.jpg)
        - `args` passed in when `SpringApplication.run()` creates the beans
- To access `args` FROM THE BEAN....
    - must `@Autowired` with `(ApplicationArguments)`
        - ![](img/03052.jpg)
- Two types of CLI arguments
    - Options
        - ![](img/03053.jpg)
            - consist of ... `--name` and `=value`
        - ![](img/03054.jpg)
            - actual value
- Inputing command-line arguments with IntelliJ
    - ![](img/03056.jpg)
    - create a new configuration
        - ![](img/03055.jpg)
        - ![](img/03057.jpg)
        - ![](img/03058.jpg)
    - apply arguments
        - ![](img/03059.jpg)
        - ![](img/03060.jpg)
- Accessing arguments within bean using these methods...
    - `getSourceArgs()`
        - gets raw arguments like `--target=windows`
    - `getOptionNames()`
        - gets names of option arguments 
            - `--target=windows` returns `target`
    - `getOptionValues()`
        - gets values of option arguments 
            - `--target=windows` returns `windows`
    - `getNonOptionArgs()`
        - all the values that didn't have a name
            - `--target=windows --target=macOS --db=h2 wales 56` returns `wales 56`
- Accessing arguments within
    - `getSourceArgs()` with `--target=windows --target=macOS --db=h2 wales 56`
        - ![](img/03061.jpg)
    - `getOptionNames()` with `--target=windows --target=macOS --db=h2 wales 56`
        - ![](img/03062.jpg)
    - `getOptionValues()` with `--target=windows --target=macOS --db=h2 wales 56`
        - ![](img/03063.jpg)
    - `getNonOptionArgs()` with `--target=windows --target=macOS --db=h2 wales 56`
        - ![](img/03064.jpg)

### Lesson 4: Configuration Classes
#### 4.1 Defining a Configuration Class and Beans
- Overview
    - Typical operation
        - ![](img/04001.jpg)
            - Spring Boot scans for classes like this
            - calls the default constructor
            - 
    - What if we want values inside the default constructor?
        - Must utilize configuration classes (annotated with `@Configuration` with annotated methods of `@Bean`)
            - ![](img/04002.jpg)
    - Example
        - ![](img/04003.jpg)
            - `myBean` bean was created
            - it is a `MyBean` type
- Accessing beans
    - call context and `.getBean()`
        - ![](img/04004.jpg)
    - `@autowired` to automatically get context within component
        - ![](img/04005.jpg)
            - ![](img/04006.jpg)

#### 4.2 Locating Configuration Classes and Bean Methods
- Configuration classes
    - components that are scanned at the start of a Spring boot startup
        - ![](img/04010.jpg)
    - you can tell SB to look in alternative packages to find components and config classes
- Redirect to find comp / config 
    - ![](img/04007.jpg)
        - ![](img/04008.jpg)
    - Alternatively... just give a parent folder
        - ![](img/04009.jpg)
- Defining beans within the Application class
    - ![](img/04011.jpg)
        - ![](img/04012.jpg)
    - ideal for...
        - small application where it would not make sense to create a configuration folder

#### 4.3 Configuration Techniques
- Learning to create instances and to control...
    - the name of those instances
    - whether a singleton / prototype
    - whether lazy / or not

- Name with `@Bean(name="")`
    - naming it
        - ![](img/04013.jpg)
    - get each of the declared 
        - ![](img/04014.jpg)
- singleton / prototype
    - specified via `@Scope("prototype)`
        - ![](img/04017.jpg)
        - ![](img/04018.jpg)
    - running it
        - ![](img/04019.jpg)
    - Note... if not specified ... scope is presumed to be singleton
- lazy / or not
    - specifying with `@Lazy`
        - ![](img/04015.jpg)
            - ![](img/04016.jpg)

#### 4.4 Configuring Bean Dependencies
- Scenario - pulling information from a datasource
    - In plain java
        - ![](img/04020.jpg)
            - class `TransactionManager` references class `DataSource` as `dataSource`
- Technique 1 - specify source as a Bean within config class; activate within another bean
    - ![](img/04021.jpg)
        - Specified as a bean with `@Bean`
        - called **within** the `transationManager1()` bean
    - Running the code
        - ![](img/04022.jpg)
- Technique 2 - specify source as a Bean within config class; activate within bean parameter
    - ![](img/04023.jpg)


### Lesson 5: Spring Boot Techniques
#### 5.1 Setting Application Properties at the Command Line
- Purpose of application properties
    - what is it
        - the way to configure beans through passing parameters like...
            - connection strings for databases
            - names of message queues
        - can be overwritten with command line
    - why bother
        - because you can run your application on a case-by-case scenario
            - lets you change what database you are using
    - where can it be defined
        - ![](img/05001.jpg)
            - application properties within CLI args overwrite those within the JAR
- Basics of CLI args
    - basics
        - ![](img/05002.jpg)
    - Doing it requires...
        - Configuration
            - ![](img/05003.jpg)
                - Ensure to select the correct main class
                    - ![](img/05004.jpg)
                - Add your command line arguments
                    - ![](img/05005.jpg)
    - Testing it...
        - ![](img/05006.jpg)
            - `John Smith` is overwritten by command line argument of `Mary Jones`


#### 5.2 Specifying which Properties File to Use
- Changing where Spring looks for properties files
    - Places
        - Prioritization
            - ![](img/05007.jpg)
        - Places
            - `/config` folder on subdirectory of Java app
                - ![](img/05010.jpg)
            - Java App Directory
                - ![](img/05009.jpg)
            - `/config` folder on classpath
                - ![](img/05008.jpg)
            - root folder on class path
                - ![](img/05011.jpg)
    - Specifying another properties files OTHER THAN `application.properties`
        - Overview
            - ![](img/05012.jpg)
                - this will look for `app2.properties` file 
                - `"spring.config.name"` lets Spring know you are looking for a properties file
            - Technique 2 -- environment variable
                - `SPRING_CONFIG_NAME`
            - Technique 3 -- command line argument
                - ![](img/05015.jpg)
        - Testing ... getting `Bill Jones` from `app2.properties` from the class path
            - ![](img/05013.jpg)
            - ![](img/05014.jpg)
        - Testing ... getting `Bill Jones` from `app2.properties` from the CLI 
            - ![](img/05016.jpg)
            - ![](img/05017.jpg)


#### 5.3 Defining YAML Properties Files
- Why YAML
    - Great for...
        - complex names for properties
        - hierarchical property names
    - What it looks like
        - ![](img/05018.jpg)
    - YAML compared to `application.properties`
        - YAML
            - ![](img/05019.jpg)
        - `application.properties`
            - ![](img/05020.jpg)
- Inserting data from YAML into a bean
    - Template
        - ![](img/05021.jpg)
        - ![](img/05022.jpg)
            - NOTE!!! Requires this dependency
                - ![](img/05025.jpg)
                - should look like
                    - ![](img/05026.jpg)
    - Testing
        - Calling for `contact.propertyName`
            - ![](img/05023.jpg)
        - Calling for `prefix="contact"` and then `tel` and `contact`
            - ![](img/05024.jpg)


#### 5.4 Using Spring Profiles
- Profile beans
    - Great for...
        - adapting between environments (development/production)
        - adapting between connection strings
    - What it looks like
        - if you want a `MyBean4` in a Development and a Production environment
            - ![](img/05027.jpg)
    - Template
        - ![](img/05028.jpg)
        - ![](img/05029.jpg)
        - 
- Profile Properties
    - What it looks like... in YAML
        - ![](img/05030.jpg)
            - notice the `---` divider
- Setting Active Profile
    - Overview
        - ![](img/05031.jpg)
    - Implementation
        - Call for the `app4.properties` with `System.setProperty()`
            - ![](img/05034.jpg)
        - This is what is in the `app4.properties`
            - ![](img/05033.jpg)
        - This is what is pulled up
            - ![](img/05032.jpg)
        - See the results
            - ![](img/05035.jpg)


#### 5.5 Using Spring Boot Actuator
- Overview
    - ![](img/05036.jpg)
- To add Actuator
    - ![](img/05037.jpg)
        - ![](img/05038.jpg)
- To select how you want to see Actuator (endpoints)
    - ![](img/05039.jpg)
        - default...
            - ![](img/05040.jpg)
- Implement at `Application.java`
    - ![](img/05041.jpg)
- Running and viewing `localhost:8080/actuator/mappings`
    - ![](img/05042.jpg)
        - shows all `/endpoints` available with required/optional arguments
- Running and viewing `localhost:8080/actuator/health`
    - ![](img/05043.jpg)
- Running and viewing `localhost:8080/actuator/metrics`
    - returns directory 
        - ![](img/05044.jpg)
    - getting `process.uptime`
        - ![](img/05045.jpg)
--- 38 sections to go

### Lesson 6: Integrating with Data Sources
#### 6.1 Understanding Spring Data
- Overview
    - Using Spring Boot as a middle man for JPA
        - intercepts transactional methods enroute to database
        - handles exceptions with...
            - commit transactions
            - or roll back the transaction
        - Achieved with an object, a special beam or sprint transaction manager
        - 
    - Also manages the connection to the database
        - normal connection
            - requires some kind of authentication 
                - takes time and resources
        - with spring boot
            - it maintains the connection to save resources
                - within a connection pool
    - Also simplifying CRUD and query database operations
        - automatically figures out what SQL query 
            - for getting data from the database
            - and return an object with that data in it
- Implementation
    - add Maven dependency / database driver / JRE file
        - on your class path
    - example -- adding H2 driver...
        - ![](img/05046.jpg)
            - ![](img/06001.jpg)

#### 6.2 Getting Started with JPA
- Basics
    - ![](img/06002.jpg)
        - requires Hibernate to better use the Java EE classes within JPA
    - Entity class --- Database table
        - each class is treated as a RDB table
        - each property is treated as a RDB column
    - **entity manager class**
        - entity classes are manages by a **entity manager class**
            - purpose - fetch / save entities to DB
            - EM class has the CRUD methods for relational database operations
    - **entity manager factory**
        - creates the **entity manager class** for that specific database
            - created automatically by spring
- Implementation of JPA within Spring Boot
    - ![](img/06003.jpg)
        - ![](img/06004.jpg)
    - ![](img/06005.jpg)
    - When Spring Boot sees this dependency...
        - creates several beans automatically in your application
            - `DataSource` object for managing connection to DB designated in POM
            - `JdbcTemplate` object for executing CRUD SQL statements
            - `EntityManagerFactory` object for creating the entity manager... converting classes into SQL tables... and queries
            - `PlatformTransactionManager` for managing any transactional method calls made by `EntityManager`


#### 6.3 Configuring JPA in Spring Boot
- Required Properties 
    - ![](img/06006.jpg)
    - ![](img/06007.jpg)
        - Normally set in `src/main/resources`
        - ideally you would need to adjust settings for databases... but...
            - Spring Boot can auto-config H2
- If you need to customize the H2 connection...
    - ![](img/06008.jpg)
        - `create-drop`
            - if Spring sees entity classes
                - will create a table even if no data is available yet
            - when Spring is at an end
                - will drop the table
        - `show_sql`
            - shows sql commands and responses


#### 6.4 Defining JPA Entity Classes
- Review
    - Entity Class
        - maps to a database table
    - To Create Entity Classes and map them to H2 database tables...
        - ![](img/06009.jpg)
    - Need Hibernate set to work with JPA
        - ![](img/06010.jpg)
            - remember `create-drop` destroys tables AFTER app closes
- Defining an Entity Class
    - `@Entity` to load entity framework
        - ![](img/06011.jpg)
    - `@Table` to specify the name of the table to be generated
        - ![](img/06012.jpg)
            - can be omitted IF...
                - you want the table name TO MATCH EXACTLY to class name
    - class properties WILL BECOME table columns
        - ![](img/06013.jpg)
            - types will become 
    - `@Column()` to specify the name of the column to be generated
        - ![](img/06014.jpg)
            - instead of using `dosh` as the name of the column
                - will use `salary` as name of column
    - `@Id` to specify primary key column
        - ![](img/06015.jpg)
            - remember primary key MUST BE UNIQUE ... better for db to manage unique generation
    - `@GeneratedValue` specifies that the DB generates the values IN THE COLUMN
        - ![](img/06016.jpg)
            - surrogate primary key - generating an id based on random number
            - `strategy` refers to the DB's strategy; each DB has different strategies
                - `GenerationType.IDENTITY` within H2 refers to auto-increment
                    - each record added gets `previousValue+1`
                    - stategies
                        - ![](img/06017.jpg)
                        - ![](img/06018.jpg)
            - `-1` specifies dummy value; DB can replace
        - alternative approach - natural primary key
            - real-world values (SSN)
            - omit the `@GeneratedValue()`
            - must write script to insert item into DB
    - What it looks like
        - implement properties (columns)
            - ![](img/06019.jpg)
        - implement methods
            - ![](img/06020.jpg)
        - overriding JPA methods to tailor to specific database
            - tailoring `equal` method
                - ![](img/06021.jpg)
                    - `equal` returns a Boolean
- Organizing Your Entity classes
    - if your entities are NOT in the same folder as the `application.java`
        - what it looks like if in same folder
            - ![](img/06022.jpg)
        - to tell Spring to look elsewhere...
            - `@EntityScan`
                - ![](img/06023.jpg)
    

#### 6.5 Seeding the Database with Sample Data
- Review
    - `jdbctemplate`
        - used by Spring for generating SQL statements
- Utilize `jdbctemplate`
    - need to `@autowire` to the dependency to utilize
        - ![](img/06024.jpg)
    - need to `@PostConstruct`
        - ensures the entire library is loaded
        - ![](img/06025.jpg)
- javadoc --- docs.spring.io/spring-framework  jdbxtemplate.html


#### 6.6 Viewing Database Data
- Review
    - `application.properties` holds the hibernate/jpa settings
    - `@Entity` creates an Entity class
    - `@Table` is used to specify a different table name from the class name
    - `@Id` specifies the property to become the primary key attribute
    - `@GeneratedValue` tells Spring to generate values based on specified `strategy`
    - `@Column` specifies the a different column name instead of the property name
    - Within application class
        - we specify a service bean that contains the business methods
            - ![](img/06026.jpg)
        - it contains
            - methods for queries
            - methods for modifications
-  Service bean
    - `@Component` specifies that it is a component
        - ![](img/06027.jpg)
    - `Scanner(System.io)` looks for keyboard inputs
        - ![](img/06028.jpg)
    - `@Autowired` tells Spring to look for a repository / storage
        - ![](img/06029.jpg)
    - `queryEntities()` prompts for an employee id
        - ![](img/06030.jpg)
            - `promptForId()` asks for an employee `id`
            - `repository.getEmployee(id)` looks for said `id`
        - 
            - 
    - `displayEmployees()` returns all employees
        - ![](img/06031.jpg)
            - `reposity.getEmployees()` looks for ALL employees
    - 
        - 
- Queries within Repository class
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