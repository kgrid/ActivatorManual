# Test Functions

When executing knowledge objects on the execution stack, it is helpful to include test functions in order to ensure the knowledge objects are working properly. Here we have included some test functions that may be helpful at each step in the process.


### Putting Knowledge Objects on Shelf
To make sure the code executed successfully:
```
tests["Status code is 200"] = responseCode.code === 200;
```

### Checking if Knowledge Objects are on Shelf
To make sure the code executed successfully:
```
tests["Status code is 200"] = responseCode.code === 200;
```

### Executing Knowledge Objects
To make sure the code executed successfully:
```
tests["Status code is 200"] = responseCode.code === 200;
```
To check in the output was 
```
tests["Body matches string"] = responseBody.has("string_you_want_to_search");
```
```
tests["Successful POST request"] = responseCode.code === 201 || responseCode.code === 202;
```
