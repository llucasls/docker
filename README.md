If you just installed docker on your machine, you'll want to add your user to
the docker group:
```sh
sudo groupadd docker
sudo usermod -aG docker $USER
```

In order to build a container using `mysql.yml` file:
```sh
docker-compose -f mysql.yml up -d
```

When building the mysql container, set a value for the $MYSQL_PASSWORD
environment variable. If you wish to use mysql without being prompted for a
password every time, use the following command:
```sh
docker container exec -it mysql mysql_config_editor set -u root -p
```
After creating the containers, the scripts scripts on the `bin/` directory will
serve as if you had the binaries themselves installed locally, if you add them
to your $PATH. However, for reading scripts you will have to redirect the
standard input.
```sh
mysql < query.sql  # It will use mysql to execute a query
mysql query.sql    # It is likely to fail
```
The second one will look for the file inside the container's working directory,
instead of your current directory.
