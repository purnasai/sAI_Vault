These are the some points that I noticed in my past experience in Data science life cycle with projects.

**Best project leads to best product**:
- Using these below mentioned tools/Concepts for **Best Practices** make a Best Project, leads to **Best product**.

### Cookie cutter
- Every project/client/Organization should have a Standard Template of Repo/Folder like a Cookie-Cutter. Cookie-Cutters comes with Standard Folder structure with 
    - Depedency management tool- poetry,pip.
    - Logging
    - Continous integration - ci/cd through git actions.
    - Pre-commit check
    - Code linters & formaters- ruff
    - Code security- bandit
    - Testing - pytest
    - Documentation-mkdocs
    - Containerization - docker

    and more. Reference repo at current time [here](https://github.com/fpgmaas/cookiecutter-poetry)

### Documentation
- Documentation is very important in a project. Documenting each and every step, idea,scope, issues would help any individual to quickly understand the project in detail. One should Document the 
- Project overview
- Development setup guide
- Architecture
- Packages & configurations
- Code
- Database schema
- Run times 
- Metrics
- Logs
- Risk rigestor
    - A document used to record and track identified risks throughout the project lifecycle, including their likelihood, impact, and mitigation strategies.
- Testing Documentation
- Deployment Documentation
- Code style guide
    - coding standards and best practices to maintain consistency across the codebase.
- Security documentation
    - like any security concerns, vulnerabilities.
- and more at the end of every project.


### Sample ML folder structure

```
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
```

### VS Code IDE Extensions
- Adding Extensions to your Coding IDE, makes life easier.
    - Better comments by aaron bond
    - dev containers by microsoft
    - docker by microsoft
    - [draw.io](http://draw.io) integration henning dieterichs
    - Excel viewer grapecity
    - github actions by github
    - Markdown preview enhanced by yiyi wang
    - powershell by microsfot.
    - remotes-ssh by microsoft.
    - vscode-pdf by tomoki1207
    - Tree - for TODO in vs code
    - Mintlify - to add automatic Class documentation    
    and more

### Multi-Processing
Use of Multi-threading, multi-processing concepts for parallization shows project efficient usage in using all avaible resources. 

I have seen Companies loosing millions due to not using A100 GPUs efficiently(I mean parallelization.) we can reduce the Computing costs heavily.

Refer complete Notes on Multiprocessing [here](https://purnasai.github.io/sAI_Vault/python/multithread_multiprocess/)
