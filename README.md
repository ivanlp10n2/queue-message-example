# Queue message example
Messaging communication between two applications with Kafka.

## Building idea
A spring boot application stores information in MariaDB and pushes events to a Queue (Kafka). 
<BR>
Another spring boot application will be listening the topic and store event in Cassandra.

- producer : spring boot with API for execute actions.
- prod_db : stores in mariadb.
- kafka : messaging queue with topics for publish and subscribe.
- consumer: spring boot consumer of kafka topic and saves in cassandra.
- consumer_db : stores in cassandra.

## API
All the endpoints are HTTP secured with basic auth.
```
username: root
password: root 
```

#### Endpoints:
**Save event and push to kafka**
```
POST /event/start
Payload : { 
    "message" : string 
} 
```

**Shutdown procedure built-in with actuators**
```
POST /actuator/shutdown
```
