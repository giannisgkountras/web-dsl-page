WebDSL also supports transforming OpenAPI specifications into WebDSL models using the openapi subcommand of the webdsl CLI tool. This transformation automatically generates the necessary components, entities, and data sources based on the provided OpenAPI specification. The resulting model can then be used to generate the full application source code.

By default, the transformation extracts the API connection details and creates a separate data source for each endpoint defined in the OpenAPI spec.

## Augmenting OpenAPI with WebDSL

WebDSL allows you to enhance the OpenAPI specification by using a custom header on specific endpoints. You can add the following annotation to generate UI components:

```yaml
x-webdsl:
    - this.id -> Gauge @ 1,1
    - this[0].title -> Text @ 1,2
```

In this example:

A Gauge component will be generated from the id field of the response.

A Text component will be generated from the title field of the first item in the response array.

The @ 1,1 and @ 1,2 specify the row and column positions of the components (1-indexed).

To transform an OpenAPI specification into a WebDSL model, execute:

```bash
webdsl openapi <openapi_file> <output_dir>
```

If the OpenAPI file is valid, the generated WebDSL model will be placed in the specified output directory. If no output dir is provided, the code will be generated in the current directory.
