# rjbrown99/rpi-alpine-mariadb

Multiple purpose MariaDB/MySQL based on Alpine for the Raspberry Pi

Image is based on the [k0st/alpine-mariadb](https://hub.docker.com/r/k0st/alpine-mariadb/) container.

## Docker image usage

```
docker run [docker-options] rjbrown99/rpi-alpine-mariadb 
```

Note that MySQL root will be randomly generated (using pwgen). 
Root password will be displayed, during first run using output similar to this:
```
[i] MySQL root Password: XXXXXXXXXXXXXXX
```

But you don't need root password really. If you connect locally, it should not 
ask you for password, so you can use following procedure:
```
docker exec -it mariadb_containerid /bin/sh
# mysql -u root mysql
```

## Examples

Typical usage:

```
docker run -it -v /host/dir/for/db:/var/lib/mysql -e MYSQL_DATABASE=db -e MYSQL_USER=user -e MYSQL_PASSWORD=blah k0st/alpine-mariadb
```

### Todo
- [ ] Check volume and data
- [ ] Provide more examples
