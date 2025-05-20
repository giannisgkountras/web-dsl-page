Connections are the way to connect to a data source. They are defined using the following syntax:

## For message brokers

```
Broker<MQTT> HomeMQTT
    host: 'localhost'
    port: 1883
    auth:
        username: ''
        password: ''
end

Broker<Redis> LocalRedis
    host: 'localhost'
    port: 6379
    db: 0
    auth:
        username: ''
        password: ''
end

Broker<AMQP> MyAMQPBroker
    host: 'localhost'
    port: 5672
    vhost: '/'
    auth:
        username: ''
        password: ''
end
```

-   **host**: Host IP address or hostname for the Broker
-   **port**: Broker Port number
-   **auth**: Authentication credentials. Unified for all communication brokers
    -   **username**: Username used for authentication
    -   **password**: Password used for authentication
-   **vhost (Optional)**: Vhost parameter. Only for AMQP brokers
-   **db (Optional)**: Database number parameter. Only for Redis brokers

**If at least one message broker is used, there must also be defined a websocket connection, that is used to connect the frontend with the backend. Only one websocket connection is needed for each application.**

```
Websocket MyWebsocket
    host: '0.0.0.0'
    port: 8000
end
```

-   **host**: Host IP address or hostname for the Websocket
-   **port**: Websocket Port number

## For databases

```
Database<MongoDB> HomeMongoDB
    host: 'localhost'
    port: 27017
    database: 'mydb'
    auth:
        username: ''
        password: ''
end

Database<MySQL> HomeMySQL
    host: 'localhost'
    port: 3306
    database: 'mydb'
    auth:
        username: ''
        password: ''
end
```

-   **host**: Host IP address or hostname for the database
-   **port**: Database Port number
-   **database**: Database name
-   **auth**: Authentication credentials. Unified for all databases

    -   **username**: Username used for authentication
    -   **password**: Password used for authentication

## For REST APIs

```
RestApi MyRestApi
    host: 'http://localhost'
    port: 8000
    headers: {"Authorization": "Bearer token"}
end
```

-   **host**: The url of the REST API
-   **port**: The port of the REST API
-   **headers**: Headers to be sent with the request. This is optional and can be used to send authentication tokens or other headers.

**If at least one REST API or database is used, there must also be defined an API connection, that is used to connect the frontend with the backend. Only one API connection is needed for each application.**

```
API MyAPI
    host: '0.0.0.0'
    port: 8000
end
```

-   **host**: Host IP address or hostname for the API
-   **port**: API Port number

**Authentication between the frontend and the backend is automatically handled by the DSL. The frontend will automatically send the authentication token to the backend, and the backend will automatically validate the token. This is done for both the Websocket and the API connections. Also, all the information of the connections are stored in the backend.**
