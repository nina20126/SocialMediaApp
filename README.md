# Social Media App
.Net Core | React with TypeScript | MobX

## Walking Skeleton - API

#### Application Architecture

* DOMAIN in the center
  * Domain contains domain entities: classes that form the foundation of the business logic for the application
  * **Domain is the center of everything and it has no dependencies on anything else.**
* APPLICATION is the second layer
  * Application layer is going to be responsible for **business logic**
  * It will have a dependency to the domain layer
  * Any of our domain entities are going to be accessible in our application layer
  * Application layer also has dependency on **persistence** layer
* API layer comes third
  * Api layer have a dependency on the application layer
* PERSISTANCE layer
  *  Have a dependency on our **domain** layer
  *  Persistance layer has an access to the entities that we use to scaffold our database
 
#### Individual Projects

**API**  
API project initially just has one responsibility: It receives HTTP requests and responses to them.  

**APPLICATION**  
Application project is responsible for processing our business logic and it has **dependency on the domain.** Application projects job is to use the domain entities, query our database and translate the code into SQL-queries. Return the logic to API.

**DOMAIN**  
The Domain contains the business entities and it is the center of everything that we do in the application.  

**PERSISTENCE**  
Persistance project provides the connection to the database and translate the code into SQL queries. This is link between Application and Domain projects.  

  Even though the API does not have a dependency on either the domain or the persistence project because it has a dependency on the application, which then has a dependency on a domain and the persistence. The API has a transitive dependency on both of those projects, too. So our API does have access to our domain and it does have access to the persistence layer via the application.
