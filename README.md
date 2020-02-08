# cookiecutter-environment

This repository serves as provisioner for cookiecutter projects. It utilizies following tools:
* python3
* vagrant
* ansible
* docker
* docker-compose
* postgreSQL
* nginx (TODO)
* uWSGI (TODO)
* kitchenCI (TODO)

How it works:
* vagrant sets up virtual machine
* virtual machine is provisioned with ansible
* ansible install all required dependencies (pip, docker, docker-compose, cookiecutter)
* cookiecutter role initializes project, sets up postgres database and starts docker-compose

## Dependecies

Make sure that you have Vagrant and virtualenv installed

## Usage

By default this provisioner will set up [cookiecutter-flask](https://github.com/cookiecutter-flask/cookiecutter-flask.git) project. In order to set up different one, pass `cookiecutter_project`, `cookiecutter_project_name` variables to `vars/main.yml` file and provide `docker-compose.yml` (possibly with postgres service).

```shell
virtualenv -p python3.8 venv
pip install -r requirements.yml

vagrant up

curl localhost:5000
```

## Encountered issues and TODOS

`docker-compose` throws an error during play after `up` command but app is still served on `5000` port.
TODO - investigate this issue and come up with fix

TODO - create github issues for each TODO:
- nginx
- uWSGI
- kitchenCI tests

## Testing
