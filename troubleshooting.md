# Troubleshooting

Here are some common errors that we identified during the execution process.

**Execution Stack Environment**

To learn more about the execution stack environment, run the following REST API command.

```
GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/env
```

**Unexpected 'h'**

If you run the POST command, and receive this response, there is an error in the payload function name. Find the KO on Object Teller, click edit, payload and identify the payload function name. This is a required field, so if the payload function name is missing you will receive this error. If the payload function ends with \(\), you will also receive this error. Make sure the payload function is formatted as follows: payloadFunction, not payloadFunction\(\) or empty.

**Missing Body**

If you run the POST command, and receive the follow response, the input body is missing. 

```
{
  "timestamp": 1485807659490,
  "status": 400,
  "error": "Bad Request",
  "exception": "org.springframework.http.converter.HttpMessageNotReadableException",
  "message": "Required request body is missing: public org.springframework.http.ResponseEntity<org.uofm.ot.executionStack.transferObjects.Result> org.uofm.ot.executionStack.controller.ExecutionStackController.getResultByArkId(java.util.Map<java.lang.String, java.lang.Object>,org.uofm.ot.executionStack.transferObjects.ArkId)",
  "path": "/ExecutionStack/knowledgeObject/ark:/99999/fk4fj2qx12/result"
}
```

**Missing Parameters or Too Many Parameters**

The execution stack will let you know if you are missing parameters, or have too many parameters. For example, you may get the following error if you have more than 1 parameter:

```
{
  "success": 0,
  "result": null,
  "errorMessage": "Number of input parameters should be 1.",
  "source": "ark:/99999/fk4fj2qx12"
}
```

or this error if you are missing a parameter:

```
{
  "success": 0,
  "result": null,
  "errorMessage": " Input parameter age is missing.",
  "source": "ark:/99999/fk4fj2qx12"
}
```



