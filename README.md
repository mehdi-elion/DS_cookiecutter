# DS_cookiecutter
A cookiecutter template for Data Science Projects

## Introduction
This is a data science cookiecutter template. This page serves as a guide through the whys and wherefores of this template, as well as the different steps to execute in order to use it.

<!-- <p align=center>
    <img src="/images/data_logo_full_black.png"  height="100">
</p> -->

## Why this template ?
When tackling a lot of data projects every developer has their own coding style and habits; which can also vary from one project to the other.
Most of the time this results in:
* heterogeneous codebases
* harder onboarding and handovers
* harder code maintenance

Therefore, this template is a **a way to homogenize and enforce coding standards across data-related projects**.


## What is in this template ?
This template proposes the following repository structure.

```console
├── conf/          <-- store project config
│   ├── base/         <-- contains metadata & params used from the code
│   └── local/        <-- [gitignored] must contain secrets & credentials
├── data/             <-- store data & models depending or project layers
│   ├── 01_raw/
│   ├── 02_intermediate.ext
│   ├── 03_primary
│   ├── 04_feature
│   ├── 05_model_input
│   ├── 06_models
│   ├── 07_model_output
│   └── 08_reporting
├── notebooks/       <-- for notebooks only
│   ├── 01_my_notebook.ipynb
│   └── ...
├── src/             <-- code devided into "project" and "test" folders
│   ├── project/
│   ├── test/
│   ├── environment.yml
│   └── requirements.txt
├── .gitignore
├── .flake8
├── pyproject.toml
├── pre-commit-config.yaml
├── azure-pipelines.yml
└── README.md
```

Each folder has a dedicated role, as displayed above.
Various configuration files are available at the root of the directory:
* `.gitignore` specifies which folders and files must be untracked
* `.flake8` specifies settings for flake8-based linting
* `pyproject.toml` specifies other linting params
* `pre-commit-config.yaml` defines the pre-commit pipeline
* `azure-pipelines.yml` defines CI/CD pipelines (by default, pre-commits; possibly testing and git mirroring in addition to that)


By following this organization, all data project will be structured the same way, thus enabling:
* homogeneity over codebases
* easier onboarding and handovers
* better code modularity & maintainability



## How to use this template ?
When you need to initiate a new project or fill an empty repo with the above-described structure, you must:

1) Install cookiecutter by running : ```pip install cookiecutter```
2) Apply cookiecutter to this template :
```console
cookiecutter https://github.com/mehdi-elion/DS_cookiecutter.git
```

This will display a series of prompts which must be answered to define the python environment, the name of the project, etc...
Note that default values are between brackets; they will be used if you press enter before typing anything.

<!-- <p align=center>
    <img src="images/cookicutter_prompt.png"  height="100">
</p> -->

Once it's done, the project is created where you typed the command with the prompted values used within it (e.g. specified python environment in `environment.yml`)

<!-- <p align=center>
    <img src="images/proj_created.png"  height="100">
</p> -->

Here is an example of the `environment.yml` intiated with cookiecutter.
<!-- <p align=center>
    <img src="images/example_env_yml.png"  width="800">
</p> -->


## Resources
For more details about cookiecutter template, please refer to [Cookicutter's documentation](https://cookiecutter.readthedocs.io/en/stable/)
