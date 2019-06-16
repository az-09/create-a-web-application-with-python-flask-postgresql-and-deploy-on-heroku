
To activate virtualenv
source env.sh

pip freeze > requirements.txt

mkdir -p postgres
docker run --rm --name pg-flask -d -p 5432:5432 -v postgres:/var/lib/postgresql/data postgres
docker exec -it pg-flask psql -U postgres
postgres=# CREATE DATABASE books_store;
postgres-# CREATE USER myname WITH ENCRYPTED PASSWORD 'myname';
postgres-# GRANT ALL PRIVILEGES ON DATABASE books_store TO myname;
postgres-# \q
