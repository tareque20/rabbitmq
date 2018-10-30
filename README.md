
# RabbitMQ
### What is AMQP?
AMQP 0-9-1 (Advanced Message Queuing Protocol) is a messaging protocol that enables conforming client applications to communicate with conforming messaging middleware brokers.

### Brokers and Their Role
Messaging brokers receive messages from publishers (applications that publish them, also known as producers) and route them to consumers (applications that process them).

Since it is a network protocol, the publishers, consumers and the broker can all reside on different machines.

![N|Solid](https://github.com/tareque20/rabbitmq/blob/master/AMQP%20Model.png)
![N|Solid](https://github.com/tareque20/rabbitmq/blob/master/AMQP.png)

## Exchange Types
RabbitMQ provides four types of exchanges: Direct, Fanout, Topic, and Headers.

### Direct Exchanges
The Direct exchange type routes messages with a routing key equal to the routing key declared by the binding queue.  The following illustrates how the direct exchange type works:
![N|Solid](https://github.com/tareque20/rabbitmq/blob/master/DirectExchange.png)

### Fanout Exchanges
The Fanout exchange type routes messages to all bound queues indiscriminately.  If a routing key is provided, it will simply be ignored. The following illustrates how the fanout exchange type works:
![N|Solid](https://github.com/tareque20/rabbitmq/blob/master/FanoutExchange.png)
The Fanout exchange type is useful for facilitating the publish-subscribe pattern.  When using the fanout exchange type, different queues can be declared to handle messages in different ways.  For instance, a message indicating a customer order has been placed might be received by one queue whose consumers fulfill the order, another whose consumers update a read-only history of orders, and yet another whose consumers record the order for reporting purposes.

### Topic Exchanges
The Topic exchange type routes messages to queues whose routing key matches all, or a portion of a routing key.  With topic exchanges, messages are published with routing keys containing a series of words separated by a dot (e.g. "word1.word2.word3").  Queues binding to a topic exchange supply a matching pattern for the server to use when routing the message.  Patterns may contain an asterisk (" * ") to match a word in a specific position of the routing key, or a hash ("#") to match zero or more words.  For example, a message published with a routing key of "honda.civic.navy" would match queues bound with "honda.civic.navy", "*.civic.*", "honda.#", or "#", but would not match "honda.accord.navy", "honda.accord.silver", "*.accord.*", or "ford.#".  The following illustrates how the fanout exchange type works:
![N|Solid](https://github.com/tareque20/rabbitmq/blob/master/TopicExchange.png)

### Headers Exchanges
The Headers exchange type routes messages based upon a matching of message headers to the expected headers specified by the binding queue.  The headers exchange type is similar to the topic exchange type in that more than one criteria can be specified as a filter, but the headers exchange differs in that its criteria is expressed in the message headers as opposed to the routing key, may occur in any order, and may be specified as matching any or all of the specified headers.  The following illustrates how the headers exchange type works:
![N|Solid](https://github.com/tareque20/rabbitmq/blob/master/HeadersExchange.png)

### Default Exchange
The default exchange is a direct exchange with no name (empty string) pre-declared by the broker. It has one special property that makes it very useful for simple applications: every queue that is created is automatically bound to it with a routing key which is the same as the queue name.

For example, when you declare a queue with the name of "search-indexing-online", the AMQP 0-9-1 broker will bind it to the default exchange using "search-indexing-online" as the routing key. Therefore, a message published to the default exchange with the routing key "search-indexing-online" will be routed to the queue "search-indexing-online". In other words, the default exchange makes it seem like it is possible to deliver messages directly to queues, even though that is not technically what is happening.


# RABBITMQ AND SERVER CONCEPTS
Here are some important concepts that need to be described before we dig deeper into RabbitMQ. 

 - **Producer:** Application that sends the messages.
 - **Consumer:** Application that receives the messages.
 - **Queue:** Buffer that stores messages.
 - **Message:** Information that is sent from the producer to a consumer through RabbitMQ.
 - **Connection:** A connection is a TCP connection between your application and the RabbitMQ broker.
 - **Channel:** A channel is a virtual connection inside a connection. When you are publishing or consuming messages from a queue - it's all done over a channel.
 - **Exchange:** Receives messages from producers and pushes them to queues depending on rules defined by the exchange type. To receive messages, a queue needs to be bound to at least one exchange.
 - **Binding:** A binding is a link between a queue and an exchange.
 - **Routing key:** The routing key is a key that the exchange looks at to decide how to route the message to queues. The routing key is like an address for the message.
 - **AMQP:** AMQP (Advanced Message Queuing Protocol) is the protocol used by RabbitMQ for messaging.
 - **Users:** It is possible to connect to RabbitMQ with a given username and password. Every user can be assigned permissions such as rights to read, write and configure privileges within the instance. Users can also be assigned permissions to specific virtual hosts.
 - **Vhost, virtual host:** A Virtual host provides a way to segregate applications using the same RabbitMQ instance. Different users can have different access privileges to different vhost and queues and exchanges can be created, so they only exist in one vhost.

# SRabbitMQ simulator
[Simulator](https://jmcle.github.io/rabbitmq-visualizer/#)



## RabbitMQ
Example with RabbitMQ

## Install RabbitMQ
[Download and install](https://www.rabbitmq.com/download.html)


## Install dependency:
```sh
$ npm install
```

## Install AMPQLib
```sh
$ npm install amqplib
```



```sh





```



# Test Hello World Example
## Run send
```sh
$ npm run send
```
## Run Receive
```sh
$ npm run receive
```

# Test Work Queues
## Run Receive
```sh
$ npm run worker
```
```sh
$ npm run worker
```
## Run send
```sh
$ npm run new_task "First message."
$ npm run new_task Second message..
$ npm run new_task Third message...
$ npm run new_task Fourth message....
$ npm run new_task Fifth message.....
```

# Test Publish and Subscribe
## Run send
```sh
$ npm run pub
```
## Run Receive
```sh
$ npm run sub
```

# Test Routing
## Run Receive
```sh
$ npm run sub-direct info warning error
```
## Run send
```sh
$ npm run pub-direct info "Info will explode."
$ npm run pub-direct error "Run. Run. Or it will explode."
```

# Test Topics
## Run Receive
```sh
$ npm run sub-topic "#"
```
```sh
$ npm run sub-topic "kern.*"
```
```sh
$ npm run sub-topic "*.critical"
```
```sh
$ npm run sub-topic "kern.*" "*.critical"
```
## Run send
```sh
$ npm run pub-topic "kern.critical" "A critical kernel error"
$ npm run pub-topic "Info" "This is info message"
```
