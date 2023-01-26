# MONGODB CHEETSHEET

### View all databases
```sh
show dbs
```

### Create a new or switch databases
```sh
use dbName
```

### View current Database
```sh
db
```

### Delete Database
```sh
db.dropDatabase()
```

# Collection Commands
```sh
Show Collections
show collections
```

#### Create a collection named 'comments'
```sh
db.createCollection('comments')
```

#### Drop a collection named 'comments'
```sh
db.comments.drop()
```

# Row(Document) Commands
```sh
Show all Rows in a Collection 
db.comments.find()
```

#### Show all Rows in a Collection (Prettified)
```sh
db.comments.find().pretty()
```

#### Find the first row matching the object
```sh
db.comments.findOne({name: 'Ranjit'})
```

#### Insert One Row
```sh
db.comments.insert({
        'name': 'Ranjit',
        'lang': 'JavaScript',
        'member_since': 5
    })
```

#### Insert many Rows
```sh
db.comments.insertMany([{
        'name': 'Ranjit',
        'lang': 'JavaScript',
        'member_since': 5
        }, 
        {'name': 'Rohan',
        'lang': 'Python',
        'member_since': 3
        },
        {'name': 'Love',
        'lang': 'Java',
        'member_since': 4
    }])
```

#### Search in a MongoDb Database
```sh
db.comments.find({lang:'Python'})
```

#### Limit the number of rows in output
```sh
db.comments.find().limit(2)
```

#### Count the number of rows in the output
```sh
db.comments.find().count()
```

#### Update a row
```sh
db.comments.updateOne({name: 'Shubham'},
{$set: {'name': 'Ranjit',
    'lang': 'JavaScript',
    'member_since': 51
}}, {upsert: true})
```

#### Mongodb Increment Operator
```sh
db.comments.update({name: 'Rohan'},
    {$inc:{
        member_since: 2
    }})
```

#### Mongodb Rename Operator
```sh
db.comments.update({name: 'Rohan'},
{$rename:{
    member_since: 'member'
}})
```

#### Delete Row
```sh
db.comments.remove({name: 'Harry'})
```

#### Less than/Greater than/ Less than or Eq/Greater than or Eq
```sh
db.comments.find({member_since: {$lt: 90}})
db.comments.find({member_since: {$lte: 90}})
db.comments.find({member_since: {$gt: 90}})
db.comments.find({member_since: {$gte: 90}})
```





