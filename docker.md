* To run redis:
`docker run -d --name redis-stack -p 6379:6379 -p 8001:8001 redis/redis-stack:latest`

* To run an image with volume:
`docker run -it --name todo2 -p 8008:8080 -v /home/saeedsoofi/projects/todo:/usr/src/app todo:v1`

* To stop and remove containers and images and volumes that were created using docker compose:
`docker compose down --rmi all -v`

* To connect to postgres container (find the ip using `docker inspect`):
`psql -h 172.18.0.3 -p 5432 -U postgres -d postgres`


* In your docker file always use `copy` instead of `add`.


* To install packages first make sure to clear cache: `RUN npm install && npm cache clean --force`


* Use `node` in your `CMD`s and not `npm`. Keeping node as the main process is simpler and allows us to use direct signaling. 


* Always use `WORKDIR` instead of `RUN mkdir` unless you need specific permission on a directory when it's created (then you need to `chown` which is a rare occasion).


* When using base images, stick to even numbered versions of major releases (not odd versions as they are experimental node versions).


* Don't use the `latest` tag.


* Dont' use `:onbuild` versions of node images. 

