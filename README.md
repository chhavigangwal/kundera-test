# kundera-test
The application provides a servlet to generate data and store them in Datastore through CPIM and Kundera GAE Datastore extension.
The generation is achieved issuing tasks on the default queue.

To easily cleanup the datastore a clean up servlet is provided, the servlet pushes a task on the default queue for each persisted table, so each task is responsible of deleting all entities of the given table.
The cleanup servlet also cleanup, if exists, a table named `usertable` which is the table used when benchmarking with YCSB.

A remote API servlet is also available, see [web.xml](https://github.com/Arci/kundera-test/blob/master/src/main/webapp/WEB-INF/web.xml).

###Start the application
To start the app just run the command:

```
mvn appengine:devserver
```
