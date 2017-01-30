# Commands

There are multiple REST API commands that can be utilized when working with the execution stack. Most arkID will be formatted like **ark:/01234/0123456789**.

_See what KO are on shelf._

```
GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf
```



_See details \(url, payload, input and output message\) for a specific KO on shelf._

```
GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/arkID
```



_Add/update KO to the shelf by Ark ID. _

```
PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/arkID
```



_Execute KO._

```
POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/arkID/result
```



_Remove KO from shelf._

```
DELETE http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/arkID
```



