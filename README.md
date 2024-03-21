# Similarity and differentiation of JavaScript and Node.js with Django on node.js ( JavaScript-Programming-Essentials )
Similarity and differentiation of JavaScript and Node.js with Django on node.js

## 🧸💬 Data and data communication path for read, write, and update of data record 

🐑💬 ➰ We create data classes in the data module for managing data connection, data activities, database and dataset definitions, and database authentication validation. </br>
👧💬 🎈 In C#.net data adaptors automatically update queries and re-organize the selection method except update and delete, or process with ALTER. </br>
🦭💬 When you select and download database drivers and integrations from Oracle, MS-SQL, MongoDB, or any of the database brands, it is easier to manage codes with drivers or data adaptors with database communication drivers and GUI management features. A good administrator and good developer select the correct management driver that makes it easier in development processes. </br>


### Javascripts constant struct ✳️

```
const employees = [
    { id: 1, name: ' 🧸💬  John Doe', age: 30, department: 'IT', salary: 50000, specialization: " 👧💬 🎈  Javascript" },
    { id: 2, name: ' 🦭💬  Alice Smith', age: 28, department: 'HR', salary: 45000, specialization: " 👧💬 🎈  Python" },
    { id: 3, name: ' 🐐💬  Bob Johnson', age: 35, department: 'Finance', salary: 6000, specialization: " 👧💬 🎈  Java" },
    //... More employee records can be added here 
];
```

### Data class model in Django - by the instruction ( Python 🐍 )

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

- - -

###  Read and respond to HTML document object from the value from data struct ✳️

```
function displayEmployees(){
    const Employees = employees;
    const EmployeesDisplay = Employees.map((employee, index) => `<p>${employee.id}: ${employee.name}: ${employee.name} - ${employee.department} - $${employee.salary} - $${employee.specialization}</p>`).join('');
    document.getElementById('employeesDetails').innerHTML = EmployeesDisplay;
}
```

### Read and respond to web object from the data module classes ( Python 🐍 )

```
def add_neworder(request):
    
    customer_id = 1
    driver_id = 1
    customer_name = "DekDee"
    order_name = "rice"
    amount = 2
    description = "discription"
    order_time = timezone.now()
    run_status = 0
    max_status = create_random(10, 60, 1)
    
    ####################################################################
    # Pre-requisites must have order name and order amount
    ####################################################################
    if request.method == 'POST':
        customer_id = request.POST.get("customer_id", "")
        order_name = request.POST.get("order_name", "invalid_ordername")
        amount = request.POST.get("amount", 0)
        description = request.POST.get("description", "discription")
        run_status = request.POST.get("run_status", 0)
        max_status = request.POST.get("max_status", create_random(10, 60, 1))
        
    elif request.method == 'GET':
        customer_id = request.GET.get("customer_id", "")
        order_name = request.GET.get("order_name", "invalid_ordername")
        amount = request.GET.get("amount", 0)
        description = request.GET.get("description", "discription")
        run_status = request.POST.get("run_status", 0)
        max_status = request.POST.get("max_status", create_random(10, 60, 1))
        
    else:
        data = create_jsonmessegereturn("request not specific method", "error")
        return HttpResponse(data)
    
    if order_name == "invalid_ordername" or amount == 0:
        data = create_jsonmessegereturn("invalid order name or order amount", "error")
        return HttpResponse(data)
    
    ####################################################################
    # 0. Find avaialble customer
    ####################################################################    
    # Aggregate function
    pipeline = [{ "$match": { "_id": str(customer_id) }},
                {"$sort": SON([("_id", -1)])}]
    
    customers_resultset = Agr_mongoDBconnection('customers', pipeline)
    
    if len(customers_resultset) < 1 :
    
        ####################################################################
        # 0.1 If not found customer create new one
        ####################################################################
        
        new_customer = {
            # "customer_id": customer_id,
            "customer_name": customer_name,
            "firstname": driver_id,
            "lastname": order_name,
            "name": amount,
            "description": description
        }
        
        customers_resultset = Insert_mongoDBconnection('customers', new_customer)
    
    ####################################################################
    # 0.2 Find avaialble ordername
    ####################################################################
    # Aggregate function
    pipeline = [{ "$match": { "ordername": str(order_name) }},
                {"$sort": SON([("_id", -1)])},{"$limit": 1 }]

    orderitems_resultset = Agr_mongoDBconnection('IOrderItems', pipeline)  
    
    if len(orderitems_resultset) > 0:
        orderitems_resultset = orderitems_resultset[0]
    
    ####################################################################
    # 0.3 If order name not available
    ####################################################################
    if len(orderitems_resultset) < 1:
        data = create_jsonmessegereturn("ordername not available", "error")
        return HttpResponse(data)
    
    ####################################################################
    # 1. Find available driver into avaliable_id
    ####################################################################
    # Aggregate function
    pipeline = [{ "$match": { "status": "Available" } },
                {"$sort": SON([("run_status", -1)])},{"$limit": 3 }]

    resultset = Agr_mongoDBconnection('drivers', pipeline)
    
    customer_id = customers_resultset["_id"]
    customer_name = customers_resultset["customer_name"]
    order_name = orderitems_resultset["ordername"]
    description = "discription"
    order_time = timezone.now()
    
    print("find availabele driver")
    drivers_avaliable_id = []
    for item in resultset:
        data = create_dictitemsfromreturnretulst(item)
        for _item in data:
            if _item == "_id":
                drivers_avaliable_id.append(data[_item])
    
    ####################################################################
    # 2. Create Order
    ####################################################################    
    # ICustomer.id = 1234
    # ICustomer.firstname = "Jirayu"
    # ICustomer.lastname = "Kaewprateep"
    
    ####################################################################
    # 2.1 Assign customer Id and Avalable driver Id
    ####################################################################
    if len(drivers_avaliable_id) > 0:
        customer_id = customers_resultset["_id"]
        driver_id = drivers_avaliable_id[0]
        customer_name = customers_resultset["customer_name"]
        order_name = orderitems_resultset["ordername"]
        description = "discription"
    
    else:
        ####################################################################
        # 2.2 If there is no available driver add temp driver Id for monitor
        ####################################################################
        customer_id = customers_resultset["_id"]
        driver_id = "temp_drivers"
        customer_name = customers_resultset["customer_name"]
        order_name = orderitems_resultset["ordername"]
        description = "discription"
    
    new_order = {
        "customer_id": customer_id,
        "customer_name": customer_name,
        "driver_id": driver_id,
        "order_name": order_name,
        "amount": amount,
        "description": description,
        "run_status": run_status,
        "max_status": max_status,
        "order_time": order_time
    }
    ###
    
    result_findinsertid = Insert_mongoDBconnection("order", new_order)
    
    print("************************************")
    print(result_findinsertid)
    print("************************************")
    
    data = create_dictitemsfromreturnretulst(result_findinsertid)
    json_data = json.dumps(data)
    ###
    
    return HttpResponse(json_data)
```

