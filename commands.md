#Commands
Below is al its of available REST API commands that can be utilized when working with the execution stack.


```
# See what KO are on shelf
GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf


# See details (url, payload, input and output message) for a specific KO on shelf
GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/arkID


# Add/update KO to the shelf by Ark ID
PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/arkID


# Execute KO
POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/arkID/result


# Remove KO from shelf
DELETE http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/arkID

```

