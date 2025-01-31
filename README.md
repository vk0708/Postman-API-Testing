# Postman-API-Testing
Postman is an API(application programming interface) development tool that helps to build, test and modify APIs.

[Basics](README.md#basics)

[POSTMAN introduction](README.md#postman-introduction)

Free APIs for practices:
https://reqres.in/

## Basics:
API -> Interface -> Communicate

HTTP: is a protocol for fetching resources. data exchange on web and client server protocol.
![image](https://github.com/user-attachments/assets/8d2f25fe-d2a0-49cc-8317-11533f876e96)

### tools which are used for API Testing :
Postman, Katalon Studio, Soap UI, Parasoft, REST assured, Tricentis Tosca, Ping API, Assertible

### What exactly we check during API testing :
Data accuracy.
Response time.
Duplicate or missing functionality.
Authorization checks.
Multithreaded issues.
Security and performance issues.
Error codes if API returns.
Reliability issues.

### HTTP response status codes
Informational responses (100 – 199)
Successful responses (200 – 299)
Redirection messages (300 – 399)
Client error responses (400 – 499)
Server error responses (500 – 599)

## POSTMAN introduction
### Postman Client
HTTP Client is a Program that uses HTTP to sent request to and receive responce from web server.

### SOAP vs REST vs GraphQL
SOAP, REST, and GraphQL are all web service APIs that have different strengths and weaknesses. The best choice depends on the requirements of the application. 

#### SOAP
Use: SOAP is well-suited for large, distributed environments like financial services, e-commerce, and telecommunications. 
Features: SOAP uses XML to exchange information, and provides built-in error handling. 

#### REST
Use: REST is a popular choice for public APIs, like e-commerce sites. 
Features: REST is simple and intuitive, and follows HTTP standards. XML and JSON

#### GraphQL
Use: GraphQL is a good choice for modern applications that require flexible data queries and reduced data transfer. 
Features: GraphQL is a query language that allows you to specify exactly what data you need. 

### Collection:
a collection is a group of saved API requests that can be organized into folders. Collections are a useful tool for organizing, testing, and sharing API requests. 

### HTTP Methods
#### GET:
Retrieves data from a server using a URI. For example, you can use GET to retrieve a list of tasks from a to-do list API. 
#### POST: 
Sends data to a server, such as customer information or a file upload. For example, you can use POST to add a new product to an e-commerce store database. 

#### Other request methods 
PUT: Replaces existing data with updated data
PATCH: Updates specific fields of existing data
DELETE: Removes existing data from a database
HEAD: Similar to GET, but without the response body
OPTIONS: Describes the communication options for a resource
Using Postman 

#### Use the Postman API client to create and send API requests
Select the method dropdown list
Edit the method name text
Save your new method
Select Send to test the endpoint

## Send your first API request
Send an API request
Make sure you've downloaded and installed the Postman desktop app. When you're ready, open the Postman desktop app and send your first API request.
1. Select + in the workbench to open a new tab.
2. Enter postman-echo.com/get for the request URL.
3. Select Send.
Postman displays the response data sent from the server in the lower pane.
![image](https://github.com/user-attachments/assets/3fc2f054-1886-4f91-8228-fe9c49cede43)

## Variables
1. Global Variables:
These are available throughout Postman across all collections and environments.
They can be set and accessed via the "Globals" tab.
Useful for data you need across multiple collections.

2. Environment Variables:
These are tied to a specific environment.
You can define and use them in an environment-specific manner.
Common for things like API keys, URLs, etc.

3. Collection Variables:
Specific to a collection, they can be used for all requests within the collection.
Useful for grouping variables that only apply within a particular collection.

4.Local Variables:
These are temporary variables used only within a single request.
Typically defined in pre-request scripts or test scripts and only live for the duration of that request.

### Analyzing a response
In Postman, analyzing a response involves reviewing various aspects of the response received after making an API request. Here's how you can analyze it:

Status Code:
Located at the top of the response pane (e.g., 200 OK, 404 Not Found).
Indicates whether the request was successful or not.

Response Body:
This is the actual content returned by the API.
Can be in different formats like JSON, XML, HTML, etc.
You can view it in different views: Raw, Preview, or Pretty (formatted for readability).

1. Headers:
Shows metadata about the response, such as content type, authorization, and cache-control.
You can inspect these to verify information like content encoding or API version.

2. Time:
Displays the response time (in milliseconds) to understand how fast the server responded.

3. Size:
Shows the size of the response payload, useful for performance testing.

4. Cookies:
Lists any cookies returned in the response, which are often used for session management.

5. Test Results:
If you've written tests in the "Tests" tab, the results will show here. You can verify if the response meets your expectations (e.g., status code, data values).

Postman also allows you to automate response validation with tests written in JavaScript under the "Tests" tab. For example, you could test if a certain field in the JSON response is correct or if the status code matches expectations.
By using these features, you can effectively analyze the response to verify the accuracy and performance of your API.

## Params
1. Path Variables:
Purpose: Used to pass data as part of the URL path, typically for identifying specific resources (e.g., a particular user, product, etc.).

Example: GET /users/{userId}

Usage in Postman: Path variables are defined in the URL itself, and you can use Postman variables like {{userId}} to make them dynamic.

Example: GET /users/{{userId}}

Example Use Case: Fetch details for a specific user by their userId.

2. Query Parameters:
Purpose: Used to send additional data as key-value pairs appended to the URL. They are often used for filtering, sorting, or paginating results.

Example:GET /users?status=active&page=2
Usage in Postman:You can add query parameters in the "Params" section in the Postman interface. They automatically append to the URL.

Example: GET /users?status={{status}}&page={{page}}

Example Use Case: Retrieve a list of users with specific filters like status or pagination like page.

Key Differences:

Location in the URL: 
- Path variables are part of the URL path (e.g., /users/123).
- Query parameters are added after the ? in the URL (e.g., /users?status=active).

Usage:
- Path variables usually represent unique identifiers (e.g., user ID).
- Query parameters are more for filtering, sorting, or providing optional data.
These two elements are often used together to build flexible and dynamic API requests.
