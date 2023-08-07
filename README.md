# Fiddler Homework

## Ex_0: Filter requests by ip (Contains: 162.55.220.72)
Enable `System Proxy`
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
***!!!Send the request first before executing rules!!!***
+ Enable `Rules`.
### Task:
Create rule:   
* Sniff URL to change request name that you wrote in Postman.

### How to do:
Here we will change value of parameter `name` in request:

Opt.1. With `Update Query Params`
+ Add rule:
+ Conditions: URL contains `http://162.55.220.72:5007` we can use `contains` or `is equal to`
+ Actions: Update Query Params, Key: name / Find and replace (Mariia -> Dariya)

Opt.2.With `URL`
+ Add rule:
+ Conditions: URL contains `http://162.55.220.72:5007`
+ Actions: Update URL / Find and replace (Mariia -> Dariya)
### Task:
Create rule: 
* Sniff URL to change request age that you wrote in Postman.

### How to do:
Here we will change value of parameter `age` in request:

Opt.1. With `Update Query Params`
+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007`
+ Actions: Update Query Params , Key: age/ Find and replace (35 -> 55)

Opt.2.With `URL`
+ Add rule:
+ Conditions: URL contains `http://162.55.220.72:5007`
+ Actions: Update URL / Find and replace ((35 -> 55)

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
***!!!Send the request first before executing rules!!!***
### Task:
Create rules:
1. Sniff request body to change name that comes from Postman.
2. Sniff request body to change age that comes from Postman.
3. Sniff request body to change salary that comes from Postman. 
4. Sniff request body to delete age that comes from Postman.  (Get 500 error)

### How to do:
Here we will change value of parameters `name`, `age`, `salary` and delete parameter `age` in  `Request Body`:

+ Add rule:
+ Conditions: `URL: http://162.55.220.72:5007`
+ Actions: Update Request Body/ Find and replace :
1. Mariia -> Dariiya
2. 35->55
3. 1500->5000
4. to get 500 error I can remove all body, using `Update Request Body/Remove` option

or `Update Request Body/Set Value/JSON`
```
Content-Disposition: form-data; name="name"

Mariia

Content-Disposition: form-data; name="salary"

1500
```
### Task:
Create rules:
 - In response change children to neighbors. 
 - In response change u_salary_1_5_year value to differect digit. 
 - In response delete salary parameter.

### How to do:

Here we will change name of parameter `children`, value of parameter `u_salary_1_5_year` and delete `salary` parameter in `Response Body`

+ Add rule:
+ Conditions: `URL http://162.55.220.72:5007`
+ Actions: Update Response Body / Find and replace 
1. children -> neighbors
2. 6000 -> 12000
3. Deleting `salary`:
  
Opt.1. Use Manual response:
```
HTTP/1.0 200 OK
Content-Type: application/json
Content-Length: 116
Server: Werkzeug/2.0.1 Python/3.8.10
Date: Sun, 06 Aug 2023 20:34:11 GMT

{"age":"35",
"family":{"children":
[["Alex",24],["Kate",12]],
"u_salary_1_5_year":6000},
"name":"Mariia"
}
   
```
 
Opt.2.  Use `Update Response Body/Find and replace `
   
"salary":1500, ->  (empty)
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
***!!!Send the request first before executing rules!!!***
### Task:
Create rules:
 - Sniff URL to change name that comes from Postman to different name in request.
 - Sniff URL to change age  that comes from Postman to different age in request.
 - Sniff URL to remove weight  that comes from Postman in request.

### How to do:
Here we will change value of parameter `name`,`age`, `salary` and remove parameter `weight`in request params:

+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007`
+ Actions: `Update Query Params / Find and replace` or `Set value`
1. Mariia -> Dariiya
2. 35 -> 55
3. `Update Query Params/Remove` : weight


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
1.  opt.1 "daily_food": 0.672 -> (empty)
   
    opt.2. use `Manual response`:
```
HTTP/1.0 200 OK
Content-Type: application/json
Content-Length: 71
Server: Werkzeug/2.0.1 Python/3.8.10
Date: Sun, 06 Aug 2023 21:18:17 GMT

{
    "age": 35,
    "daily_sleep": 140.0,
    "name": "Mariia"
}
```
`Update Response Body / Find and replace`:

3. 0.672 -> 1.1
  
5. "daily_sleep" -> "sleep"
  
7. 140.0 -> 300.0

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
***!!!Send the request first before executing rules!!!***
### Task:
Create rules:
 - Sniff url to change name that comes from Postman to different name in request.
 - Sniff url to change age that comes from Postman to different age in request.
 - Sniff url to remove name that comes from Postman in request.
### How to do:
Here we will change value of parameter `name`,`age`, and remove parameter `name`in request params:

+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007
+ Actions: Update Query Params / Find and replace or use `Set value`
1. Mariia -> Dariiya
2. 35 -> 55
3. `remove`: "name"
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
1. opt.1 "salary": 1500 -> (empty)
   
opt.2. with `Manual Response`
```
HTTP/1.0 200 OK
Content-Type: application/json
Content-Length: 186
Server: Werkzeug/2.0.1 Python/3.8.10
Date: Sun, 06 Aug 2023 22:06:45 GMT

{
    "age": "35",
    "family": {
        "children": [
            [
                "Alex",
                24
            ],
            [
                "Kate",
                12
            ]
        ],
        "pets": {
            "cat": {
                "age": 3,
                "name": "Sunny"
            },
            "dog": {
                "age": 4,
                "name": "Luky"
            }
        },
        "u_salary_1_5_year": 6000
    },
    "name": "Mariia"
   
}
```
2. Use `Manual response`:
```  
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 237
Server: Werkzeug/2.0.1 Python/3.8.10
Date: Sun, 06 Aug 2023 22:17:08 GMT

{: "age": "35", "family": { "children": [ [ "Alex", 24 ], [ "Kate", 12 ] ], "pets": { "cat": { "weight": 15, "name": "Denny" }, "dog": { "age": 4, "name": "Luky" } }, "u_salary_1_5_year": 6000 }, "name": "Mariia", "salary": 1500
}: 
```
 
3. **In request**: Opt.1 Change `URL` from GET to POST request (take POST URL from Postman)
   
**In response**:
1) Use `Manual Response`
```
HTTP/1.0 405 Method Not Allowed
Content-Type: application/json
Content-Length: 538
Server: Werkzeug/2.0.1 Python/3.8.10
Date: Sun, 06 Aug 2023 22:28:53 GMT

{
    "age": "35",
    "family": {
        "children": [
            [
                "Alex",
                24
            ],
            [
                "Kate",
                12
            ]
        ],
        "pets": {
            "cat": {
                "age": 3,
                "name": "Sunny"
            },
            "dog": {
                "age": 4,
                "name": "Luky"
            }
        },
        "u_salary_1_5_year": 6000
    },
    "name": "Mariia",
    "salary": 1500
}
```
2) With `Update Status Code`

Choose `405 Method not Allowed`
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
***!!!Send the request first before executing rules!!!***
### Task:
Create rules:
 - Sniff url to change name  that comes from Postman to different name in request.
 - Sniff url to change age  that comes from Postman to different age in request.
 - Sniff url in request to remove salary that you wrote in Postman.
### How to do:
Here we will change value of parameter `name`,`age`, and remove parameter `salary`in request params:

+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007
+ Actions: opt.1. `Update Query Params/name / Find and replace` 
1. Mariia -> Dariiya
 or opt.2. `Set value` `Denny`
3. Actions: opt.1. `Update Query Params/name / Find and replace` 35 -> 18
   opt.2. `Set value` `18`
4. `Update Query Params/name/Remove` "salary"
### Task:
Create rules:

 - In response delete parameter salary.
 - In response change value of parameter salary to string value. 
 - Receive 405 status code

### How to do:
Here we will change `Response Body`:
+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007`
1. with `Manual response`:
```
HTTP/1.0 200 OK
Content-Type: application/json
Content-Length: 57
Server: Werkzeug/2.0.1 Python/3.8.10
Date: Mon, 07 Aug 2023 07:25:00 GMT

{
    "age": 35,
    "name": "Mariia",
   }

```
+ Actions: `Update Response Body / Find and replace`
2. opt.1 "salary": 1500 -> (empty)
   opt.2  in `Update Query Params` `remove/key:salary`
3. Use `Manual Response`:
```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 66
Server: Werkzeug/2.0.1 Python/3.8.10
Date: Mon, 07 Aug 2023 08:10:52 GMT

{
    "age": 35,
    "name": "Mariia",
    "salary": "a lot"
}
```
4. `In request`: Change `URL` from GET to POST request (take from Postman)
   `In Response`: Opt.1. Use `Manual Response`:
```
   HTTP/1.0 405 Method Not Allowed
Content-Type: application/json
Content-Length: 117
Server: Werkzeug/2.0.1 Python/3.8.10
Date: Mon, 07 Aug 2023 08:18:40 GMT

{
    "age": 35,
    "name": "Mariia",
    "salary": [
        1500,
        "3000",
        "4500"
    ]
}
```
                  Opt.2. With `Update Status Code`

Choose `405 Method not Allowed`
            


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
***!!!Send the request first before executing rules!!!***
### Task:
Create rules:
 - Sniff body request to change age that you wrote in Postman.
 - Sniff body request to change salary that you wrote in Postman.
 - Sniff body request to delete salary that you wrote in Postman.

### How to do:
Here we will change value of parameter `name`,`age`, and remove parameter `salary`in request params:

+ Add rule:
+ Conditions: `URL contains http://162.55.220.72:5007
+ Actions: `Update Request Body` / Find and replace
1. 35 -> 18
2. 1500 -> 5000
3. opt.1  "salary":1500 -> empty
   opt.2. `Update Query Params`:`Remove` "salary"
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
3. opt.1  `Update Response Body/Set value/JSON`:
```
{
    
    "qa_salary_after_1.5_year": 4950.0,
    "qa_salary_after_12_months": 4050.0000000000005,
    "qa_salary_after_3.5_years": 5700.0,
    "qa_salary_after_6_months": 3000,
    "start_qa_salary": 1500
}
```
   opt.2  Use `Manual Response`:
```
HTTP/1.0 200 OK
Content-Type: application/json
Content-Length: 211
Server: Werkzeug/2.0.1 Python/3.8.10
Date: Mon, 07 Aug 2023 08:40:51 GMT

{
    "qa_salary_after_1.5_year": 4950.0,
    "qa_salary_after_12_months": 4050.0000000000005,
    "qa_salary_after_3.5_years": 5700.0,
    "qa_salary_after_6_months": 3000,
    "start_qa_salary": 1500
}   
```
4. In `Manual response` change the whole response
```
HTTP/1.0 200 OK
Content-Type: application/json
Content-Length: 452
Server: Werkzeug/2.0.1 Python/3.8.10
Date: Mon, 07 Aug 2023 08:52:14 GMT

{
   <person>
        <u_age>35</u_age>
        <u_name>
            <name>Maiia</name>
            <salary>1500</salary>
            <age>35</age>
        </u_name>
        <u_salary_5_years>6300.0</u_salary_5_years>
    </person>, 
    "qa_salary_after_1.5_year": 4950.0,
    "qa_salary_after_12_months": 4050.0000000000005,
    "qa_salary_after_3.5_years": 5700.0,
    "qa_salary_after_6_months": 3000,
    "start_qa_salary": 1500
}
```
