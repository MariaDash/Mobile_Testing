# Fiddler HomeWork

## Ex_0: Filter requests by ip (Contains:162.55.220.72)

```
Protocol: http
IP: 162.55.220.72
Port: 5005
```

## Ex_1: 

```
Method: GET
EndPoint: /get_method
request URL params: 
 name: str
 age: int
```
```
response: 
[
    "Str",
    "Str"
]
```

### Task:
Create rule:   
* Sniff URL to change request name that you wrote in Postman.

### How to do:
Here we will change value of parameter `name` in request:

+ Enable Rules.
+ Add rule:
+ Conditions: URL contains `http://162.55.220.72:5007`
+ Actions: Update Query Params / Find and replace (Mariia -> Dariya)

### Task:
Create rule: 
* Sniff URL to change request age that you wrote in Postman.

### How to do:
Here we will change value of parameter `age` in request:

+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007`
+ Actions: Update Query Params / Find and replace (35 -> 55)


## Ex_2:
```
Method: POST
EndPoint: /user_info_3
request form data: 
 name: str
 age: int
 salary: int
```
```
response: 
{'name': name,
          'age': age,
          'salary': salary,
          'family': {'children': [['Alex', 24], ['Kate', 12]],
                     'u_salary_1_5_year': salary * 4}}
```
### Task:
Create rules:
1. Sniff request body to change name that comes from Postman.
2. Sniff request body to change age that comes from Postman.
3. Sniff request body to change salary that comes from Postman. 
4. Sniff request body to delete age that comes from Postman.  (Get 500 error)

### How to do:
Here we will change value of parameters `name`, `age`, `salary` and delete parameter `age` in  Request Body:

+ Add rule:
+ Conditions: `URL: http://162.55.220.72:5007`
+ Actions: Update Request Body/ Find and replace :
1. Mariia -> Dariiya
2. 35->55
3. 1500->3000
4. "age":35->Null (empty) or Remove "age":35

### Task:
Create rules:
 - In response change children to neighbors. 
 - In response change u_salary_1_5_year value to differect digit. 
 - In response delete salary parameter.

### How to do:

Here we will change name of parameter `children`, value of parameter `u_salary_1_5_year` and delete `salary` parameter in Response Body

+ Add rule:
+ Conditions: `URL http://162.55.220.72:5007`
+ Actions: Update Response Body / Find and replace 
1. children -> neighbors
2. "u_salary_1_5_year":6000 -> "u_salary_1_5_year":12000
3. opt.1. "salary":2000, -> Null (empty)
   opt.2. remove "salary":2000



## Ex_3:
```
Method: GET
EndPoint: /object_info_1
request URL params: 
 name: str
 age: int
 weight: int
```
```
response: 
{'name': name,
          'age': age,
          'daily_food': weight * 0.012,
          'daily_sleep': weight * 2.5}
```
### Task:
Create rules:
 - Sniff URL to change name that comes from Postman to different name in request.
 - Sniff URL to change age  that comes from Postman to different age in request.
 - Sniff URL to remove weight  that comes from Postman in request.

### How to do:
Here we will change value of parameter `name`,`age`, `salary` and remove parameter `weight`in request params:

+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007`
+ Actions: Update Query Params / Find and replace
1. Mariia -> Dariiya
2. 35 -> 55
3. opt.1  "weight":56 -> Null
   opt.2. remove "weight":56


### Task:
Create rules:

 - In response delete parameter  `daily_food`.
 - In response change the value of `daily_food` parameter to different digit. 
 - In response rename parameter `daily_sleep` to `sleep`
 - In response change value of parameter `daily_sleep` to different digit. 

### How to do:
Here we will change `Response Body`:
+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007`
+ Actions: Update Response Body / Find and replace
1. opt.1 "daily_food": 0.672 -> Null
   opt.2  remove "daily_food": 0.672
2. 0.672 -> 1.1
3. "daily_sleep" -> "sleep"
4. "daily_sleep": 140.0 -> "daily_sleep": 300.0

## Ex_4:
```
Method: GET
EndPoint: /object_info_3
request url params: 
 name: str
 age: int
 salary: int
```
```
response: 
{'name': name,
          'age': age,
          'salary': salary,
          'family': {'children': [['Alex', 24], ['Kate', 12]],
                     'pets': {'cat':{'name':'Sunny',
                                     'age': 3},
                              'dog':{'name':'Luky',
                                     'age': 4}},
                     'u_salary_1_5_year': salary * 4}
          }
```
### Task:
Create rules:
 - Sniff url to change name that comes from Postman to different name in request.
 - Sniff url to change age that comes from Postman to different age in request.
 - Sniff url to remove name that comes from Postman in request.
### How to do:
Here we will change value of parameter `name`,`age`, and remove parameter `name`in request params:

+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007
+ Actions: Update Query Params / Find and replace
1. Mariia -> Dariiya
2. 35 -> 55
3. opt.1  "name":"Mariia" -> Null
   opt.2. remove "name":"Mariia"
