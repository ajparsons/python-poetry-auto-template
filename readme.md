# Python project template

This template repository can be used to create a new repository with the skeleton of a poetry-based Python library.

This is based on the general approach of [simonw/python-lib](https://github.com/simonw/python-lib), but with a different default structure. 

# Creating a new template

A new repository based on this template can be created in Github or through cookiecutter.

## Templating in GitHub

The templating process can be run entirely in GitHub to create a new repository. 

Start here: https://github.com/ajparsons/poetry-auto-template/generate

Add a one-line description of your repository, then click "Create repository from template".

# Templating with cookiecutter

This repo can also be used to set up a template offline using [cookiecutter](https://cookiecutter.readthedocs.io/en/stable/). To start the processs:

```
python -m cookiecutter https://github.com/ajparsons/poetry-auto-template/
```

## Features
 
The default package uses:

* [poetry](https://python-poetry.org/) for package management,
* [pytest](https://docs.pytest.org/en/7.1.x/) for testing,
* [black](https://black.readthedocs.io/en/stable/) for linting,
* [pyright](https://github.com/microsoft/pyright) for typechecking. 

New repositories include config files and Dockerfile for developing in VS Code or Codespaces, so the development process can happen end to end in Github. (Or not! Will still worked cloned locally). 

The test suite contains meta tests for alignment between the `__version__` of the package and the poetry version, and that the current version is documented in the change log. 

The template version includes a default GitHub Action for testing on Python 3.8-3.10, and publishing to pypi.

By default, the test action requires pytest, black and pyright to return no errors.

The default licence is the MIT Licence. Change if needed. 

# Publishing the package

* Set a GitHub Actions secret for PYPI_TOKEN. 
* For the initial publish. In the Actions tab for a repo, trigger a manual workfork flow with the 'force to pypi' box ticked.
* Subsequently, if the poetry version is bumped and all tests pass - the GitHub Action will automatically publish on push to the main branch.
