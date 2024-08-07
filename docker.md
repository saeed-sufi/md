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

* Always use `USER node` in your dockerfiles after `apt/apk` or `npm i -g` commands that require root user. But use it before regular `npm install` command so that you only give write permissions wherever your app really needs to have such permissions. 


* After you set `User node`, only these 3 commands use this user to do their job: `RUN`, `Entrypoint` and `CMD`. Other commands do not respect this user. For example, the `WORKDIR` command always uses the `root user` even if you've previously set the user to node. The way to get around this problem of `WORKDIR` is: `RUN mkdir app && chown -R node:node app`


* By default `docker compose exec` set you as `node` user if it sees `USER node` in the Dockerfile. If you need to change this behaviour, do this: `docker compose exec -u root`.


* Make sure to give the node user permisions for copying files: `COPY --chown=node:node . .`. This might not be required for all apps but it's a best practice to do it since some apps may run into permission problems. 


* A temporary solution for node app to listen for linux signals:
`docker run --init -d node-app`


* To perform a gracefull shutdown of you node app in a contaier, add this code in your node app:
https://github.com/BretFisher/docker-mastery-for-nodejs/blob/4cd605de4e80f002d7ce876c0e20cd93564f9481/sample-graceful-shutdown/sample.js


* Docker manages multiple `replicas` or `tasks` of node which means it can run multiple instance of node. In fact, multiple containers will run off the same image. 


* Docker uses linux signals to stop app (SIGINT / SIGTERM / SIGKILL).


* To get the container IP address run the following command:

`docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container_id_or_name>`


* To enable rabbitmq management interface and access it in browser (localhost:15672):

`docker exec -it rabbitmqvideoverification rabbitmq-plugins enable rabbitmq_management`

* Put `docker-compose*.yml` file inside `.dockerignore`. It contains lots of info about your app and you don't want a bad guy to have access to it. 

* Run the following command to run postgres:
```
docker run --name postgres \
    -e POSTGRES_USER=postgres \
    -e POSTGRES_PASSWORD=ev3VJFD5jAR6b9@ \
    -e POSTGRES_DB=farashenasa \
    -p 5432:5432 \
    -v my_postgres_data:/var/lib/postgresql/data \
    -d postgres:16.3-bookworm
```


