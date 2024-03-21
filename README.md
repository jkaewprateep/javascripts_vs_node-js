# Similarity and differentiation of JavaScript and Node.js with Django on node.js ( JavaScript-Programming-Essentials )
Similarity and differentiation of JavaScript and Node.js with Django on node.js

## 🧸💬 Data and data communication path for read, write, and update of data record 

🐑💬 ➰ We create data classes in the data module for managing data connection, data activities, database and dataset definitions, and database authentication validation. </br>
👧💬 🎈 In C#.net data adaptors automatically update queries and re-organize the selection method except update and delete, or process with ALTER. </br>
🦭💬 When you select and download database drivers and integrations from Oracle, MS-SQL, MongoDB, or any of the database brands, it is easier to manage codes with drivers or data adaptors with database communication drivers and GUI management features. A good administrator and good developer select the correct management driver that makes it easier in development processes. </br>


### Javascripts constant struct ✳️

🐐💬 A simple constant variable for a data array contains the data record, access, and reference over the javascripts and memory. </br>
🦁💬 Define a class or class module that is saved because it cannot see directly from the codes or debugging when communication over networks Internet is encrypted with session ID as default. </br>
💃( 👩‍🏫 )💬 How to reuse cookies 🍪 from clients for only none business data and use online business data without updating or storing data on the current local machine ⁉️ </br>
🦤💬 Session data is copied and protected by default session data communication mechanisms 🧲 but it can be protected by the method of communications, secured variables, and flag settings for cookies and local accessibility. </br>
🦭💬 At the application level secured communications channels can be managed by HTTP and secured communication support and differentiate sources of data and accessibility but some applications have a load to control local devices and user control applications have TCP/IP and message communication levels they can create their own policy and security compliance. Applications are found using their communication method not only CTI or card control devices but backend and proprietary communication as they need to define ```hello``` and ```reply``` messages. 🔐 </br>

```
const employees = [
    { id: 1, name: ' 🧸💬  John Doe', age: 30, department: 'IT', salary: 50000, specialization: " 👧💬 🎈  Javascript" },
    { id: 2, name: ' 🦭💬  Alice Smith', age: 28, department: 'HR', salary: 45000, specialization: " 👧💬 🎈  Python" },
    { id: 3, name: ' 🐐💬  Bob Johnson', age: 35, department: 'Finance', salary: 6000, specialization: " 👧💬 🎈  Java" },
    //... More employee records can be added here 
];
```

### Data class model in Django - by the instruction ( Python 🐍 )

🐑💬 ➰ Define data model in data module, update of data fields and data foreign keys and objects can be synchronized by the ```migrate command ``` . </br>
🐨🎁🎵🎶 The data model helps manage communication methods the same as the dataset and data set configuration in C#.net applications, you can update the dataset file and reload the application, and in the Django multi-programming languages platforms, you can migrate or update their attributes. </br>

```
class IEntiryDriver(models.Model):
    # 🧸💬 Define data fields
    _id = models.PositiveIntegerField(primary_key=True, validators=[MaxValueValidator(9999999999)])
    _TGOid = models.PositiveIntegerField(primary_key=False, validators=[MaxValueValidator(9999999999)])
    _IGOid = models.PositiveIntegerField(primary_key=False, validators=[MaxValueValidator(9999999999)])
    home_location_point = IGeoPoint.coordinates
    driving_radius_miles = models.DecimalField(max_digits=12, decimal_places=4)
    description = models.CharField(max_length=2048)
    run_status = models.PositiveIntegerField(primary_key=False, validators=[MaxValueValidator(1000000000)])
    max_status = models.PositiveIntegerField(primary_key=False, validators=[MaxValueValidator(1000000000)])
    status = models.CharField(max_length=256)
    
    def __str__(self):                                           # 🧸💬 Default call object reply __str__
        return self._id
```

### MongoDB 🥭 in database connection - sample find collection and client connectivity

🐑💬 ➰ Database connections and memory management for the database are handled under COM level but for the database driver wrapper they are managed on top of the natural database driver make sure you set the right permissions and correct versions and OS management for the database connection. In some cases, they are possible to connect but there are some message displays between the query result because of no backward compatibility software requirements and the machine cannot map output for the command. </br>
🐐💬 There is no native MongoDB connectivity in the Django data module but there are Oracle and SQL you had replaced the data communication path with the update codes to communicate with MongoDB. I saw of these requirements on the Internet and they are discussion about database debugging messages and operations. 👶💬 DekDee is listen for the input to facilitates </br>

```
def Find_mongoDBconnection(CollectionName, pipeline):
    # Set the Stable API version when creating a new client
    # 🧸💬 Initiate MongoClient for MongoDB communications, timeout and maxPoolSize for connections management
    client = MongoClient(uri, server_api=ServerApi('1'), connectTimeoutMS=3000, socketTimeoutMS=3000, maxPoolSize=50)
    
    # Define DB Name
    # 🧸💬 Define database name in MongoDB
    dbname = client['admin']
    
    # Define Collection
    # 🧸💬 Define collection name target
    collection = dbname[CollectionName]
    
    try:
        # 🧸💬 List collection from collection name called pipeline, MongoDB query string
        result = list(collection.find(pipeline))

    # 🧸💬 Exception for printing    
    except PyMongoError as e:
        print(f"Database operation failed: {e}")
    
    return result
```

- - -

###  Read and respond to HTML document object from the value from data struct ✳️

👧💬 🎈 In some applications communication messages need to constructed as structs with templates that is because of debugging and validate of the method and work tracing backlog of the application features. </br>

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

- - -

### Event - listeners C#.net 🎸

```
constructor(props) {
    super(props);
    this.state = { username: "", name: "", lastname : "", department: "", email: "", password: "",
                    ck_register: false, currentCount: 0, errors: "", fetched_data: [], submit_btn: "Submit" };

    this.password_handleChange = this.password_handleChange.bind(this);
    this.username_handleChange = this.username_handleChange.bind(this);
    this.email_handleChange = this.email_handleChange.bind(this);
    this.name_handleChange = this.name_handleChange.bind(this);
    this.lastname_handleChange = this.lastname_handleChange.bind(this);
    this.department_handleChange = this.department_handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
    /*this.handleRegisterClick = this.handleRegisterClick.bind(this);*/
    this.handleRegisterCKClick = this.handleRegisterCKClick.bind(this);
}

Login_verification( ) {
    this.populateUserData(this.state.username, this.state.password);
}

Add_employeedata() {
    this.AddEmployeeData(this.state.username, this.state.name, this.state.lastname, this.state.department,
        this.state.password, this.state.email);
}
```
