
 # SpringBoot Application and Azure DocumentDB for MongoDB Protocol
DocumentDB databases can now be used as the data store for apps written for MongoDB. This means that by using existing drivers for MongoDB databases, your application written for MongoDB can now communicate with DocumentDB and use DocumentDB databases instead of MongoDB databases. In many cases, you can switch from using MongoDB to DocumentDB by simply changing a connection string.

This is a SpringBoot application that uses Spring Data MongoDB to do CRUD operations on MongoDB. The same code base is used with both MongoDB and DocumentDB for MongoDB Protocol.

## Local
Following are the instructions to run the app locally against a local MongoDB instance and against Azure DocumentDB for MongoDB protocol instance.
1. Install Java and Maven
2. Install and start MongoDB
3. Clone the repository
4. Make the project base as the current directory 
5. Run the application by executing the follwoing command from the project base directory
      >  mvn package && java  -jar target/PCFReadingListDocDB-0.0.1.jar 
6. Access the appliction from the following URL:
      > http://localhost:7070    
7. Create a DocumentDB account for MongoDB protocol
     > Detailed instructions can be found [HERE](https://docs.microsoft.com/en-us/azure/documentdb/documentdb-create-account).
8. Retrieve and update the connection string for DocumentDB
     > Detailed instructions can be found [HERE](https://docs.microsoft.com/en-us/azure/documentdb/documentdb-connect-mongodb-account).
9. The updated connection string will be of the following format.Make sure to replace DATABASE with a name of your choice.The database will be created on demand when you start adding books to your readinglist.    
      > mongodb://USERNAME:PASSWORD@HOST:PORT/DATABASE?ssl=true
10. From the project base directory run the following command:
      > mvn package && java -Dspring.data.mongodb.uri=CONNECTIONSTRING -jar target/PCFReadingListDocDB-0.0.1.jar
11. Access the appliction from the following URL:
      > http://localhost:7070 

## Docker
Following are the instructions to run the app in a docker linux environmnet with DocumnetDB as the persistence store.
1. Install docker for linux 
2. In a docker command line make the project base as the current directory
3. Run the following command to build a docker image(don't miss the period)
   > docker build -t DOCKERHUBREPO:latest .
   DOCKERHUBREPO could be any name but using a gitgub repository name 
4. Execute the docker fun command to start the container. The command will be of the following format:
   >  docker run -d -e spring.data.mongodb.uri='CONNECTIONSTRING' -p 7070:7070 -t DOCKERHUBREPO:latest
5. Access the appliction from the following URL:
   > http://DOCKERHOST:7070 

## kubernetes
Coming soon
## Pivotal Cloud Foundry
Coming soon
## RedHat OpenShift
Coming soon
# Contributing
Coming soon

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
