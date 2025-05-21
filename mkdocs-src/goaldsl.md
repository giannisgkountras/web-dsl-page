WebDSL also supports transforming [GoalDSL](https://github.com/robotics-4-all/goal-dsl) into WebDSL models. To transform a GoalDSL model into a WebDSL model, execute:

```bash
webdsl transform goaldsl <goal_dsl_file> <output_file>
```

If the GoalDSL file is valid, the generated WebDSL model will be placed in the specified output directory with the specified file name. If no output dir is provided, the code will be generated in the current directory.
