# Cassandra on Container
This image is based on [cassandra 2.2.8](https://github.com/docker-library/cassandra/blob/master/2.2/Dockerfile).

I add `cassandra.yaml` to enable set user with password.


## Troubleshooting
* `ERROR 06:11:55 Exception encountered during startup: Unknown listen_address '::1 127.0.0.1'`
This is caused by bellow script in `[docker-entrypoint.sh](https://github.com/docker-library/cassandra/blob/master/2.2/docker-entrypoint.sh)`:
```
if [ "$CASSANDRA_LISTEN_ADDRESS" = 'auto' ]; then
    CASSANDRA_LISTEN_ADDRESS="$(hostname --ip-address)"
fi
```
So I suggest to set env CASSANDRA_LISTEN_ADDRESS when start container or change your server's hostname and mapping ip address.

[reference:org.apache.cassandra.auth.CassandraRoleManager doesn’t support PASSWORD](http://www.dbrnd.com/2016/05/nosql-org-apache-cassandra-auth-cassandrarolemanager-doesnt-support-password/)
