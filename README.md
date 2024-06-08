# Test setup with pgcat, postgres and pgbench

Start the cluster:

```shell
docker-compose up
```

Try with `pgbench`:

```shell
# https://www.postgresql.org/docs/current/pgbench.html
# init "postgres" database for pgbench
pgbench -p 6432 -h localhost -i -U postgres postgres
# bench with 200 clients for 20 seconds
# -C: new connection for each transaction
# -n: no vacuuming before running test
pgbench -p 6432 -h localhost -T 20 -C -c 200 -n -U postgres postgres
```
