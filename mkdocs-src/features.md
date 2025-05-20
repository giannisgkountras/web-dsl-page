-   **Declarative Syntax**: Define data sources, entities and components and their relationships in a clear and concise manner.
-   **Extensible**: Easily add custom logic and components to fit your specific use case.
-   **Human-Readable**: Applications are defined in a way that is easy to understand and maintain.

Currently the DSL supports the following types of data sources:

-   **Message Broker**: MQTT, AMQP, Redis
-   **REST API**: REST API
-   **Database**: MongoDB, MySQL
-   **Static**: Static data

And the following types of components:

-   **Text**: Displays static or dynamic text content
-   **Image**: Renders an image from a given source
-   **Bar Chart**: Visualizes data using a bar chart
-   **Line Chart**: Visualizes trends over time with a line chart
-   **Pie Chart**: Displays proportional data in a pie chart format
-   **Table**: Shows structured data in a tabular format, allowind CRUD operations
-   **Live Table**: Real-time table that updates as new data arrives
-   **Form**: Collects user input and submits it to a data source
-   **Notification**: Displays alerts or status messages
-   **Gauge**: Represents a single numeric value within a range
-   **JSON Viewer**: Formats and displays JSON data for readability
-   **Alive Status**: Indicates the active status of a broker topic
-   **Publisher**: Sends messages to a broker topic
-   **Logs**: Displays real-time log messages from broker topics
-   **Progress Bar**: Visual indicator of progress
