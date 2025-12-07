# letta-docker-compse

A project to run letta in docker locally with a local running postgres database and odoo server.

## setting up the database

```bash
psql -U $POSTGRES_USER postgres -c "CREATE DATABASE letta OWNER $POSTGRES_USER"

sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -sc)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'

wget -q https://www.postgresql.org/media/keys/ACCC4CF8.asc -O- | sudo apt-key add -

sudo apt update

sudo apt install postgresql-14-pgvector

psql -U $POSTGRES_USER letta -c "CREATE EXTENSION vector"
```

## setting up the pip

if letta-client is installed in you environment, delete it

```python
pip uninstall letta-client -y
```

and install the fix pull request

```bash
pip install git+https://github.com/apexive/letta-python.git@main
```

With these configurations you can use letta mcp server with odoo and keep the memory of your chat.
