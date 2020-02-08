# cookiecutter-environment

This repository serves as provisioner for cookiecutter projects


## Dependecies

Make sure that you have Vagrant and virtualenv installed

## Usage

By default this provisioner will set up [cookiecutter-flask](https://github.com/cookiecutter-flask/cookiecutter-flask.git) project. In order to set up different one, pass `cookiecutter_project` and `cookiecutter_project_name` variables to `vars/main.yml` file.

```shell
virtualenv -p python3.8 venv
pip install -r requirements.yml

vagrant up
```

## Testing
