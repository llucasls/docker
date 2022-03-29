In order to build a container using `mysql.yml` file:
```
docker-compose -f mysql.yml up -d
```

For mysql in particular, there are a few comands to make it easier to use on the
command line. First, edit the password on `mysql.yml` to one of your liking,
then execute the command below on your terminal. It will prompt you for your
password.
```
docker container exec -it mysql mysql_config_editor set -u root -p
```
Then, paste the following function in your `.bashrc` or `.zshrc` file.
```
mysql() {
	docker container exec -it mysql mysql "$@"
}
```
There. Next time you open up a terminal, just type in `mysql` and you're good to
go.
