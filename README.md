# python-template

Cookiecutter template for quick setup of Python projects.

## Included
- Package management with pip-tools
- pre-commit hooks
- Linting with flake8, black, isort
- Type Checking with mypy
- Tests with pytest
- CI with Github Actions

## Usage
Install [cookiecutter](https://cookiecutter.readthedocs.io/en/1.7.2/) with [pipx](https://github.com/pypa/pipx)
```bash
$ pipx install cookiecutter
```

Set up a new project with this template
```bash
$ cookiecutter git+ssh://git@github.com/kencx/python-template.git

# pyproject.toml branch
$ cookiecutter git+ssh://git@github.com/kencx/python-template.git -c pyproject.toml
```

### Todo
- Consider `[nox](https://nox.thea.codes/en/stable/)` or tox
- Add Build workflow
