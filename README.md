# UFO_BlogEntry

### Authors

Arkadiusz Paryz - cph-ap228@cphbusiness.dk 

István Farkas - cph-if36@cphubisness.dk 

Sean Altoft - cph-sa230@cphbusiness.dk 

Vlad Mircea Burac - cph-mb402@cphbusiness.dk 

---

### Abstract

In this blog entry we present three protocols; namely REST, sockets and message queues, that can handle communication between a Unity client and a server. 
We present three use cases to give an example of usages and benefits, but also identify each one of them and the limitations of these technologies, however the main focus is on the comparison between WebSockets and Message Queues. It is hoped that this study will inform fellow practicioners of these protocols, in differentiating between them and their intended purpose.

### Hypothesis 

It is to no suprise that these three widely used message protocols are widely used and that many are familiar with their existence, however the issue at hand is identifying the different protocols at hand and their limitations for whatever use case their users might need resolving. In a real-world scenario, it can be a must to learn and differentiate & optimize your application, supported by the right choice of protocol for the task. Why shouldn't everyone identify themselves with the possibilities of the most concurrent ones to date? Can our research paper influence others to make the right choice by unfolding the truth and story behind these protocols and their preferred use cases? These research questions are illuminated and brought to question; What limitations brought them to existance, why other message protocol profiliation haven't superseeded them. Our examples, define which exact limitations and needs that led into these protocols being enhanced and integrated into real everyday-applications and tasks, how we have used them and how you should use them.

##### Case study 
## How do we stop message protocols proliferating? Learn to pick your standards!

“Trying to punch a nail through wood with your left fist, while holding a hammer in your right”. 
This is especially true in scenarios where connections are bound to be made between clients and a server to create a seamless operation with no downtime. However, what your application may need is the understanding between a need and a preference. A selection of popular messaging protocols have been compared in this paper to see, that many of these processes can be lightened for increased performance and less headaches. If developers started to push their “high-horsed” preferences to the side and focused more on what their application really needs. 

##### RESTful HTTP versus. WebSockets #####

To really dive down into what differs between the protocols we must start by what they mean in general sense, how they interpret and what resulted to the standardization of other mainstream messaging protocols. 

##### Starting with sockets ##### 
Sockets are a paradigm for handling networking, and the concept has been around for decades. Sockets were once a way to standardize networking I/O, very much like an API, which means that regardless of the particulars hardware application would be able to program to sockets and proceed to work with many different hardware implementations. But the whole idea behind a socket, is that it is a “port” through which data goes in and out of. Much like a real trading port for data, where the socket itself is the dock and is where the exchanges are happening for the applications standpoint.
Now WebSockets are just an extension of the original socket idea and became a movement in implementing sockets to steer away from the standard HTTP protocol. See while HTTP was invented for the World Wide Web and has been used ever since, it has had some pretty major limitations. A protocol that worked in very particular ways to say the least, and really isn’t suited for every need. Obviously, the problem resides in how HTTP handles connections. If you’re in need to made a request to download HTML or an image, a port would open, data would be transferred and then it would close again. The opening and closing creates overhead, and for applications and uses where the users want rapid responses, real time interactions and/or display streams of data, this approach simply doesn’t work. Another limitation with HTTP is that it was until the introduction of sockets a “pull” paradigm. Where the browser would request or pull information from servers, but the server would not be able to push data to the browser when it wanted to. Which lead to another issue with having to pill the server for new information by repeating requests to see if any new data was published. 


Back in 2011, the WebSocket as we know today, got standardized and allowed the usage of the WebSocket protocol, to make more flexible ways of transferring data too and from servers within the browser, to allow for more control and a steadier data stream. This also allows for Peer-to-Peer connections between browsers, unlike HTTP. WebSockets allows the socket which is connected to the server to stay “open” for communication, which lead to data freely being able to be pushed to the browser in real-time on demand. 

