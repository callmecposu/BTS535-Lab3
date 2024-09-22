# Mobile app for hosting/joining local events


## Work division

We as a team have outlined tasks for our Workshop, and came down to the following:

- 3 problems that our solution would solve
- Ways our solution would remedy the stated problems (1 for each problem)
- 7 Technologies required by a solution

Given that the person who stated the problem would have the most understanding of how to solve it, we have unified stating the problem and proposing the solution to it in one task.

Overall, we have 10 tasks (3 problems/solutions and 7 technologies) that are divided evenly within 5 members of our team.


## Describe the problem

### Problem 1 *(by Jiseok Shim)*
Difficulty in organizing and managing small-scale local events

Problem:
Event organizers have difficulties in conducting and organizing small local events. In checking participants' confirmation, communication with participants, and event feedback, Organizers feel uncomfortable performing manually or using various apps without a dedicated app, and this is inefficient event management.

### Problem 2 *(by Anurag Das)*
Difficulty in Discovering Relevant Local Events

Problem:
People often struggle to find interesting and relevant local events that align with their interests and preferences. This can lead to missed opportunities for social connections, entertainment, and learning.

### Problem 3 *(by Anurag Das)*
Lack of Community Building at Events

Problem:
Many local events fail to foster a sense of community and connection among attendees. This can lead to a lack of engagement and a feeling of isolation.


## Propose a solution

### Solution to Problem 1 *(by Jiseok Shim)*
Difficulty in organizing and managing small-scale local events

Solution:
A mobile app for hosting/participating local events can help run and manage events successfully. The app can support organizers and simplify event management. For example, it provides organizers with functions such as managing participants, communicating with participants, and collecting event feedback to facilitate event management and data tracking.

### Solution to Problem 2 *(by Anurag Das)*
Difficulty in Discovering Relevant Local Events.

Solution:
Our mobile app will address this problem by providing a personalized event discovery platform. Users can create profiles indicating their interests and preferences, allowing the app to curate a tailored list of events. Additionally, we will implement a robust search function with filters for various categories (e.g., music, art, food, sports) and location-based recommendations to help users find events near them.

### Solution to Problem 3 *(by Anurag Das)*
Lack of Community Building at Events

Solution:
Our mobile app will address this problem by incorporating features that promote community building. We will include a messaging function to facilitate communication between attendees and event organizers. Additionally, we will explore the possibility of creating virtual event communities where users can discuss topics related to the event or connect with like-minded individuals. This will help to create a more inclusive and engaging event experience.


## List the technologies required by the solution

### Mobile Development Framework *(by Maksym Volkovynskyi)*

#### Chosen Technology: *React Native*

Since we are developing a mobile application, we will require a Mobile Development Framework. There are several options to choose from, including:

- Native iOS Development with **Swift**
- Native Android Development with **Java**
- Cross-platform Development with **Flutter**
- Cross-platform Development with **React Native**

Native development options have gone out of the question for us due to having to maintain two separate codebases for Android and iOS versions of the app, which would bring significant overhead at the early stages of development. Hence, our choice lies between **Flutter** and **React Native**. Since **React Native** is a direct **React** offspring, choosing it as a base mobile development framework would make it easy for us to port the frontend layer to a website later on, whereas a **Flutter** project would not be portable to web and would have us rebuild the website from scratch when we require it.

### Backend Framework *(by Daniel Krause)*

##### Node.js + Express

*Node.js (a runtime environment that executes JS server-side) and Express (a minimal web framework for Node.js).*


Reasoning:


Node.js offers high scalability. It's non-blocking IO, allows, unlike traditional server-side languages like PHP or Ruby, to handle a greater amount of concurrent requests, such as multiple users creating or joining events in real time. Since Express is lightweight, this allows us to create a structured and easy to maintain codebase from the ground up, streamlining future CI & CD. Node.js also allows us to use JavaScript on both frontend and backend, providing further consistency in the codebase, increasing team collaboration and development. Alternatives like Django or RoR would require additional infrastructure to match out-of-box Node.js+Express capabilities, which would increase overall project overhead.

### Database *(by Jiseok Shim)*

