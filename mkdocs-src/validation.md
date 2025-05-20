Validation is perfomed using either the CLI or the REST API of the DSL.

In the case of the CLI, `validate` is a subcommand of `webdsl`.

To validate a WebDSL model file, execute:

```bash
webdsl validate <webdsl_file>
```

If the model passes the validation rules (grammar) you should see something
like:

```bash
✔ Model is valid.
```
