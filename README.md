About docker-postgres
=====================

This is a the Dockerfile for a customized Postgres Docker image. We initially needed a custom image to enable prepared transactions and came across the image of nuxeo, which we forked to upgrade to Postgres version 9.5.

Building
========

```
docker build -t nuxeo/postgres .
```

Configuration
=============

During initialization the `config.sh` will be run to automatically configure some key parameters of PostgreSQL.

These parameters can be passed as environment variables :

-	`PG_SHARED_BUFFERS` : size of the PG Shared buffer (default is 100MB)
-	`PG_PREPARED_TRANSACTIONS` : max number of prepared transactions (default is 32)
-	`PG_EFFECTIVE_CACHE` : `effective_cache_size` (default is 1GB)
-	`PG_WORK_MEM` : Work memory (default is 32M)
-	`PG_WAL_BUFFERS` : `wal_buffers` (default is 8MB)
