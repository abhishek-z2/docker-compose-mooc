development project: shrnk

shrnk is a URL shortener built in Go, PostgreSQL and Redis. 

the Go application runs directly on the host machine, while the suppporting services ( PostgreSQL and Redis ) are containerized by integrating docker compose. 

both services run in seperate containers, managed through docker compose

### PostgreSQL configuration

- PostgreSQL uses official postgres:16 image
- the containers port 5432 is mapped to host port 5433 ( avoided host port 5432 to avoid conflict with locally running psql instance ) 
- a named docker volume pgdata is used to persist database across container restarts and recreations



### Redis configuration

- Redis run using official image redis:7
- the Go application connects to redis through its exposed host port