##### Representational State Transfer or REST #####
REST is another abstraction for creating API’s for applications in a standardized way. It was developed to formalize the approach behind HTTP/1.0, finding what worked well and using this more structured abstraction to influence the newer design of HTTP/1.1. One could say that REST is the design style behind HTTP. The typical and traditional web applications are architected with creating REST endpoints utilizing HTTP. A real-world advantage of HTTP is however that it’s recognized and utilized by every programming language, in a sense that they all receive requests for information and are therefore responding accordingly to the request. The usage of REST is predictable in the ways which REST organizes these requests. Requests originate from the client, and the common HTTP verbs include: GET, POST, PUT & DELETE amongst others. These correspond to the expected operations as retrieving data, submitting data, updating and deleting data. 

REST while also being stateless, and by inheriting the nature of statelessness and the principle of RESTful, we can mandate what kind of commands that can be offered between the client and server. The implementation of stateless requests means that the communication between consumer and service is initiated by the request, and the request contains all the information necessary for the server to respond. This creates the client-server mandate, meaning that each service provided has multiple capabilities and listens for requests. The requests are made by a consumer and then accepted or rejected by the server. Finally of the worthy principles of RESTful is the one that makes the RESTful architecture so scalable, layered systems. Multiple layered systems can be used to grow and expand the interface, even when none of the layers can see into the other. This allows for new commands and middleware to be added on top, without impacting the original commands and function between the client and server. 

##### AMQP

Message queues provide an asynchronous communications protocol, which can be useful in processing larger amount of data in a message, or when we require processing of jobs in a more controlled manner. In practice message queue protocols and WebSockets can be quite similar, they each transmit a message and can trigger events remotely, allowing dynamicity and the possibility of having cross-platform input to some extent. 

AMQP is usually used with a specific library for your programming language of choice, and in those libraries the protocol is established over a specific port. So, in effect, over sockets. Since WebSockets are actually sockets, the AMQP protocol can be used over WebSockets as well, if desired. In a way, AMQP can be seen as an extension to what sockets can do by default, since it also includes message encryption, and a queing system, in it's protocol.

For delivering and receiving AMQP messages you need a broker. A broker is no more than a server that receive, store and deliver messages. Depending on your costs and infrastructure, this fact may add extra complexity to your project, having to configure and maintain one/several/federation/... of brokers. This broker is basically a middleware between the ends of your applications that do the communication.


##### RabbitMQ
RabbitMQ is a message-queueing software also known as a message broker or queue manager, and it is the example we will use here. Simply said; it is software where queues are defined, to which applications connect in order to transfer a message or messages. There are other similar software solutions, but we will focus on RabbitMQ.

It uses the AMQP protocol to receive and send messages through it's queues, and comes with all you need to be able to use the AMQP protocol and manage your queues. It's in built web manager allows you to do all operations you would like to do on channels, exchanges, and queues, including publishing and consuming messages, purging a whole queue, deleting or creating them, or even moving all messages from one queue to another.

##### HTTP vs AMQP

The main advantage of AMQP over REST is that it allows for message queueing, and handling problems with information transfer. Such as, for example requeueing a failed message, or choosing how to read from a queue. It also allows message filtering and separation to different queues, depending on the message source, content, and headers.

The main problem with AMQP is that it is a pretty complex protocol, with a large documentation, and is not as widely adopted or familiar to most developers as HTTP and REST. Also, debugging over HTTP is easy and repeatable, whereas an AMQP message is harder to debug (you need connection to the queue, libraries, maybe scripting, etc...).

If fastness is what you are looking for, the HTTP conveys messages faster, but does not ensure the message actually gets there as well. The trade off here is that the AMQP protocol can be used to provide a more specific, and customized solution, to your messaging needs, while ensuring message delivery asynchronously, whereas HTTP is pretty straightforward in it's usage, but is synchronous and stateless, not ensuring message delivery. 

