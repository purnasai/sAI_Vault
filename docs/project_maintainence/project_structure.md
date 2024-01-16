These are the some points that I noticed in my past experience in Data science life cycle with projects.

### Cookie cutter
- Every project/client/Organization should have a Standard Template of Repo/Folder like a Cookie-Cutter. Cookie-Cutters comes with Standard Folder structure with 
    - Depedency management tool- poetry,pip.
    - logging
    - Continous integration - ci/cd through git actions.
    - pre-commit check
    - Code linters & formaters- ruff
    - Code security- bandit
    - Testing
    - Documentation
    - containers

    and more. Reference repo at current time [here](https://github.com/fpgmaas/cookiecutter-poetry)

### Documentation
- Document the Architecture, packages selected, run times, metrics, logs and more at the end of every project.

### Sample ML folder structure

- input
    - train.csv
    - test.csv
- src
    - create_folds.py
    - train.py
    - inference.py
    - models.py
    - config.py
    - model_dispatcher.py
- models
    - model_rf.bin
    - model_et.bin
- tests
    - test_train.py
    - test_models.py
    - test_inference.py
- notebooks
    - exploration.ipynb
    - check_data.ipynb
- README.md
- LICENSE

### Extensions
- Adding Extensions to your Coding IDE, makes life easier. VSCode Extensions
    - Tree - for TODO in vs code
    - Mintlify - to add automatic Class documentation
    - Better Comments
    - vscode-pdf
    - Excel Viewer
    
    and more

### Multi-Processing
- Multi-threading, multi-processing, using joblib, is always a learning curve to improve the speed up of a process.
- Celery 

### Type-checking
- Also called as Type-checking/Type-hinting. This helps us to better understand about the inputs/outputs that goes into/out of a fuction.

<p align="center" width="100%">
    <img width="40%" src="../imgs/type_checking.png"></img>
</p>

### Exception-handling
- Exception handling is must and always handy.

### Parquet
- using parquet(instead of csv/json/numpy/pickle) file comes with less storage size & quick redability

### Multiplexers
- Terminal multiplexers like Tmux([cheatsheet](https://tmuxcheatsheet.com/)), Screen(same as tmux) are very useful to run multiple operations at same time.

```cmd
tmux ls
tumx new-session -s ray_llm for new-session
tmux attach-session -t ray_llm for attach-session
ctrl+b d to detach session
```

###