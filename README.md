# Mobile app for hosting/joining local events


## Work division

We as a team have outlined tasks for our Workshop, and came down to the following:

- 3 problems that our solution would solve
- Ways our solution would remedy the stated problems (1 for each problem)
- 5 Technologies required by a solution

Given that the person who stated the problem would have the most understanding of how to solve it, we have unified stating the problem and proposing the solution to it in one task.

Overall, we have 8 tasks (3 problems/solutions and 5 technologies) that are divided evenly within 4 members of our team.


## Describe the problem

### Problem 1 *(by Jiseok Shim)*
Difficulty in organizing and managing small-scale local events

Problem:
Event organizers have difficulties in conducting and organizing small local events. In checking participants' confirmation, communication with participants, and event feedback, Organizers feel uncomfortable performing manually or using various apps without a dedicated app, and this is inefficient event management.

### Problem 2 *(by Anurag Das)*

### Problem 3 *(by Anurag Das)*


## Propose a solution

### Solution to Problem 1 *(by Jiseok Shim)*
Difficulty in organizing and managing small-scale local events

Solution:
A mobile app for hosting/participating local events can help run and manage events successfully. The app can support organizers and simplify event management. For example, it provides organizers with functions such as managing participants, communicating with participants, and collecting event feedback to facilitate event management and data tracking.

### Solution to Problem 2 *(by Anurag Das)*

### Solution to Problem 3 *(by Anurag Das)*


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
