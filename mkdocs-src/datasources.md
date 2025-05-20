Data sources are the specific endpoints, queries or topics that are used to retrieve or send data. They are defined using the following syntax:

-   For message brokers:

```
BrokerTopic TopicName
    connection: <BrokerName>
    topic: 'my/topic'
end
```

-   **connection**: The name of the connection to the message broker
-   **topic**: The topic to subscribe or publish to

-   For databases:

```
MySQLQuery MyQueryName
    connection: <DatabaseName>
    query: 'SELECT * FROM mytable'
end

MongoDBQuery MyQueryName
    connection: <DatabaseName>
    collection: 'mycollection'
    filter: '{"field": "value"}'
end
```

-   **connection**: The name of the connection to the database
-   **query**: The SQL query to execute (for MySQL)
-   **collection**: The name of the collection to query (for MongoDB)
-   **filter**: The filter to apply to the query (optional for MongoDB)

-   For REST APIs:

```
RestEndpoint EndpointName
    connection: <RestApiName>
    path: '/api/v1/resource'
    method: 'POST'
    body: {"key": "value"}
    params: {"param1": "value1", "param2": "value2"}
```

-   **connection**: The name of the connection to the REST API
-   **path**: The path of the endpoint
-   **method**: The HTTP method to use (GET, POST, PUT, DELETE), if not specified, GET is used
-   **body**: The body of the request (for POST and PUT), optional
-   **params**: The query parameters to include in the request, optional
