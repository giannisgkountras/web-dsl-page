Entities are used to define data models and their relationships with data sources. They are defined using the following syntax:

```
Entity EntityName
    description: 'Description of the entity'
    source: <DataSourceName>
    strict: true
    interval: 5000
    attributes:
        - attribute_name: attribute_type
end
```

-   **description**: A description of the entity,
-   **source**: The name of the data source to use
-   **strict**: When set to true, the entity only accepts data that matches its defined attributes exactly. Any undefined attributes will be rejected, and references to non-existent attributes will result in a validation error. When false, the entity can accept additional, undefined attributes without error.
-   **interval**: The interval in milliseconds for the entity to reload data from the data source. This is optional and can be used to set a custom interval for the entity in case of rest apis and databases.
-   **attributes**: A list of attributes for the entity. Each attribute has a name and a type.
-   **attribute_name**: The name of the attribute
-   **attribute_type**: The type of the attribute. The supported types are int, float, string, bool, list and dict.

## Entity Overloading

Entity overloading is a feature that allows you to a new entity that will replace an existing entity everywhere in the model. This is useful when you want to change the behavior of an entity without having to change all the references to it.

```
Entity NewEntityName overloads OldEntityName
    description: 'Description of the entity'
    source: <DataSourceName>
    strict: true
    interval: 5000
    attributes:
        - attribute_name: attribute_type
end
```
