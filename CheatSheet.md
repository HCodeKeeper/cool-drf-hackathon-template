# CheatSheet

### Wsl start service
`sudo service postgresql start`

### Postgres
`psql -U postgres -h host_name [-d database_name]`

OR

`sudo -u postgres psql postgres`

#### psql:
`\l` to list dbs

`\d` to list tables

`\?` manual

#### Create db
`createdb db1`

### Poetry

install poetry

! Poetry doesnt download python version, instead it uses already installed in your path which version is => version in pyproject

#### commands
`poetry install` to sync pyproject dependencies with venv (poetry handles venv creation itself)
`poetry run` proxy to run any command via poetry venv
`poetry add` to install new dependency
There is no command to install everything from .txt, unfortunately

