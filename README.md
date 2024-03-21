# Similarity and differentiate of JavaScript and Node.js with Django on node.js ( JavaScript-Programming-Essentials )
Similarity and differentiate of JavaScript and Node.js with Django on node.js

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
