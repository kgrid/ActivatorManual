# Troubleshooting

Here are some common errors that we identified during the execution process. 

**Activator Environment**

To learn more about the activator environment, run the following REST API command.

```
GET baseUrl/env
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

The activator will let you know if you are missing parameters, or have too many parameters. For example, you may get the following error if you have more than 1 parameter:

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

The KGrid Team has also created a Json-Formatted Postman Collection with Error Handling Messages to help trouble shoot.
'''
{
	"id": "407c8bf5-ee4a-0f2b-8073-ecc7984ba855",
	"name": "Error Message Handling ",
	"description": "Example REST API commands with KGrid test knowledge objects to aid in Error Message Handling.",
	"order": [
		"76af8e1e-b27e-69e5-56b9-ec2bcc7ed513",
		"dd6191e8-8165-bf90-eb9a-d0b870cc5d8e",
		"609faacd-a7fb-e6a8-e41a-6a12131984bc",
		"717080cc-0e69-4a6c-b94f-41bdc4991816",
		"7c9487c4-366f-ae65-d1c3-d6f3c3e91012",
		"65487ce9-ecd4-92ba-335e-8fe3dc24cefa",
		"8f143d19-a69a-544a-2285-e716d5bef7f7",
		"44640312-639a-6353-aff0-9891cdd9a20d",
		"5111ea0b-c0f1-543b-bd6d-53d8fca8f4af",
		"94df6a81-fb2b-c9a6-e583-9b5e80a4defb"
	],
	"folders": [],
	"timestamp": 1493149778578,
	"owner": "1316650",
	"public": false,
	"requests": [
		{
			"id": "44640312-639a-6353-aff0-9891cdd9a20d",
			"headers": "Content-Type: application/json\n",
			"url": "{{baseUrl}}/knowledgeObject/ark:/99999/fk4fj2qx12/result",
			"preRequestScript": null,
			"pathVariables": {},
			"method": "POST",
			"data": [],
			"dataMode": "raw",
			"tests": null,
			"currentHelper": "normal",
			"helperAttributes": {},
			"time": 1493238649135,
			"name": "Wrong Type of Input",
			"description": "",
			"collectionId": "407c8bf5-ee4a-0f2b-8073-ecc7984ba855",
			"responses": [],
			"rawModeData": "{\"words\":[\"hello\",\"world\"]}"
		},
		{
			"id": "5111ea0b-c0f1-543b-bd6d-53d8fca8f4af",
			"headers": "Content-Type: application/json\n",
			"url": "{{baseUrl}}/knowledgeObject/ark:/99999/fk4v41133q/result",
			"pathVariables": {},
			"preRequestScript": null,
			"method": "POST",
			"collectionId": "407c8bf5-ee4a-0f2b-8073-ecc7984ba855",
			"data": [],
			"dataMode": "raw",
			"name": "Input Value Out of Range",
			"description": "",
			"descriptionFormat": "html",
			"time": 1493922127318,
			"version": 2,
			"responses": [],
			"tests": null,
			"currentHelper": "normal",
			"helperAttributes": {},
			"rawModeData": "{\"a\":100,\"b\":10}"
		},
		{
			"id": "609faacd-a7fb-e6a8-e41a-6a12131984bc",
			"headers": "",
			"url": "{{baseUrl}}/knowledgeObject/ark:/99999/fk4fj2qx12/result",
			"pathVariables": {},
			"preRequestScript": null,
			"method": "POST",
			"collectionId": "407c8bf5-ee4a-0f2b-8073-ecc7984ba855",
			"data": null,
			"dataMode": "params",
			"name": "Missing content type",
			"description": "",
			"descriptionFormat": "html",
			"time": 1493237994487,
			"version": 2,
			"responses": [],
			"tests": null,
			"currentHelper": "normal",
			"helperAttributes": {}
		},
		{
			"id": "65487ce9-ecd4-92ba-335e-8fe3dc24cefa",
			"headers": "Content-Type: application/json\n",
			"url": "{{baseUrl}}/knowledgeObject/ark:/99999/fk4fj2qx12/result",
			"pathVariables": {},
			"preRequestScript": null,
			"method": "POST",
			"collectionId": "407c8bf5-ee4a-0f2b-8073-ecc7984ba855",
			"data": [],
			"dataMode": "raw",
			"name": "Missing Specific Input in Body",
			"description": "",
			"descriptionFormat": "html",
			"time": 1493238444989,
			"version": 2,
			"responses": [],
			"tests": null,
			"currentHelper": "normal",
			"helperAttributes": {},
			"rawModeData": "{\"word\":[\"hello\",\"world\"]}"
		},
		{
			"id": "717080cc-0e69-4a6c-b94f-41bdc4991816",
			"headers": "Content-Type: application/json\n",
			"url": "{{baseUrl}}/knowledgeObject/ark:/99999/fk4fj2qx12/result",
			"pathVariables": {},
			"preRequestScript": null,
			"method": "POST",
			"collectionId": "407c8bf5-ee4a-0f2b-8073-ecc7984ba855",
			"data": null,
			"dataMode": "params",
			"name": "Missing Request Body",
			"description": "",
			"descriptionFormat": "html",
			"time": 1493238031402,
			"version": 2,
			"responses": [],
			"tests": null,
			"currentHelper": "normal",
			"helperAttributes": {}
		},
		{
			"id": "76af8e1e-b27e-69e5-56b9-ec2bcc7ed513",
			"headers": "",
			"url": "{{baseUrl}}/shelf/ark:/99999/fk4fj2qx12",
			"pathVariables": {},
			"preRequestScript": null,
			"method": "PUT",
			"collectionId": "407c8bf5-ee4a-0f2b-8073-ecc7984ba855",
			"data": null,
			"dataMode": "params",
			"name": "Add String Concatenator to Shelf",
			"description": "No error message. Adding String concatenator on shelf if not already on it.",
			"descriptionFormat": "html",
			"time": 1493237926851,
			"version": 2,
			"responses": [],
			"tests": null,
			"currentHelper": "normal",
			"helperAttributes": {}
		},
		{
			"id": "7c9487c4-366f-ae65-d1c3-d6f3c3e91012",
			"headers": "Content-Type: application/json\n",
			"url": "{{baseUrl}}/knowledgeObject/ark:/99999/fk4fj2qx12/result",
			"preRequestScript": null,
			"pathVariables": {},
			"method": "POST",
			"data": [],
			"dataMode": "raw",
			"tests": null,
			"currentHelper": "normal",
			"helperAttributes": {},
			"time": 1493238429646,
			"name": "Missing Inputs in Body",
			"description": "",
			"collectionId": "407c8bf5-ee4a-0f2b-8073-ecc7984ba855",
			"responses": [],
			"rawModeData": "{\"word\":[\"hello\",\"world\"]}"
		},
		{
			"id": "8f143d19-a69a-544a-2285-e716d5bef7f7",
			"headers": "Content-Type: application/json\n",
			"url": "{{baseUrl}}/knowledgeObject/ark:/99999/fk4fj2qx12/result",
			"pathVariables": {},
			"preRequestScript": null,
			"method": "POST",
			"collectionId": "407c8bf5-ee4a-0f2b-8073-ecc7984ba855",
			"data": [],
			"dataMode": "raw",
			"name": "No Inputs Given in Body",
			"description": "",
			"descriptionFormat": "html",
			"time": 1493238527544,
			"version": 2,
			"responses": [],
			"tests": null,
			"currentHelper": "normal",
			"helperAttributes": {},
			"rawModeData": "{}"
		},
		{
			"id": "94df6a81-fb2b-c9a6-e583-9b5e80a4defb",
			"headers": "Content-Type: application/json\n",
			"url": "{{baseUrl}}/knowledgeObject/ark:/99999/fk4fj2qx12/result",
			"pathVariables": {},
			"preRequestScript": null,
			"method": "POST",
			"collectionId": "407c8bf5-ee4a-0f2b-8073-ecc7984ba855",
			"data": [],
			"dataMode": "raw",
			"name": "Working Example",
			"description": "",
			"descriptionFormat": "html",
			"time": 1493238658440,
			"version": 2,
			"responses": [],
			"tests": null,
			"currentHelper": "normal",
			"helperAttributes": {},
			"rawModeData": "{\"words\":[\"hello\",\"world\"]}"
		},
		{
			"id": "dd6191e8-8165-bf90-eb9a-d0b870cc5d8e",
			"headers": "",
			"url": "{{baseUrl}}/shelf/ark:/99999/fk4v41133q",
			"pathVariables": {},
			"preRequestScript": null,
			"method": "PUT",
			"collectionId": "407c8bf5-ee4a-0f2b-8073-ecc7984ba855",
			"data": null,
			"dataMode": "params",
			"name": "Add Product Calculator to Shelf",
			"description": "",
			"descriptionFormat": "html",
			"time": 1493921890970,
			"version": 2,
			"responses": [],
			"tests": null,
			"currentHelper": "normal",
			"helperAttributes": {}
		}
	]
}
'''

