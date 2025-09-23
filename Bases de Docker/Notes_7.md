# Comandos de Docker 3 / diferentes instancias de postgres

## Se utilizan las variables de entorno:

docker container run \
--name postgres-alpha \
-e POSTGRES_PASSWORD=mypass1 \
-dp 5432:5432 \
postgres

>Debbuginng
>> Tuve que hacerlo de esta manera ya que como lo marca la documentacion no pude hacerlo
docker container run --name postgres-alpha -e POSTGRES_PASSWORD=mypass1 -p 5432:5432 postgres

>La consola me devolvio:
>>
The files belonging to this database system will be owned by user "postgres".
This user must also own the server process.

The database cluster will be initialized with locale "en_US.utf8".
The default database encoding has accordingly been set to "UTF8".
The default text search configuration will be set to "english".

Data page checksums are disabled.

fixing permissions on existing directory /var/lib/postgresql/data ... ok
creating subdirectories ... ok
selecting dynamic shared memory implementation ... posix
selecting default "max_connections" ... 100
selecting default "shared_buffers" ... 128MB
selecting default time zone ... Etc/UTC
creating configuration files ... ok
running bootstrap script ... ok
performing post-bootstrap initialization ... ok
syncing data to disk ... initdb: warning: enabling "trust" authentication for local connections
initdb: hint: You can change this by editing pg_hba.conf or using the option -A, or --auth-local and --auth-host, the next time you run initdb.
ok


Success. You can now start the database server using:

    pg_ctl -D /var/lib/postgresql/data -l logfile start

waiting for server to start....2025-09-22 00:47:35.301 UTC [48] LOG:  starting PostgreSQL 17.6 (Debian 17.6-1.pgdg13+1) on x86_64-pc-linux-gnu, compiled by gcc (Debian 14.2.0-19) 14.2.0, 64-bit
2025-09-22 00:47:35.304 UTC [48] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
2025-09-22 00:47:35.315 UTC [51] LOG:  database system was shut down at 2025-09-22 00:47:34 UTC
2025-09-22 00:47:35.324 UTC [48] LOG:  database system is ready to accept connections
 done
server started

/usr/local/bin/docker-entrypoint.sh: ignoring /docker-entrypoint-initdb.d/*

2025-09-22 00:47:35.426 UTC [48] LOG:  received fast shutdown request
waiting for server to shut down....2025-09-22 00:47:35.428 UTC [48] LOG:  aborting any active transactions
2025-09-22 00:47:35.431 UTC [48] LOG:  background worker "logical replication launcher" (PID 54) exited with exit code 1    
2025-09-22 00:47:35.431 UTC [49] LOG:  shutting down
2025-09-22 00:47:35.432 UTC [49] LOG:  checkpoint starting: shutdown immediate
2025-09-22 00:47:35.443 UTC [49] LOG:  checkpoint complete: wrote 3 buffers (0.0%); 0 WAL file(s) added, 0 removed, 0 recycled; write=0.003 s, sync=0.002 s, total=0.013 s; sync files=2, longest=0.001 s, average=0.001 s; distance=0 kB, estimate=0 kB; lsn=0/14ED7B8, redo lsn=0/14ED7B8
2025-09-22 00:47:35.451 UTC [48] LOG:  database system is shut down
 done
server stopped

PostgreSQL init process complete; ready for start up.

2025-09-22 00:47:35.563 UTC [1] LOG:  starting PostgreSQL 17.6 (Debian 17.6-1.pgdg13+1) on x86_64-pc-linux-gnu, compiled by gcc (Debian 14.2.0-19) 14.2.0, 64-bit
2025-09-22 00:47:35.564 UTC [1] LOG:  listening on IPv4 address "0.0.0.0", port 5432
2025-09-22 00:47:35.564 UTC [1] LOG:  listening on IPv6 address "::", port 5432
2025-09-22 00:47:35.569 UTC [1] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
2025-09-22 00:47:35.576 UTC [62] LOG:  database system was shut down at 2025-09-22 00:47:35 UTC
2025-09-22 00:47:35.586 UTC [1] LOG:  database system is ready to accept connections

## Creamos una nueva conexión:

![alt text](screenshots-Lesson-1/image12.png)


## Creamos una nueva instancia Beta:

> docker container run --name postgres-beta -e POSTGRES_PASSWORD=mypass1 -p 5433:5432 postgres:14-alpine3.17  

## Se hace una conexión para la instancia Beta:

![alt text](screenshots-Lesson-1/image13.png)

## Se muestran ambos contenedores en un purto diferente:

![alt text](screenshots-Lesson-1/image14.png)