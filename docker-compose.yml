version: "3"
services:
  node:
    image: "node:13"
    user: "node"
    working_dir: /home/node/app
    environment:
      - NODE_ENV=production
    volumes:
      - /c/Users/Jon/docker/db/node:/home/node/app
    ports:
      - "8081"
    command: "npm install && ng serve"

  db1:
    image: "couchbase:6.5.0"
    volumes:
      - ./couchbase/1:/opt/couchbase/var
    ports:
      - "8091-8096:8091-8096"
      - "11210-11211:11210-11211"
  db2:
    image: "couchbase:6.5.0"
    volumes:
      - ./couchbase/2:/opt/couchbase/var
  db3:
    image: "couchbase:6.5.0"
    volumes:
      - ./couchbase/3:/opt/couchbase/var

  go:
    image: "golang:1.13"
    working_dir: /usr/src/myapp
    volumes:
      - /c/Users/Jon/docker/db/go:/usr/src/myapp
    command: "go run *.go"