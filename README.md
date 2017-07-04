export M2=/Users/dimeh/Documents/Tools/apache-maven-3.3.9/bin
export PATH=$PATH:$M2

> docker build -t ehayanis/demo-webapp .
=======
**Download and Start Mongo DB Server**
> docker run -P -d --name mongodb mongo

**Use of mongodb**
> docker exec -it mongodb /bin/bash <br>
> mongo admin -u admin -p OapsdL7wpSD0 --host localhost --port 28017

**Create and list collections**
> use microserviceblog
> db.createCollection('testCollection')
> db.getCollectionNames()

**MongoDB Overview**
> Database, Collection (Table), Document (Row)

**Insert into collection**
> db.mycol.insert({
     _id: ObjectId(7df78ad8902c),<br>
     title: 'MongoDB Overview', <br>
     description: 'MongoDB is no sql database',<br>
     by: 'tutorials point',<br>
     url: 'http://www.tutorialspoint.com',<br>
     tags: ['mongodb', 'database', 'NoSQL'],<br>
     likes: 100<br>
  })
  
**Find Document in Collection**
> db.testCollection.find({"by":"tutorials point"}).pretty() <br>
> db.testCollection.find({$and:[{"by":"tutorials point"},{"likes": "$gt:50"}]}).pretty()

**Update and sate methods**
> The update method updates the value in the existing document, while save replaces the existing document 

**Remove Documents**
> To remove all elements <br> 
db.testCollection.remove() <br>
> To remove specific elements <br>
db.testCollection.remove({'title':'MongoDB Overview'})


DOCKER and VMs provisionning

> docker-machine create --driver digitalocean --digitalocean-access-token 9ac826913187236a863f38942a219a5e7336139efc1cd21809ed97d75a7bdd14 demo-machine

> docker-machine env demo-machine 

> eval $(docker-machine env demo-machine)

> docker info 

> docker-compose up -d
