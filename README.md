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

# Test Tpics
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
# RabbitMQ
[![N|Solid](https://github.com/tareque20/rabbitmq/blob/master/AMQP.png)]

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