### Section client for communication with HTML events ❇️ react.js

```
// TEMPORARY PLACEHOLDER DATA
const url = "https://localhost:8000/retreive_ordersTOPN/";

async function getData(index: Int32) {

  const res = await fetch(url + "?number=2",
  {
    method: 'GET',
    headers: {
      "Host": "https://127.0.0.1:3000/",
      'content-type': 'application/json',
      "User-Agent": "PostmanRuntime/7.36.1",
      "Accept": "*/*",
    },
    })

    if (!res.ok) {
      return [0, 0, 50];
    }

  const data = await res.json();

  try {
    const run_status = Number(data[index].run_status)
    const max_status = Number(data[index].max_status)
    const order_id = String(data[index]._id)
    console.log(order_id)
    console.log(run_status)
    console.log(max_status)
    return [order_id, run_status, max_status];

  } catch (error) {
      const run_status = 0
      const max_status = 100
      const order_id = "0000000000000"
      console.log(order_id)
      console.log(run_status)
      console.log(max_status)
      return [order_id, run_status, max_status];
  }
};

const getMockStatusConfigByIndex = async (index: number) => {

  const [order_id, run_status, max_status] = await getData( index )
  return [order_id, run_status, max_status];
};
```

### Data Rendering - react.js Server-Client ❇️

```
renderItem={async (driver, index) => {
    const [driver_id, percentComplete, numSteps] = await getMockStatusConfigByIndex(index);
```

### Data Rendering - javaScripts HTML ✳️

```
function findEmployeeById(employeeId) {
    const foundEmployee = employees.find(employee => employee.id === employeeId);
    if (foundEmployee) {
        document.getElementById('employeesDetails').innerHTML =`<p>${foundEmployee.id}: ${foundEmployee.name}: ${foundEmployee.name} - ${foundEmployee.department} - ${foundEmployee.salary} - ${foundEmployee.specialization}</p>`;
    }
    else{
        document.getElementById('employeesDetails').innerHTML = 'no employee has been found with this ID';

    }
}
```