### Task:
Create rules:
 - In response delete parameter salary.
 - In response change value of parameter cat to different json. 
 - Receive 405 status code

### How to do:
Here we will change `Response Body`:
+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007`
+ Actions: Update Response Body / Find and replace
1. opt.1 "salary": 1500 -> Null
   opt.2  remove "salary": 1500
2. Opt.1 in `Update Response Body`
```
"cat": { "age": 3, "name": "Sunny"}
```
Change to
```
"cat": {
                "weight": 15,
                "name": "Denny"
            }
```
   Opt.2 In `Manual response` change the whole response
3. In request: Opt.1 Change `URL` from GET to POST request (take from Postman)
               Opt. 2 In  `Update request header` change method from `GET` to `POST`
   In response: In `Update Response Header` change status code from `200` to `405`

## Ex_5:
```
Method: GET
EndPoint: /object_info_4
request url params: 
 name: str
 age: int
 salary: int
```
```
response: 
{'name': name,
          'age': int(age),
          'salary': [salary, str(salary * 2), str(salary * 3)]}
```

### Task:
Create rules:
 - Sniff url to change name  that comes from Postman to different name in request.
 - Sniff url to change age  that comes from Postman to different age in request.
 - Sniff url in request to remove salary that you wrote in Postman.
### How to do:
Here we will change value of parameter `name`,`age`, and remove parameter `salary`in request params:

+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007
+ Actions: Update Query Params / Find and replace
1. Mariia -> Dariiya
2. 35 -> 55
3. opt.1  "salary":1500 -> Null
   opt.2. remove "salary":1500
### Task:
Create rules:

 - In response delete parameter salary.
 - In response change value of parameter salary to string value. 
 - Receive 405 status code

### How to do:
Here we will change `Response Body`:
+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007`
+ Actions: Update Response Body / Find and replace
1. opt.1 "salary": 1500 -> Null
   opt.2  remove "salary": 1500
2. "salary": [ 1500, "3000", "4500"] -> "salary": "a_lot"
3. In request: Opt.1 Change `URL` from GET to POST request (take from Postman)
               Opt. 2 In  `Update request header` change method from `GET` to `POST`
   In response: In `Update Response Header` change status code from `200` to `405`


## Ex_6:
```
Method: POST
EndPoint: /user_info_2
request form data: 
 name: str
 age: int
 salary: int
```
```
response: 
{'start_qa_salary': salary,
          'qa_salary_after_6_months': salary * 2,
          'qa_salary_after_12_months': salary * 2.7,
          'qa_salary_after_1.5_year': salary * 3.3,
          'qa_salary_after_3.5_years': salary * 3.8,
          'person': {'u_name': [user_name, salary, age],
                     'u_age': age,
                     'u_salary_5_years': salary * 4.2}
          }
```

### Task:
Create rules:
 - Sniff body request to change age that you wrote in Postman.
 - Sniff body request to change salary that you wrote in Postman.
 - Sniff body request to delete salary that you wrote in Postman.

### How to do:
Here we will change value of parameter `name`,`age`, and remove parameter `salary`in request params:

+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007
+ Actions: Update Query Params / Find and replace
1. 35 -> 55
2. 1500 -> 5000
3. opt.1  "salary":1500 -> Null
   opt.2. remove "salary":1500
### Task:
Create rules:
 - Sniff response to rename qa_salary_after_6_months to qa_salary_after_10_months. 
- In response change value of  qa_salary_after_1.5_year to different digit. 
 - In response delete parameter person. 
 - In response change value of parameter person from json to xml. 

### How to do:
Here we will change `Response Body`:
+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007`
+ Actions: Update Response Body / Find and replace
1. "qa_salary_after_6_months" -> "qa_salary_after_10_months"
2. "qa_salary_after_1.5_year": 4950.0 ->  "qa_salary_after_1.5_year": 5000
3. opt.1  
```
"person": {
        "u_age": 35,
        "u_name": [
            "Mariia",
            1500,
            35
        ],
        "u_salary_5_years": 6300.0
    }
```
Change to `Null`
   opt.2  remove 
```
   "person": {
        "u_age": 35,
        "u_name": [
            "Mariia",
            1500,
            35
        ],
        "u_salary_5_years": 6300.0
    }
```
4.  Opt.1 in `Update Response Body`
```
   "person": {
        "u_age": 35,
        "u_name": [
            "Mariia",
            1500,
            35
        ],
        "u_salary_5_years": 6300.0
    }
```
Change to
```
<?xml version="1.0" encoding="UTF-8"?>
<root>
   <u_age>35</u_age>
   <u_name>
      <element>Mariia</element>
      <element>1500</element>
      <element>35</element>
   </u_name>
   <u_salary_5_years>6300.0</u_salary_5_years>
</root>
```
   Opt.2 In `Manual response` change the whole response