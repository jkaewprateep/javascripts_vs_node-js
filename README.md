# Similarity and differentiation of JavaScript and Node.js with Django on node.js ( JavaScript-Programming-Essentials )
Similarity and differentiation of JavaScript and Node.js with Django on node.js

## 🧸💬 Data and data communication path for read, write, and update of data record 

🐑💬 ➰ We create data classes in the data module for managing data connection, data activities, database and dataset definitions, and database authentication validation. </br>
👧💬 🎈 In C#.net data adaptors automatically update queries and re-organize the selection method except update and delete, or process with ALTER. </br>
🦭💬 When you select and download database drivers and integrations from Oracle, MS-SQL, MongoDB, or any of the database brands, it is easier to manage codes with drivers or data adaptors with database communication drivers and GUI management features. A good administrator and good developer select the correct management driver that makes it easier in development processes. </br>


### Javascript constant struct 

```
const employees = [
    { id: 1, name: ' 🧸💬  John Doe', age: 30, department: 'IT', salary: 50000, specialization: " 👧💬 🎈  Javascript" },
    { id: 2, name: ' 🦭💬  Alice Smith', age: 28, department: 'HR', salary: 45000, specialization: " 👧💬 🎈  Python" },
    { id: 3, name: ' 🐐💬  Bob Johnson', age: 35, department: 'Finance', salary: 6000, specialization: " 👧💬 🎈  Java" },
    //... More employee records can be added here 
];
```

### Data class model in Django - by the instruction

```
class IEntiryDriver(models.Model):
    _id = models.PositiveIntegerField(primary_key=True, validators=[MaxValueValidator(9999999999)])
    _TGOid = models.PositiveIntegerField(primary_key=False, validators=[MaxValueValidator(9999999999)])
    _IGOid = models.PositiveIntegerField(primary_key=False, validators=[MaxValueValidator(9999999999)])
    home_location_point = IGeoPoint.coordinates
    driving_radius_miles = models.DecimalField(max_digits=12, decimal_places=4)
    description = models.CharField(max_length=2048)
    run_status = models.PositiveIntegerField(primary_key=False, validators=[MaxValueValidator(1000000000)])
    max_status = models.PositiveIntegerField(primary_key=False, validators=[MaxValueValidator(1000000000)])
    status = models.CharField(max_length=256)
    
    def __str__(self):
        return self._id
```

### MongoDB 🥭 in database connection - sample find collection and client connectivity

```
def Find_mongoDBconnection(CollectionName, pipeline):
    # Set the Stable API version when creating a new client
    client = MongoClient(uri, server_api=ServerApi('1'), connectTimeoutMS=3000, socketTimeoutMS=3000, maxPoolSize=50)
    
    # Define DB Name
    dbname = client['admin']
    
    # Define Collection
    collection = dbname[CollectionName]
    
    try:
        result = list(collection.find(pipeline))
        
    except PyMongoError as e:
        print(f"Database operation failed: {e}")
    
    return result
```
