# adpro-module9-publisher

### 1. How much data your publisher program will send to the message broker in one run?

My publisher program can send five messages to the message broker in one run. Each of these messages is a `UserCreatedEventMessage` that includes two string fields: `user_id` and `user_name`. The total amount of data transferred corresponds to the combined size of the five messages. 

### 2. The URL “amqp://guest:guest@localhost:5672” being the same in both the publisher and subscriber programs means they are connected to the same RabbitMQ message broker.

The URL specifies the protocol (`amqp`), username and password(`guest:guest`), and the address of the broker (`localhost:5672`, which includes the default port for RabbitMQ). By using the same connection URL, both the publisher and subscriber operate within the same message environment. This ensure that any message published by the publisher to a queue or exchange on the broker can be received and processed by the subscriber listening on the same broker instance. 