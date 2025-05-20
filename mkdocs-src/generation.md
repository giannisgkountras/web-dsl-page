Code generation is perfomed using either the CLI or the REST API of the DSL.

In the case of the CLI, `generate` is a subcommand of `webdsl`.

To generate the source code of a WebDSL model, execute:

```bash
webdsl generate <webdsl_file> <output_dir>
```

The generated code will be placed in the specified output directory. If no output dir is provided, the code will be generated in the current directory.
