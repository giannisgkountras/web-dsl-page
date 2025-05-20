Conditions are very similar to conditions in imperative programming languages
such as Python, Java, C++ or JavaScript. You can use Entity Attributes in a
condition just like a variable by referencing it in the Condition using
it's Fully-Qualified Name (FQN) in dot (.) notation. They are used to dynamically show or hide components based on the data received from the data sources.

## Condition Formatting:

You can combine two conditions into a more complex one using logical operators but make sure to not forget the parenthesis.

The supported logical operators are:

-   **AND**: Logical AND
-   **OR**: Logical OR

## Condition Examples

Given that we have an entity named `TempSensor1` with attributes `temp`, `humidity` and components named `MyComponent`, `MyOtherComponent` we can use the following conditions:

```
if TempSensor1.temp > 10 and TempSensor1.humidity < 20
    use MyComponent, MyOtherComponent

if 0 > TempSensor1.temp > 10 or TempSensor1.humidity < 20
    use MyComponent
else
    use MyComponent, MyOtherComponent

if TempSensor1.temp > 10
    use MyComponent
else if TempSensor1.temp < 10
    use MyOtherComponent
else
    use MyComponent
```

The supported comparison operators are:

-   **>**: Greater than
-   **<**: Less than
-   **>=**: Greater than or equal to
-   **<=**: Less than or equal to
-   **==**: Equal to
-   **!=**: Not equal to
