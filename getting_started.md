# Getting Started
**Whose responsibility is it to make the input/output specs? Authors or executors?**


1. Find the knowledge objects Ark ID. The ArkID can be found on ObjectTeller.
2. Using REST API commands, add knowledge object to shelf.
  ```
  PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/ark:/ArkID
  ```
2. Check the shelf to make sure the knowledge object ArkID was properly added. If your ArkID of interest is not on the shelf, double check you have the correct ArkID and re-do step 2.

  ```
  GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/
  ```

3. Add body (input parameters) and tests (optional). Execute the  knowledge object.
```
POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/ark:/ArkID/result
```