HTTP is also not as scaleable as AMQP, with RabbitMQ having everything you need "out of the box" for you to use the protocol, and the ability to fanout a message to inform multiple components at once, among many others, that are just not available over HTTP. For AMQP, having a broker as a middleware can have several advantages in terms of message transformations, depending on where that message is being sent, and, in effect, larger orchestrations of message pathways can be set up, which is just not possible in the same way over HTTP.

##### What do we get to choose and use? #####	                                                         	                                  
In a nutshell REST refers to usage of defining principles for developing API, but due to the traditional use of endpoints and HTTP protocols with today’s standard of web applications it falls short based on a bottleneck with the principle of opening and closing connections. This makes WebSockets are more viable choice when seeking performance in being able to send and receive data, and the number of concurrent devices that can do so is a significant consideration in using WebSockets.

Generalizing, WebSockets is a stateful protocol where communication happens over a dedicated TCP connection. On the other hand, HTTP is inherently a stateless protocol. This has an impact on how these will perform with the load but that really depends on the use case. 
Since communication over WebSockets happens over a reusable TCP connection, the overhead per message is lower compared to HTTP, as previously mentioned. Hence this, it can reach a higher throughput per server. But there is a limit to which a single server can scale and that is where WebSockets run into issues. It’s not an easy and or efficient task to horizontally scale applications using WebSockets. HTTP has a clear advantage in this field, since we can scale its overall throughput by adding more servers without impacting the overall performance of the application. 

The same case can be made about AMQP. It's scaling is harder to do from a dev ops perspective, and performance can be impacted quite a bit, depending on how complex the middleware logic for message handling gets. Yet, in the case of actual message sending and communication, here is where AMQP has a leg over both HTTP and Sockets, as it allows for more cases to be covered in the ways we want our messages queued and delivered.

### Use Cases

For the purpose of this demonstration we are going to look at an example on integrating these protocols into Unity, and evaluate their pros and cons based on acceptance criteria. 

##### Case 1 - REST 

As software developers we are quite familiar with the capabilities of the REST API, and the limitations of it, one in particular being dynamicity.

In order to be able to display the required message on our screen we would need to query continuously the API to see if there are any updates, or have a button, which creates a GET() request. However the purpose of the application is to display the information received from the JSON Object as soon as it is sent, therefore this approach does not really pass our acceptance criteria.

##### Case 1.1 - Using JSON

The purpose of this application is to send and receive location data (coordinates), name of the sender and an image as byte array. 
In order to achieve this we will have one phone that acts as a producer and another phone would act as a consumer

On the producer side we capture a photo, enter our name and when we tap the send button, we serialize the information, including the coordinates obtained dependent on the devices location.

In order to transmit this message and display it on another phone we are going to take in consideration the previously mentioned protocols.

The JSON Object we are transferring:

