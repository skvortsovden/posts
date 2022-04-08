# Cheatsheet Mongo

### view all databases

```cmd
show dbs
```

### show current db
```cmd
db
```

### view collection inside database

```cmd
show collections
```

### switch database

```cmd
use {db_name}
```


### list all documents in collection

```cmd
db.{collectio_name}.find()
```

### drop database

```cmd
db.dropDatabase()
```

### check database size

```cmd
db.stats(1024 * 1024).storageSize // in megabytes
```