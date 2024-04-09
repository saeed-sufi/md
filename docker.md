* To run redis:
`docker run -d --name redis-stack -p 6379:6379 -p 8001:8001 redis/redis-stack:latest`

* To run an image with volume:
`docker run -it --name todo2 -p 8008:8080 -v /home/saeedsoofi/projects/todo:/usr/src/app todo:v1`

* To stop and remove containers and images and volumes that were created using docker compose:
`docker compose down --rmi all -v`

* To connect to postgres container (find the ip using `docker inspect`):
`psql -h 172.18.0.3 -p 5432 -U postgres -d postgres`
