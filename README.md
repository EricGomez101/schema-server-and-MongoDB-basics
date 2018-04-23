# A demo of basic schema, MongoDB and server set-up
- In particular, demonstrating how MongoDB Database and Collections get named and established

# Command Line Mongo
1. In your console, use `mongod` to start the MongoDB daemon serving up your database
```console
$ mongod
  ...
  YYY-MM-DDThh:mm:ss.mmm-#### I NETWORK  [initandlisten] waiting for connections on port 27017
```

2. There will be a lot more in the console report from invoking `mongod`. If the last line does not tell you that the daemon is waiting for connections, you may need to stop any other instances of `mongod` which are active on your computer.
3. In a separate console, use the `mongo` command to interact with the database through the command line.
```console
$  mongo        <---- invoke the MongoDB
   MongoDB shell version v3.6.3
   connecting to: mongodb://127.0.0.1:27017
   MongoDB server version: 3.6.3
   Server has startup warnings:  <---- ?????
   ...
   2018-04-23T10:46:00.525-0400 I CONTROL  [initandlisten]
```

4. You may see "warnings" reported. Take a minute to read these warnings over and investigate what they mean. In general, warnings - unlike errors - won't stop you from working with the program.
5. Here are examples of some useful `mongo` commands for navigating and investigating your databases, collections and data:
```console
> show dbs                  <---- list all the databases
   admin   0.000GB
   config  0.000GB
   local   0.000GB
   users   0.000GB
> db                        <---- display which db is active (test is the default)
   test
> use users                 <---- use a particular database
   switched to db users
> db
   users                    <---- see?
> show collections          <---- currently no collections in the users DB
> db.users.find().pretty()  <---- display contents nicely
   {
           "_id" : ObjectId("5ab457b6103d0e1cb6597d16"),
           "username" : "bob",
           "passwordHash" : "$2a$11$dsFfbj6ETxWbMtNJLEQEEOZnCKqFjjyFR2BA0gdO/sBvhJMkuFfSy",
           "__v" : 0
   }
> db.dropDatabase()         <---- nuke db out of existence
   { "dropped" : "users", "ok" : 1 }
> quit()                    <---- well... this should be fairly obvious?
$
```
