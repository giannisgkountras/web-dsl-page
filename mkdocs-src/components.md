Components are used to define the visual representation of the data. They are defined using the following syntax:

```
Component ComponentName
    type: <ComponentType>
    entity: <EntityName>
end
```

-   **type**: The type of the component.
-   **entity**: The name of the entity to use. If not specified, the component should have static data.

After declaring a component you can use it in any screen by referencing it by its name.

```
use ComponentName
```

You can also declare a component inline in a screen. This is useful when you want to use a simple component only in one screen and not in the whole application.

# Component Types

There are many component types available in the DSL. They all have a common way to access the data from the entity. The data is accessed using the **accessors** that have this syntax: `this.attribute_name[array_index]...`
For example:

-   `this.temp[0]` will access the first element of the `temp` attribute of the entity.
-   `this.temp[0].value` will access the value of the first element of the `temp` attribute of the entity.
-   `this[0].data` will access the data of the first element of the entity.

For components that support static data, the syntax is different. The data is provided by strings or lists. More details on each component type.

Currently the DSL supports the following component types:

## Text

```
Text
    content: <accessor> | "static text"
    size: 24
    color: "#fff"
    weight: "600"
```

-   **content**: The content of the text. It can be a string or an accessor.
-   **size**: The font size of the text.
-   **color**: The color of the text in hex string.
-   **weight**: The font weight of the text.

## Image

```
Image
    source: <accessor> | "static image"
    width: 100
    height: 100
```

-   **source**: The source of the image. It can be a string or an accessor.
-   **width**: The width of the image.
-   **height**: The height of the image.

## Bar Chart

```
BarChart
    description: "Description of the chart"
    xLabel: "Label for x axis"
    yLabel: "Label for y axis"
    xValue: <accessor> | "static x value"
    yValues: <accessor>, <accessor>... | "static y value", "static y value"...
    staticData: [ {...}, {...} ]
```

-   **description**: The description of the chart.
-   **xLabel**: The label for the x axis.
-   **yLabel**: The label for the y axis.
-   **xValue**: The x value of the chart. It can be a string or an accessor.
-   **yValues**: The y values of the chart. It can be strings or an accessors seperated by commas.
-   **staticData**: The static data of the chart. It can be a list of dictionaries.

## Line Chart

```
LineChart
    description: "Description of the chart"
    xLabel: "Label for x axis"
    yLabel: "Label for y axis"
    xValue: <accessor> | "static x value"
    yValues: <accessor>, <accessor>... | "static y value", "static y value"...
    staticData: [ {...}, {...} ]
```

-   **description**: The description of the chart.
-   **xLabel**: The label for the x axis.
-   **yLabel**: The label for the y axis.
-   **xValue**: The x value of the chart. It can be a string or an accessor.
-   **yValues**: The y values of the chart. It can be strings or an accessors seperated by commas.
-   **staticData**: The static data of the chart. It can be a list of dictionaries.

## Pie Chart

```
PieChart
    description: "Chart title or description"
    dataName: <accessor> | "static label key"
    value: <accessor> | "static value key"
    staticData: [ {...}, {...} ]
```

-   **description**: The description of the chart.
-   **dataName**: The key for each slice label, as accessor or static string.
-   **value**: The key for each slice value, as accessor or static string.
-   **staticData**: The static data of the chart. It can be a list of dictionaries.

## Table

```
Table
    primary_key: "id"
    attributes: <accessor>, <accessor>, ...
    description: "Optional table description"
    table: "collection_or_table_name"
    crud: true
```

-   **primary_key**: The primary key of the table.
-   **attributes**: The data fields to display. It can be a list of accessors. Optional, if not specified, all attributes of the entity will be displayed.
-   **description**: The description of the table.
-   **table**: The name of the table or collection to use. Optional, for use with databases
-   **crud**: If true, the table will support CRUD operations. This is supported only for databases.

## Live Table

```
LiveTable
    columns: <accessor>, <accessor>, ...
```

-   **columns**: The data fields to display. It can be a list of accessors. Optional, if not specified, all attributes of the entity will be displayed.

## Form

```
Form
    description: "Form description"
    elements:
        Label "Your name"
        Input
            type: text
            placeholder: "Enter name"
            datakey: "username"
            required: true
```

-   **description**: The description of the form.
-   **elements**: The elements of the form. It can be a list of elements. Each element can be a label or input.
-   **Label**: The label of the element.
-   **Input**: The input of the element. It can be a text, number, email, password or checkbox.

## Notification

```
Notification
    type: success | error | warning | info
    message: <accessor>
```

-   **type**: The type of the notification. It can be success, error, warning or info.
-   **message**: The message of the notification. It can be an accessor.

## Gauge

```
Gauge
    value: <accessor> | 0.5
    description: "Battery level"
```

-   **value**: The value of the gauge. It can be an accessor or a static value.
-   **description**: The description of the gauge.

## JSON Viewer

```
JsonViewer
    attributes: <accessor>, <accessor>, ...
```

-   **attributes**: The keys to display. It can be a list of accessors. Optional, if not specified, all attributes of the entity will be displayed.

## Alive Status

```
Alive
    timeout: 5000
    description: "Sensor alive status"
```

-   **timeout**: The timeout in milliseconds. If the data source does not send data for this time, it will be considered dead.
-   **description**: The description of the alive status.

## Publisher

```
Publish
    broker: <broker_ref>
    endpoint: <endpoint_ref>
    topic: "topic/name"
    json: '{"command": "start"}'
    description: "Send start signal"
```

-   **broker**: The name of the broker to use.
-   **endpoint**: The name of the endpoint to use.
    Either the broker or the endpoint is required.
-   **topic**: The topic to publish to. If not specified, the publisher will have an input field to enter the topic.
-   **json**: The JSON payload to send. If not specified, the publisher will have an input field to enter the payload.
-   **description**: The description of the publisher.

## Logs

```
Logs
    attributes: <accessor>, <accessor>, ...

```

-   **attributes**: The keys to display. It can be a list of accessors. Optional, if not specified, all attributes of the entity will be displayed.

## Progress Bar

```
Progressbar
    value: <accessor> | 0.4
    max: <accessor> | 100
    description: "Loading progress"
    barColor: "#00FF00"
    textColor: "#000000"
    trackColor: "#CCCCCC"
```

-   **value**: The value of the progress bar. It can be an accessor or a static value.
-   **max**: The maximum value of the progress bar. It can be an accessor or a static value.
-   **description**: The description of the progress bar.
-   **barColor**: The color of the progress bar. It can be a hex string.
-   **textColor**: The color of the text. It can be a hex string.
-   **trackColor**: The color of the track. It can be a hex string.