MongoDB: MongoDB is a database that provides high performance and easy scalability.
MongoDB has a high degree of schema freedom, allowing it to store data without prescribing the structure and fields of the data, which is useful when the structure of the data changes frequently or when it needs to be stored in various forms. When event organizers run multiple small events, SQL based databases requires frequent changes to the data structure, while MongoDB does not fix the schema, so it has the advantage of being able to easily change the data structure. It is a good technology for event organizers who can also change the data structure while conducting various local events.
Unlike SQL based databases, MongoDB can provide a faster and more pleasant experience when you need to send notifications to users through fast memory access or when you need to communicate with participants in real-time.
MongoDB helps you easily retrieve data and extract only the data you need by using various query functions. In addition, MongoDB can handle large amounts of data by providing the MapReduce function.This is useful later when local events become larger and more participants have to deal with large amounts of data.

### Real-Time Communication *(by Maksym Volkovynskyi)*

#### Chosen Tecnhology: *WebSockets*

We find it necessary for our app to enable its users, whether they are events' attendees or hosts, to seamlessly connect with one another. To implement this feature, we require some sort of Real-Time Communication framework that would allow for consistent and secure two-way communication between users, be it in a form of Direct Messaging or Event Group Chats. 

To achieve this functionality, we will need to rely on a chat microservice utilizing a communication protocol that enables two-way information exchange between client and server. There are two communication protocols that can be used for this purpose: **gRPC (Google Remote Procedure Call)** and **WebSockets**. **gRPC** offers more advanced features and enhanced performance, but it can't be used directly from a browser interface, which would render chat microservice inaccessible if we decide to make a website port for our application later. **WebSockets**, on the other hand, can be used in both mobile and browser environments, which would allow us to build the chat microservice once and reuse it for both mobile application and website.

### Payment Integration *(by Daniel Krause)*

##### Stripe

*Stripe - an online payment processing platform.*


Reasoning:


Stripe offers an incredibly friendly developer API with excellent documentation. Stripe also offloads a lot of the payment processing overhead off of the developer. PCI DSS compliance, encryption, and fraud prevention are all done on their end and to a very high standard. This reduces the burden of developing, implementing, and then maintaining this subsystem. Stripes as an all-in-one platform, unlike Paypal or other alternatives, will allow us to vastly reduce the manhours required to complete this subsystem, while still allowing this subsystem to scale with the rest of the project. We need what Stripe offers (payment processing, recurring payments, secure transactions, a custom checkout experience, event ticketing management, and an inhouse analytics and reporting) since our platform intends to solve our users need to schedule events that may require attendees to prepay for food, accommodation, and other amenities, etc.

### Geolocation Services *(By Japit Singh)*

#### Chosen Technology: *Google Maps API*

We believe that our app must assist users in finding nearby events and offer location-based event recommendations. In order to put this into practice, geolocation services are needed to show event locations on a map, provide directions to the site, and let users filter events according to proximity. Our project requires the Google Maps API because of its many capabilities, which include precise geocoding, a wide range of routing choices, and a wealth of location data. Integrating the Google Maps API will improve user experience by enabling real-time travel and increasing the effectiveness and engagement of event discovery.

### Analytics and Reporting *(By Japit Singh)*

#### Chosen Technology: *Google Analytics*

We need analytics tools to track user behavior, keep an eye on app performance, and learn more about event engagement. For this, Google Analytics will be incorporated, providing comprehensive reporting on event interactions and user behavior. This technology is essential to our project since it allows event planners and developers to analyze user participation and find popular features to optimize the app experience. Google Analytics gives us strong insights into user activity patterns, conversion tracking, and demographics, enabling us to make informed decisions to improve the performance of our application.

### Recommendation System: *(By Anurag Das)*

#### Chosen Technology: *TensorFlow*

Reasoning: 

TensorFlow is an open-source machine learning library developed by Google. It provides a comprehensive ecosystem for building and deploying machine learning models, including those for recommendation systems. TensorFlow has dedicated modules like TensorFlow Recommenders, which simplifies building recommendation algorithms using collaborative filtering, content-based methods, and hybrid approaches. It’s highly scalable and can easily integrate with mobile apps.

### Community Forum: *(By Anurag Das)*

#### Chosen Technology: *Firebase Firestore*

Reasoning: 

Firebase Firestore is a NoSQL database that offers real-time synchronization, which can be useful for a custom-built forum. You can create a lightweight, scalable forum by using Firebase as your backend and building a custom frontend using React Native or another frontend technology. Firebase offers built-in support for real-time updates, making it ideal for dynamic interactions like posts and comments appearing instantly.