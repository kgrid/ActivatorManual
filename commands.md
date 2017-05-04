# Commands

There are multiple REST API commands that can be utilized when working with an Activator. Most arkID will be formatted as **ark:/.../...**.

_See what KO are on shelf._

```
GET {{baseUrl}}/shelf
```



_See details \(url, payload, input and output message\) for a specific KO on shelf._

```
GET {{baseUrl}}/shelf/arkID
```



_Add/update KO to the shelf by Ark ID. _

```
PUT {{baseUrl}}/shelf/arkID
```



_Execute KO._

```
POST {{baseUrl}}/knowledgeObject/arkID/result
```



_Remove KO from shelf._

```
DELETE {{baseUrl}}/shelf/arkID
```



