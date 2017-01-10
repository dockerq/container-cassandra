# Cassandra on Container
This image is based on [cassandra 2.2.8](https://github.com/docker-library/cassandra/blob/master/2.2/Dockerfile).

I add `cassandra.yaml` to enable set user with password.

[reference:org.apache.cassandra.auth.CassandraRoleManager doesn’t support PASSWORD](http://www.dbrnd.com/2016/05/nosql-org-apache-cassandra-auth-cassandrarolemanager-doesnt-support-password/)
