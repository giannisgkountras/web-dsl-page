Loops are used to iterate over a list of elements coming from the live data source. They are used to dynamically show or hide components based on the data received from the data sources. Loops currently support only the Text, Image and Gauge components.

## Loop Formatting:

You can use the following syntax to define a loop:

```
for item in <entity_name>.<attribute_name>
    use Text with item.value
    orientation: column
```

-   **orientation**: The orientation of the loop. It can be column or row.
-   **with**: The data accessor to use with the item. It needs to start with `item` and follows the accessor logic. If not specified, the component should have static data.

There can also be if statements inside the loop to show only a part of the data based on a condition. This condition is simpler than the one used in the conditions section. You can use the following syntax to define a condition inside a loop:

```
for item in CarData.metrics
    use Gauge with item.value if item.value > 30
    else use Text content:"Low Value"
    orientation: column
```
