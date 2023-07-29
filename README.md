# Charles HW Traffic capture

## Ex_0: 
Focus on the following requests:
Write `ip number` in `Filter` in tab `structure`
```
Protocol: http
IP: 162.55.220.72
Port: 5007
```

## Ex_1:   
```
Method: GET  
EndPoint: /get_method  
request url params:  
 name: str  
 age: int
```

response: 
```
[
    “Str”,
    “Str”
]
```

Task:
Change url in `Charles Proxy` so you can change the name of  `Postman` request to your name that you create in `Charles Proxy`. Do this with `Rewrite` and with `Breakpoint`. 


## How to do Ex_1:
Use this URI in Charles `http://162.55.220.72:5007/get_method?name=Mariia&age=35` 
In  `BreakPoints` change response text in `Edit Response` from `Mariia` to `Dariia`.
Or use can sniff the request. Go to `Edit request` and change the name. 

In `Rewrite` create a sniffing in `Modify Query Param` in request:   
`Match` - that will be changed (Mariia)   
`Replace` - the new pattern (Dariia)    
Write 'name' of variable in Match and in Replace fields.  

## Ex_2:
```
Method: POST
EndPoint: /user_info_3
request form data: 
 name: str
 age: int
 salary: int
```

response: 
```
{'name': name,
          'age': age,
          'salary': salary,
          'family': {'children': [['Alex', 24], ['Kate', 12]],
                     'u_salary_1_5_year': salary * 4}}
```

Task:
Sniff  `body` in `Charles` so in request comes `salary` from `Postman` and in `u_salary_1_5_year` comes the number that is less than in request `salary`.
Do this with `Rewrite` and with `Breakpoints`.   


## How to do Ex_2:
Use this URI in Charles `http://162.55.220.72:5007/user_info_3`
In  `BreakPoints`  change `u_salary_1_5_year` in `Edit Response`

In `Rewrite` change `BODY Response`:   
`Match` - that will be changed ("u_salary_1_5_year":6000)   
`Replace` - the new pattern ("u_salary_1_5_year":1000)    
	
## Ex_3:
```
Method: GET
EndPoint: /object_info_1
request url params: 
 name: str
 age: int
 weight: int
```

response: 
```
{'name': name,
          'age': age,
          'daily_food': weight * 0.012,
          'daily_sleep': weight * 2.5}
```

Task:

Sniff request parameters in Charles so that Postman receive response with another name, daily_food > weight from request, and daily_sleep < weight from request. Do this with `Rewrite` and with `Breakpoints`. 


## How to do Ex_3:
Use this URI in Charles `http://162.55.220.72:5007/object_info_1?name=Mariia&age=35&weight=56` 

In  `BreakPoints` change  name / daily_food / daily_sleep in "Edit Response".    
In `Rewrite` sniff `Modify Query Param` in request:   
`Match` - that will be changed 
+ name : name
+ value : Mariia

`Replace` - the new pattern:
+ name: name
+ value: Rose

In `Rewrite` sniff  `Body` Response
1. daily food: 
Match:  0.672
Replace: 57   
2. daily_sleep 
Match: 140
Replace: 55



## Ex_4:
```
Method: GET
EndPoint: /object_info_3
request url params: 
 name: str
 age: int
 salary: int
```

response: 
```
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

Task:
   
Make Charles do so that server showed 500 Status Code.   
Make Charles do so that server showed 405 Status Code. 
Do this with `Rewrite` and with `Breakpoints`. 
## How to do Ex_4:

Use this URI in Charles `http://162.55.220.72:5007/object_info_3?name=Mariia&age=35&salary=1500 `

### If we want to test frontend(changing response to see how front is answering):
In `BreakPoints` sniff response status code in  "Edit Response"  from 200 OK to get on front 500 ОК / 405 ОК   

Create sniffing rule in `Rewrite` Response Status code changing. Change the value from 200 to 500/405  to get it on front.
### If we want to test Backend (change request to see how back is answering):
In `BreakPoints` create a sniffing rule. 
1. Sniff request method from GET to POST in  "Edit request"  to get 405 error on server.
2. Sniff  query parameter 'salary' in  "Edit request"  to get 500 error on server. 

Create sniffing rule in `Rewrite`.
1. to get 500 error from server change values of  parameters to different type in `Modify Query Param`:
Match: name: Salary; value: _ (empty)
Replace: name: salary; value: sal

2. to get 405 error from server change METHOD  in URL: 
Match : /object_info_3
Replace: /user_info_3

## Ex_5:
```
Method: GET
EndPoint: /object_info_4
request url params: 
 name: str
 age: int
 salary: int
```

response: 
```
{'name': name,
          'age': int(age),
          'salary': [salary, str(salary * 2), str(salary * 3)]}
```


Task: 
 1. Make with Charles that the server give a 405 error.   
 2. Sniff `salary` in request   
 3. Sniff `(salary * 2)` in  response   
Do this with `Rewrite` and with `Breakpoints`.

## How to do Ex_5:
Use this URI: `http://162.55.220.72:5007/object_info_4?name=Mariia&age=35&salary=1500`

`Breakpoints`:
1. Sniff response status code in  "Edit Response"  from 200 OK to  405 ОК 
2. In `Edit request` change value of parameter `salary`
3. In `Edit response` change value of parameter `(salary * 2)`
`Rewrite`:
Testing frontend:
1. To get 405 error in `Rewrite` in `Response Status` choose 405 instead 200 

* To change salary*2 of response use `BODY` of `Response` :   
	Match -3000 (salary * 2) 
	Replace - 15000  
  
Testing backend:  
1. To get 405 error from server change METHOD  in URL: 
Match : /object_info_4
Replace: /user_info_3
2.  For sniffing salary in request in Rewrite choose `Modify Query Param` in  request:    
	Match: 
    + name: salary
    + value: 1500

    Replace: 
    + name: salary
    + value: 5000 


## Ex_6:
```
Method: POST
EndPoint: /user_info_2
request form data: 
 name: str
 age: int
 salary: int
```

response: 
```
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


Task:
1. Make with Charles so , Postman reveivw the answer in which `qa_salary_after_1.5_year` will be renamed in`qa_salary_after_1.5_month`   
2. Make with Charles so `qa_salary_after_3.5_years` will be less then `qa_salary_after_12_months` in  response   
Do this with `Rewrite` and with `Breakpoints`.

 ## How to do Ex_6:
`Breakpoints`:
1. In `Edit response` change name of parameter `qa_salary_after_1.5_year` to `qa_salary_after_1.5_month`
2. In `Edit response` change value of parameter `qa_salary_after_3.5_years` less then `qa_salary_after_12_months`

`Rewrite`:
1. In `BODY` `Response`:    

	Match - qa_salary_after_1.5_year   
	Raplace - qa_salary_after_1.5_month  
and
2. In `BODY` `Response`: 
	Match - 5700   
	Raplace - 3000  