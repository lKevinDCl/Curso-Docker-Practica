# Docker compose ejecución

> docker compose up 

>> consola devolvio:
docker compose up       
time="2025-09-23T09:35:36-06:00" level=warning msg="C:\\Users\\kevin\\Documents\\Curso Udemy Docker\\Multi-container Apps Docker-Compose\\postgres-pgadmin\\docker-compose.yml: the attribute `version` is obsolete, it will be ignored, please remove it to avoid potential confusion"
[+] Running 4/4
 ✔ Network postgres-pgadmin_postgres-net    Created                                                                    0.1s 
 ✔ Volume "postgres-pgadmin_postgres-data"  Created                                                                    0.0s 
 ✔ Container postgres-db                    Created                                                                    0.2s 
 ✔ Container pgAdmin                        Created                                                                    0.2s 
Attaching to pgAdmin, postgres-db
postgres-db  | The files belonging to this database system will be owned by user "postgres".
postgres-db  | This user must also own the server process.
postgres-db  |                                                                                                              
postgres-db  | The database cluster will be initialized with locale "en_US.utf8".                                           
postgres-db  | The default database encoding has accordingly been set to "UTF8".                                            
postgres-db  | The default text search configuration will be set to "english".
postgres-db  |                                                                                                              
postgres-db  | Data page checksums are disabled.                                                                            
postgres-db  |                                                                                                              
postgres-db  | fixing permissions on existing directory /var/lib/postgresql/data ... ok                                     
postgres-db  | creating subdirectories ... ok                                                                               
postgres-db  | selecting dynamic shared memory implementation ... posix                                                     
postgres-db  | selecting default max_connections ... 100                                                                    
postgres-db  | selecting default shared_buffers ... 128MB
postgres-db  | selecting default time zone ... Etc/UTC
postgres-db  | creating configuration files ... ok
postgres-db  | running bootstrap script ... ok
postgres-db  | performing post-bootstrap initialization ... ok
postgres-db  | initdb: warning: enabling "trust" authentication for local connections
postgres-db  | initdb: hint: You can change this by editing pg_hba.conf or using the option -A, or --auth-local and --auth-host, the next time you run initdb.                                                                                          
postgres-db  | syncing data to disk ... ok
postgres-db  |                                                                                                              
postgres-db  |                                                                                                              
postgres-db  | Success. You can now start the database server using:                                                        
postgres-db  | 
postgres-db  |     pg_ctl -D /var/lib/postgresql/data -l logfile start                                                      
postgres-db  |                                                                                                              
postgres-db  | waiting for server to start....2025-09-23 15:35:39.117 UTC [48] LOG:  starting PostgreSQL 15.1 (Debian 15.1-1.pgdg110+1) on x86_64-pc-linux-gnu, compiled by gcc (Debian 10.2.1-6) 10.2.1 20210110, 64-bit
postgres-db  | 2025-09-23 15:35:39.120 UTC [48] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
postgres-db  | 2025-09-23 15:35:39.130 UTC [51] LOG:  database system was shut down at 2025-09-23 15:35:38 UTC              
postgres-db  | 2025-09-23 15:35:39.141 UTC [48] LOG:  database system is ready to accept connections
postgres-db  |  done                                                                                                        
postgres-db  | server started
postgres-db  |                                                                                                              
postgres-db  | /usr/local/bin/docker-entrypoint.sh: ignoring /docker-entrypoint-initdb.d/*
postgres-db  |                                                                                                              
postgres-db  | 2025-09-23 15:35:39.275 UTC [48] LOG:  received fast shutdown request                                        
postgres-db  | waiting for server to shut down....2025-09-23 15:35:39.277 UTC [48] LOG:  aborting any active transactions
postgres-db  | 2025-09-23 15:35:39.280 UTC [48] LOG:  background worker "logical replication launcher" (PID 54) exited with exit code 1                                                                                                                 
postgres-db  | 2025-09-23 15:35:39.280 UTC [49] LOG:  shutting down
postgres-db  | 2025-09-23 15:35:39.283 UTC [49] LOG:  checkpoint starting: shutdown immediate                               
postgres-db  | 2025-09-23 15:35:39.296 UTC [49] LOG:  checkpoint complete: wrote 3 buffers (0.0%); 0 WAL file(s) added, 0 removed, 0 recycled; write=0.005 s, sync=0.002 s, total=0.016 s; sync files=2, longest=0.001 s, average=0.001 s; distance=0 kB, estimate=0 kB
postgres-db  | 2025-09-23 15:35:39.306 UTC [48] LOG:  database system is shut down
postgres-db  |  done                                                                                                        
postgres-db  | server stopped
postgres-db  |                                                                                                              
postgres-db  | PostgreSQL init process complete; ready for start up.                                                        
postgres-db  |                                                                                                              
postgres-db  | 2025-09-23 15:35:39.417 UTC [1] LOG:  starting PostgreSQL 15.1 (Debian 15.1-1.pgdg110+1) on x86_64-pc-linux-gnu, compiled by gcc (Debian 10.2.1-6) 10.2.1 20210110, 64-bit
postgres-db  | 2025-09-23 15:35:39.419 UTC [1] LOG:  listening on IPv4 address "0.0.0.0", port 5432
postgres-db  | 2025-09-23 15:35:39.419 UTC [1] LOG:  listening on IPv6 address "::", port 5432                              
postgres-db  | 2025-09-23 15:35:39.423 UTC [1] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"           
postgres-db  | 2025-09-23 15:35:39.433 UTC [62] LOG:  database system was shut down at 2025-09-23 15:35:39 UTC
postgres-db  | 2025-09-23 15:35:39.442 UTC [1] LOG:  database system is ready to accept connections                         


