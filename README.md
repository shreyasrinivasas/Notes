# Notes

JSON JavaScript Object Notation is a **format for structuring data**
It is mainly used for **storing and transferring data** between the **browser and the server**.
Python too supports JSON with a built-in package called json
This package provides all the necessary tools for working with JSON Objects including parsing, serializing, deserializing, and many more. 


[Convert the JSON objects to Python objects and vice-versa.]
import json
emp='{"id":"087","name":"Shreya","dept":"ECE"}'
print(emp)
print(type(emp))

#Convert JSON string to Python dict
#we need to load it in order to convert into dictionary
**emp_dict=json.loads(emp)**
print(emp_dict)
print(type(emp_dict))

#Convert Python dict to JSON string

**emp_json=json.dumps(emp_dict)**
print(emp_json)
print(type(emp_json))

#output>>
{"id":"087","name":"Shreya","dept":"ECE"}
<class 'str'>
{'id': '087', 'name': 'Shreya', 'dept': 'ECE'}
<class 'dict'>
{"id": "087", "name": "Shreya", "dept": "ECE"}
<class 'str'>

# Working With JSON Data in Python
JSON >  It means that a script (executable) file which is made of text in a programming language, is used to store and transfer the data.

The text in JSON is done through quoted-string which contains the value in key-value mapping within { }
It is similar to the dictionary in Python

#{key:value mapping}
a ={"name":"John",
   "age":31,
    "Salary":25000}
print(a)
print(type(a))


b=json.dumps(a)
print(b)
print(type(b))

#OUTPUT>>
{'name': 'John', 'age': 31, 'Salary': 25000}
<class 'dict'>
{"name": "John", "age": 31, "Salary": 25000}
<class 'str'>


 **Python program showing that json support different primitive types**

Serializing JSON : 
The process of encoding JSON is usually called serialization.
To handle the data flow in a file, the JSON library in Python uses **dump()** function to convert the **Python** objects into their respective **JSON** object, so it makes easy to write data to files. See the following table given below.  


[Python ->	JSON object]
dict	-> object
list,tuple ->	array
str	-> string
int, long, float-> numbers
True	-> true
False	-> false
None ->	null



var = {
	"Subjects": {
				"Maths":85,
				"Physics":90
				}
	}
  
**Serializing JSON **: (Python -> JSON)

with open("Sample.json", "w") as p:
     json.dump(var, p)

#Here, the dump() takes two arguments first, the data object to be serialized, and second the object to which it will be written(Byte format). 

**Deserializing JSON **: (JSON -> python)

conversion of JSON objects into their respective Python objects
with open("Sample.json", "r") as read_it:
     data = json.load(read_it)

Deserialization Example : 
json_var ="""
{
	"Country": {
		"name": "INDIA",
		"Languages_spoken": [
			{
				"names": ["Hindi", "English", "Bengali", "Telugu"]
			}
		]
	}
}
"""
var = json.loads(json_var)

# Read JSON file using Python
# This example shows reading from both string and JSON file. The file shown above is used.

#Python program to readjson file
import json

#JSON string
a = '{"name": "Bob", "languages": "English"}'
#deserializes into dict and returns dict.
y = json.loads(a)
print("JSON string = ", y)
print()


#JSON file
f = open ('data.json', "r")
#Reading from file
data = json.loads(f.read())
#Iterating through the jsonlist
for i in data['emp_details']:
	print(i)
#Closing file
f.close()


