# Databases running inside Docker

## MongoDB

Installing MongoDB from container:
```
$ sudo docker images
$ sudo docker pull mongo:latest
$ sudo docker images
```

Create a folder in **/home/user-name** folder:
```
$ cd ~
$ mkdir mongodb-docker
$ cd mongodb-docker
$ sudo docker run -d -p 2717:27017 -v ~/mongodb-docker:/data/db --name mymongo mongo:latest
$ sudo docker ps
$ sudo docker exec -it mymongo bash
/# mongo
> show dbs
> use test
> db.user.insert({"name": "Shahjalal"})
> db.user.find()
> exit
/# exit
```

From the local terminal:
```
$ sudo apt install mongodb-clients
$ mongo localhost:2717
> show dbs
> use test
> db.user.find()
> exit
```

Stop docker running container:
```
$ sudo docker ps
$ sudo docker stop e98d524d5562
$ sudo docker ps
```
