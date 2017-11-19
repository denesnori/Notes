## dumps and loads

- converts between strings and objects

### ```json.dumps(object)``` -> JSON string
- retirn a string representing a json object from an object

```
import json
obj = { 'test': 1 }

json.dumps(obj) # '{"test":1}'
type(json.dumps(obj)) #<class 'str'>
```

### ```json.loads()```
returns an object from a string represeonting a json object

## dump and load
- converts between files and objects

### ```json.dump()```
- write to a file instead of a string

### ```json.load()```
- read from a file instead of a string

```
with open('data.json') as fh:
  a = json.load(fh)
```
htttp://jsonplaceholder.ytpicode.com/posts/1

dir(response)
response.headers it is a dictionary
response.json() dictionary

http://data.gov.uk

Reference:
- [stackoverflow - json.dump(s), json.load(s)](https://stackoverflow.com/questions/32911336/what-is-the-difference-between-json-dumps-and-json-load)
