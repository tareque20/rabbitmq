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