![alt text](https://github.com/cph-ap228/UFO_BlogEntry/blob/master/images/JSON.PNG)

##### Case 1.2 - AMQP and Socket.IO

You might be wondering why didn’t we separate AMQP and Socket.io? The reason is because for completing the acceptance criteria for this case, we are using a very similar approach in the two protocols. 

In order to fulfill the acceptance criteria we are passing the JSON Object in the body and retrieving it on the consumer side. 
Let us demonstrate:

![alt text](https://github.com/cph-ap228/UFO_BlogEntry/blob/master/images/AMQPvsWS.PNG)

The interesting bit in these protocols are the listeners which are “Listening”/waiting for a specific action and when the action has been triggered, the function can trigger an event which in our case would be to display the information on screen.

#### Case 1.3 - AMQP and Socket.IO

This case is an extension to the previous case to demonstrate where one producer sends out a message to multiple or only specific devices. 

We can achieve this by using both protocols, but by using the Socket.io we need to implement logic in order to transmit message to specific consumers. 

AMQP has built-in “identifiers” to fulfill the criteria, where in our opinion this approach surpasses the Socket.io for this purpose.

How can AMQP identify which queues to use/who to send the message to?

We will explain it in two sections, 1. Using the channels 2. Using CorrelationId

##### 1. Channels/Exchange Types

![alt text](https://github.com/cph-ap228/UFO_BlogEntry/blob/master/images/Channels.PNG)


The image above explains how a message is being transmitted from the Producer/Publisher to our Consumer.

<details>
<summary>Exchange Types</summary>
<br>

..* Direct Exchange
![alt text](https://github.com/cph-ap228/UFO_BlogEntry/blob/master/images/DirectExchange.png)

The Direct exchange type routes messages with a routing key equal to the routing key declared by the binding queue.

..* Fanout Exchange
![alt text](https://github.com/cph-ap228/UFO_BlogEntry/blob/master/images/FanoutExchange.png)

The Fanout exchange type routes messages to all bound queues indiscriminately.  If a routing key is provided, it will simply be ignored.

..* Topic Exchange
![alt text](https://github.com/cph-ap228/UFO_BlogEntry/blob/master/images/TopicExchange.png)

The Topic exchange type routes messages to queues whose routing key matches all, or a portion of a routing key.  With topic exchanges, messages are published with routing keys containing a series of words separated by a dot (e.g. “word1.word2.word3”).

..* Headers Exchange
![alt text](https://github.com/cph-ap228/UFO_BlogEntry/blob/master/images/HeadersExchange.png)

The Headers exchange type routes messages based upon a matching of message headers to the expected headers specified by the binding queue.

</details>



##### 2. CorrelationId

The CorrelationId can be defined when publishing a message to an exchange, by using the IAmqpMessageProperties.

![alt text](https://github.com/cph-ap228/UFO_BlogEntry/blob/master/images/IAmqpMessageProperties.PNG)

The CorrelationId can be very useful when we would like to keep a reference of the device that we just received a message from, so that we can communicate back to that exact device if necessary.


### Conclusion

In conclusion for these protocols, for the bulk of the scenarios then, where occasional communication is required with the server, like for example, getting the record of an employee, it’s still sensible to use REST service over HTTP.

WebSockets are more suitable for cases where a push-based and real-time communication defines the requirement more appropriately, saying you’d like to have a newer client-side application with stock-prices, which requires real-time updates on the server, gives much more leverage to using WebSockets. Additionally, WebSockets works better for scenarios where a message needs to be pushed to multiple clients simultaneously, where RESTful services will find it difficult if not prohibitive. 

AMQP can solve these problems and have even more control over how it does, but it takes a different approach than simple socket connections, although it does not fit RESTful services in the same way as them. In short, AMQP needs it's own unique approach when designing with it's middleware broker architecture in mind. But as previously discussed, this can over complicate a solution to a simple problem.

If you want to talk with the world (provide an API for third party usage), HTTP is giving all you need. It is supported, well known and widely used. Combined with the: "You do not have to care if there is a problem in the communications, because it is the duty of the client of your API to execute the request again if something went wrong"-attitude.

If you want to have simple communication between two sources, then sockets should have your back.

If you want to have internal communication, where you control every single request, I would use AMQP, because it is easy to use, supported in most of the languages used nowadays, reliable, scalable and fast.

All three protocols are great, no doubt about that. But only one of them adds reliablity on your communications “out of the box" and that is key, also, only one of them is scalable almost out of the box and the fact that communications are not blocking the services allows you to continue using your resources for other processes. Furthermore, why re-inventing the wheel creating our own reliability process “just because”? Why adding extra code that has to be maintained only because “we can”? We have it clear, if it is asynchronous, use AMQP with RabbitMQ.

It all must be drawn and selected based on requirements. There’s no silver lining but many forget that they might be using the wrong procedure for their specific task and application, essentially wasting resources by trying to achieve the same thing which could be done with a different approach and protocol.

----------------------------------------------------------------------------------------------------------------------------------------

#### Resources
https://www.rabbitmq.com/tutorials/amqp-concepts.html

https://peterdaugaardrasmussen.com/2019/01/24/what-is-the-difference-between-websockets-and-http/

https://dev.to/fedejsoren/amqp-vs-http
