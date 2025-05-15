# adpro-module9-publisher

### 1. How much data your publisher program will send to the message broker in one run?

My publisher program can send five messages to the message broker in one run. Each of these messages is a `UserCreatedEventMessage` that includes two string fields: `user_id` and `user_name`. The total amount of data transferred corresponds to the combined size of the five messages. 

### 2. The URL “amqp://guest:guest@localhost:5672” being the same in both the publisher and subscriber programs means they are connected to the same RabbitMQ message broker.

The URL specifies the protocol (`amqp`), username and password(`guest:guest`), and the address of the broker (`localhost:5672`, which includes the default port for RabbitMQ). By using the same connection URL, both the publisher and subscriber operate within the same message environment. This ensure that any message published by the publisher to a queue or exchange on the broker can be received and processed by the subscriber listening on the same broker instance. 

![alt text](images/image.png)
![](images/publisher.png)
![](images/subscriber.png)

When I run `cargo run` in the publisher, it connects to the RabbitMQ message broker and publishes five `UserCreatedEventMEssage` instances to the `user_created` queue, each containing unique user information. On the subscriber side, it connects to the same broker and sets it up to listen for messages on that same queue. As soon as the events are published, subscriber receives them in real time and outputs the details of each message to the console. 