# Getting Started
1. Whose responsibility is it to make the input/output specs? Authors or executers?


1. Add knowledge object of interest onto shelf.
  ```
  PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/ark:/ArkID
  ```
2. Check shelf to make sure the knowledge object was properly added.

  ```
  GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/
  ```

3. Add body and tests (optional), and execute knowledge object.
```
POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/ark:/ArkID/result
```