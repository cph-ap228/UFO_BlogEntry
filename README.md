# UFO_BlogEntry

### How do we stop message protocols proliferating? Learn to pick your standards!


“Trying to punch a nail through wood with your left fist, while holding a hammer in your right”. 
This is especially true in scenarios where connections are bound to be made between clients and a server to create a seamless operation with no downtime. However, what your application may need is the understanding between a need and a preference. A selection of popular messaging protocols have been compared in this paper to see, that many of these processes can be lightened for increased performance and less headaches. If developers started to push their “high-horsed” preferences to the side and focused more on what their application really needs. 

##### RESTful HTTP versus. WebSockets #####

To really dive down into what differs between the protocols we must start by what they mean in general sense, how they interpret and what resulted to the standardization of other mainstream messaging protocols. 

##### Starting with sockets ##### 
Sockets are a paradigm for handling networking, and the concept has been around for decades. Sockets were once a way to standardize networking I/O, very much like an API, which means that regardless of the particulars hardware application would be able to program to sockets and proceed to work with many different hardware implementations. But the whole idea behind a socket, is that it is a “port” through which data goes in and out of. Much like a real trading port for data, where the socket itself is the dock and is where the exchanges are happening for the applications standpoint.
Now WebSockets are just an extension of the original socket idea and became a movement in implementing sockets to steer away from the standard HTTP protocol. See while HTTP was invented for the World Wide Web and has been used ever since, it has had some pretty major limitations. A protocol that worked in very particular ways to say the least, and really isn’t suited for every need. Obviously, the problem resides in how HTTP handles connections. If you’re in need to made a request to download HTML or an image, a port would open, data would be transferred and then it would close again. The opening and closing creates overhead, and for applications and uses where the users want rapid responses, real time interactions and/or display streams of data, this approach simply doesn’t work. Another limitation with HTTP is that it was until the introduction of sockets a “pull” paradigm. Where the browser would request or pull information from servers, but the server would not be able to push data to the browser when it wanted to. Which lead to another issue with having to pill the server for new information by repeating requests to see if any new data was published. 


Back in 2011, the WebSocket as we know today, got standardized and allowed the usage of the WebSocket protocol, to make more flexible ways of transferring data too and from servers within the browser, to allow for more control and a steadier data stream. This also allows for Peer-to-Peer connections between browsers, unlike HTTP. WebSockets allows the socket which is connected to the server to stay “open” for communication, which lead to data freely being able to be pushed to the browser in real-time on demand. 

##### Representational State Transfer or REST #####
, on the other hand is another abstraction for creating API’s for applications in a standardized way. It was developed to formalize the approach behind HTTP/1.0, finding what worked well and using this more structured abstraction to influence the newer design of HTTP/1.1. One could say that REST is the design style behind HTTP. The typical and traditional web applications are architected with creating REST endpoints utilizing HTTP. A real-world advantage of HTTP is however that it’s recognized and utilized by every programming language, in a sense that they all receive requests for information and are therefore responding accordingly to the request. The usage of REST is predictable in the ways which REST organizes these requests. Requests originate from the client, and the common HTTP verbs include: GET, POST, PUT & DELETE amongst others. These correspond to the expected operations as retrieving data, submitting data, updating and deleting data. 

REST while also being stateless, and by inheriting the nature of statelessness and the principle of RESTful, we can mandate what kind of commands that can be offered between the client and server. The implementation of stateless requests means that the communication between consumer and service is initiated by the request, and the request contains all the information necessary for the server to respond. This creates the client-server mandate, meaning that each service provided has multiple capabilities and listens for requests. The requests are made by a consumer and then accepted or rejected by the server. Finally of the worthy principles of RESTful is the one that makes the RESTful architecture so scalable, layered systems. Multiple layered systems can be used to grow and expand the interface, even when none of the layers can see into the other. This allows for new commands and middleware to be added on top, without impacting the original commands and function between the client and server. 

##### What do we get to choose and use? #####	                                                         	                                  
In a nutshell REST refers to usage of defining principles for developing API, but due to the traditional use of endpoints and HTTP protocols with today’s standard of web applications it falls short based on a bottleneck with the principle of opening and closing connections. This makes WebSockets are more viable choice when seeking performance in being able to send and receive data, and the number of concurrent devices that can do so is a significant consideration in using WebSockets.

Generalizing, WebSockets is a stateful protocol where communication happens over a dedicated TCP connection. On the other hand, HTTP is inherently a stateless protocol. This has an impact on how these will perform with the load but that really depends on the use case. 
Since communication over WebSockets happens over a reusable TCP connection, the overhead per message is lower compared to HTTP, as previously mentioned. Hence this, it can reach a higher throughput per server. But there is a limit to which a single server can scale and that is where WebSockets run into issues. It’s not an easy and or efficient task to horizontally scale applications using WebSockets. HTTP has a clear advantage in this field, since we can scale its overall throughput by adding more servers without impacting the overall performance of the application. 

In conclusion for these protocols, for the bulk of the scenarios then, where occasional communication is required with the server, like for example, getting the record of an employee, it’s still sensible to use REST service over HTTP. WebSockets are more suitable for cases where a push-based and real-time communication defines the requirement more appropriately, saying you’d like to have a newer client-side application with stock-prices, which requires real-time updates on the server, gives much more leverage to using WebSockets. Additionally, WebSockets works better for scenarios where a message needs to be pushed to multiple clients simultaneously, where RESTful services will find it difficult if not prohibitive. 

It all must be drawn and selected based on requirements. There’s no silver lining but many forget that they might be using the wrong procedure for their specific task and application, essentially wasting resources by trying to achieve the same thing which could be done with a different approach and protocol. 

#### versus. AMQP (RabbitMQ) 
TO DO (…) 
Section of details on the protocol
Compare with REST and WebSockets,

##### AMQP vs WebSocket

Message queues provide an asynchronous communications protocol, which can be useful in processing larger amount of data in a message, or when we require processing of jobs in a more controlled manner. In practice message queue protocols and websockets can be quite similar, they each transmit a message and can trigger events remotely, allowing dynamicity and the possibility of having cross-platform input to some extent. 



Pros and Cons based on use cases.
Conclusion
