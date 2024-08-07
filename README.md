# CS-465-Full-Stack-Dev-I

The client, Travlr Getaways has requested a fully functioning travel booking website, which will include a customer-facing website, a database, and an admin single-page application that all need to work together. For the architecture of this full stack web application, the MEAN (MongoDB, Express, Angular, and Node.js) stack will be used for the development including the initial setup of the Node.js server and the Express framework. We will work to customize the customer-facing webpage to align with the wireframe provided and meet Travlr Getaways’ vision. The wireframe will be an initial reference to guide the construction of a static customer-facing website using HTML, CSS, and JavaScript. We will also develop an administrator interface, request responses using traveler search criteria, and collect login identification. MongoDB database will be used to store travel booking trips. We will create JSON files containing initial data for seeding the database to enable testing of the RESTful API routes. A client single-page application (SPA) using Angular, with tested security features will complete the full stack web application. Finally, Travlr Getaways has requested an added layer of security that applies to server-side applications to produce web tokens for web login authentication. <br> 
<br>
<b>Web Browser:</b> The application must support interaction with various web browsers to ensure compatibility and consistent behavior across different browsers.<br>
<b>Server-Side Components / Database Dependency:</b> Since MongoDB is used as the database management system, the application should be designed to utilize MongoDB-compatible libraries and frameworks for database interactions.<br>
<b>Client-Server Communication:</b> Communication between client and server components with dependencies and interactions requires a RESTful API to be efficient.<br>
<b>Authentication:</b> Must integrate robust authentication protocols (web tokens) to authenticate and authorize users securely.<br>
<br>
<b>Client-Side Components:</b><br>
Web Browser: The interface - how users interact with the application.
Client Session: Manages the session state on the client-side.
Traveler Portfolio: Manages and displays the client’s portfolio information.
Graphic Library: Houses graphical elements and functionalities for the interface.<br>
<br>
<b>Server-Side Components:</b><br>
Authentication Server: Handles user authentication and authorization processes.
Server Session: Manages the session state on the server-side.
Traveler Database: Stores client data like profile information, preferences, and historical data.
Mongoose ODM: Object-Document Mapping (ODM) library for MongoDB for interactions with the MongoDB database.<br>
<br>
<b>Database Component:</b><br>
MongoDB: A NoSQL database used to store various types of data required by the application.<br>
<br>
<b>Components and Relationships:</b><br>
•	The Web Browser interacts with both the Traveler Portfolio and Client Session components showing that the user interface elements and session management are handled on the client-side.<br>
•	The Traveler Portfolio component interacts with the Graphic Library for rendering graphical elements and with MongoDB for data storage.<br>
•	MongoDB interacts with Mongoose ODM for communication between the application and the database.<br>
•	The Server Session component connects to the Traveler Database for accessing client data.<br>
•	The Client Session component communicates with the Authentication Server for client-server authentication processes.<br><br>
Overall, the architecture follows a clear definition of client-side and server-side responsibilities. The client-side components handle user interactions and interface logic, and the server-side components manage data storage, authentication, and session management. Using MongoDB as the database offers flexibility and scalability in handling data storage needs.<br>
<br>
<b>Sequence:</b><br>
Beginning in in the Client-Side, the user interacts with the application through the browser and UI elements generated by AngularJS. AngularJS captures user events like clicks, keystrokes, etc., and responds to them by triggering actions or updating data. When the user performs an action that requests or sends data to the server AngularJS sends HTTP requests to the server-side.<br>
<br>
On the Server-Side Express.js handles incoming HTTP requests from the client-side and routes them to the appropriate controller based on the URL endpoint. The controller logic executes things like querying the database (MongoDB), processing data, and generating responses. Data validation, authentication, authorization, etc., is also executed on the server-side. If data needs to be pulled or modified, Express.js interacts with MongoDB using Mongoose to use the database.<br>
<br>
In the Data-Tier, MongoDB receives requests from the server-side to perform CRUD (Create, Read, Update, Delete) operations on the data stored in the database. MongoDB processes the requests and performs operations like retrieving documents, inserting new data, updating existing data, or deleting data based on the requests received from the server-side.<br>
<br>
Back to the Server-Side, after processing the data and/or performing necessary operations, Express.js generates an HTTP response in JSON format that is sent back to the client-side for the corresponding request.<br>
<br>
Back to Client-Side, AngularJS receives the HTTP response from the server-side and updates the UI and binds the data, updating the view with the changes.<br>
<br>
This cycle repeats as users continue to interact with the application, triggering new HTTP requests and responses between the client-side and server-side components.<br>
<br><br>
<b>How is the Angular project structure different from that of the Express HTML customer-facing page?</b>
In an Angular project, everything is organized into neat sections. You have the main stuff (app), different parts of the site (components), and tools you need (services). There's also a place for things you don't change often, like pictures and colors (assets). The project also has a list of instructions (angular.json) and a list of what it needs (package.json).
In an Express project, you have a folder that keeps things everyone can see (public), another folder with the different versions of the site (views),  a map (routes) to find the right place to deliver each version and a list of what it needs (package.json).<br>
<br><br>

<b>What are some advantages and disadvantages of the SPA functionality? What additional functionality is provided by a SPA compared to a simple web application interaction?</b>
An SPA (Single Page Application) doesn't need to reload the entire page so it feels faster and more responsive. It only get the data they need, so they can also be more efficient and reduce the load on the server. Developers can use frameworks like Angular to build SPAs, which can make development faster and more organized.
Search engines sometimes have trouble indexing SPAs because they rely heavily on JavaScript. They might take longer to load initially because they need to get all the code for the app before displaying anything. Developing SPAs can be more complex than traditional websites, especially for beginners. Some older browsers might not support all the features used in SPAs.
SPAs can update content without refreshing the whole page, making them feel more dynamic and some can work offline. They can also provide smoother animations and transitions and keep track of things like user preferences and data changes without losing them when the page reloads.<br>
<br><br>

<b>What is the process of testing to make sure the SPA is working with the API to GET and PUT data in the database?</b> What are some errors you ran into or what are some errors you could expect to run into?
Make sure the MongoDB is installed and running, set up your Express.js API to connect to MongoDB and define routes for GET and PUT requests. Set up your Angular application to make HTTP requests to the API. In Postman, create GET requests to get data from the API endpoints and PUT requests to update data in the database. Check MongoDBCompass to see that changes were made to the database. 
Some errors that could cause problems are not having all components are up and running, typos  and making wrong associations or connections.



