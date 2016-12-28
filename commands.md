#Commands

There are multiple REST API commands that can be utilized when working with the execution stack. Most arkID will be formatted like **ark:/01234/0123456789**.

1. See what KO are on shelf.
    ```
GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf

    ```
2. See details (url, payload, input and output message) for a specific KO on shelf.
    ```
GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/arkID
    ```
    
3. Add/update KO to the shelf by Ark ID. 
    ```
PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/arkID
    ```

4. Execute KO.
    ```
POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/arkID/result
    ```

5. Remove KO from shelf.
    ```
DELETE http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/arkID
    ```





