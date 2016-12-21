# Getting Started

There are two ways to utilize the execution stack: \(1\) Load to the Execution Stack \(pull from the library\), and \(2\) Download and Direct Upload. Direct upload may be useful when testing during development by eliminating the library steps. First, we will show how to load to the execution stack by pulling from the ObjectTeller library.

### Load to Execution Stack: Basic Steps

1. Find the knowledge objects \(KO\) ArkID. The ArkID can be found on ObjectTeller.

2. Using REST API commands, add KO to shelf. Execute the PUT command.

   ```
   PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/ark:/ArkID
   
   ```
   
3. Check the shelf to make sure the KO ArkID was properly added. If your ArkID of interest is not on the shelf, double check you have the correct ArkID and re-do step 2.

   ```
   GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/
   ```

4. Add body \(input parameters\) and tests \(optional\). The following header must be used when execute KO. Copy & Paste the header into your REST API client and execute the POST command.

   ```
   Accept:application/json
   Content-Type:application/json
   ```
   
   ```
   POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/ark:/ArkID/result
   ```




### Example 1:

Now, let's try using an actual knowledge object: Total Prescriptions.



1. Find KO Ark Id from the Object Teller Library.

2. Using REST API commands, add the KO the shelf. Open your REST API client, and run the following ADD/UPDATE command. 

   ```
   PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/ark:/99999/fk4rf60z9w
   
   ```


3. Check if the KO is on the shelf. If the Ark ID is not on the shelf, double check you have the correct Ark ID and re-do step 2.  

   ```
   GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf
   
   ```

4. Now let's execute the KO. Let's add a basic body that was included in the test function within the Total Prescriptions script. Copy & Paste the header and execute the command.
body = {"DrugIDs":"101 204 708 406 190"}.  
   
   ```
   Accept:application/json
   Content-Type:application/json
   
   ```
   
   ```
   POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/ark:/99999/fk4rf60z9w/result
   
   ```
   

The output should be 5.

### Direct Upload to Execution Stack: Basic Steps

1. If you are downloading a payload from a KO, go to the ObjectTeller Library and find the KO of interest. Click download.
2. Go to your REST API client and use the PUT command to add the payload to the shelf. In order to add a payload to the shelf, an Ark ID must be defined. We suggest choosing a test Ark ID or one not in use to prevent confusion. 
3. Copy & Paste the payload into the body, add the required header, and execute the PUT command
4. Check in the KO is on the shelf. If the Ark ID is not on the shelf, double check you have the correct ArkID and re-do step 2.
5. Add body \(input parameters\) and tests \(optional\). Execute the KO.

### Example 2:

Let's use the same KO we used in Example 1: Total Prescriptions.

1. Find the Total Prescriptions KO of from ObjectTeller, and download the payload, or copy & paste the payload below.

   ```
         {
           "metadata": {
             "title": "Total Prescriptions",
             "owner": "",
             "description": "Example of creating a KO for Authoring Manual",
             "contributors": "Ian Informatician",
             "keywords": "",
             "published": false,
             "lastModified": 1479790800000,
             "createdOn": 1479186000000,
             "objectType": null,
             "citations": [],
             "license": {
               "licenseName": "",
               "licenseLink": "null"
             }
           },
           "inputMessage": "<rdf:RDF xmlns:ot=\"http://uofm.org/objectteller/#\"\n xmlns:rdf=\"http://www.w3.org/1999/02/22-rdf-syntax-ns#\">\n  <rdf:Description rdf:about=\"http://uofm.org/objectteller/inputMessage\">\n    <ot:noofparams>1</ot:noofparams>\n    <ot:params>\n      <rdf:Seq>\n        <rdf:li>rxcuisIn</rdf:li>\n      </rdf:Seq>\n    </ot:params>\n  </rdf:Description>\n  <rdf:Description rdf:about=\"http://uofm.org/objectteller/param/\">\n    <ot:datatype>STRING</ot:datatype>\n  </rdf:Description>\n</rdf:RDF>\n",
           "outputMessage": "<rdf:RDF xmlns:ot=\"http://uofm.org/objectteller/\"\n  xmlns:rdf=\"http://www.w3.org/1999/02/22-rdf-syntax-ns#\">\n  <rdf:Description rdf:about=\"http://uofm.org/objectteller/outputMessage\">\n    <ot:returntype>INT</ot:returntype>\n  </rdf:Description>\n</rdf:RDF>\n",
           "payload": {
             "content": "def TotalPrescriptions(DrugIDDict):\n    rxcuistring = DrugIDDict.get(\"DrugIDs\")\n    rxcuis=rxcuistring.split()\n    return (len(rxcuis))\n\ndef test():\n    if TotalPrescriptions({\"DrugIDs\":\"\"}) == 0:\n        print (\"ok.\")\n    else:\n        print (\"error.\")\n    if TotalPrescriptions({\"DrugIDs\":\"101 204 708 406 190\"}) == 5:\n        print (\"ok.\")\n    else:\n        print (\"error.\")\n    if TotalPrescriptions({\"DrugIDs\":\"101 204 708\"}) == 3:\n        print (\"ok.\")\n    else:\n        print (\"error.\")\n    if TotalPrescriptions({\"DrugIDs\":\"192\"}) == 1:\n        print (\"ok.\")\n    else:\n        print (\"error.\")\n    if TotalPrescriptions({\"DrugIDs\":\"192 108 458 378 142 155 246\"}) == 7:\n        print (\"ok.\")\n    else:\n        print (\"error.\")\n    if TotalPrescriptions({\"DrugIDs\":\"192 108 458 378 142 155 246 123 423\"}) == 9:\n        print (\"ok.\")\n    else:\n        print (\"error.\")\n",
             "functionName": "TotalPrescriptions()",
             "engineType": "Python"
           },
           "logData": "99999-fk4rf60z9w wasGeneratedBy http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/fcrepo/rest/99999-fk4rf60z9w/Log/CreateActivity \n 99999-fk4rf60z9w isA http://www.w3.org/ns/prov#Entity \n 99999-fk4rf60z9w wasAttributedTo Ian Informatician \n 99999-fk4rf60z9w/Log/CreateActivity isA http://www.w3.org/ns/prov#Activity \n 99999-fk4rf60z9w/Log/CreateActivity startedAtTime Tue Nov 15 10:29:25 EST 2016 \n 99999-fk4rf60z9w/Log/CreateActivity Used http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/fcrepo/rest/99999-fk4rf60z9w \n 99999-fk4rf60z9w/Log/CreateActivity wasAssociatedWith Ian Informatician \n 99999-fk4rf60z9w/Log/CreateActivity endedAtTime Tue Nov 15 10:29:25 EST 2016 \n ",
           "uri": "ark:/99999/fk4rf60z9w"
         }
   ```

2. Go to your REST API client and use the PUT command to add the payload to the shelf. Let's assign this KO the following ark ID:** ark:/99999/0123456789**. 

3. Copy & Paste or Upload the payload into the body. To add the payload, click "body", "raw", and then use the drop down box to change "text" to select "JSON \(application/json\)". Paste the JSON formatted payload into the body, and execute the PUT command.
   
   ```
   PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/ark:/99999/0123456789

   ``` 
   
4. Check if the KO is on the shelf by looking for the ark ID.

   ```
   GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/
   
   ```

5. Using the POST command, add body \(input parameters\) and tests\(optional\). Copy & Paste the header and execute the KO.
   body = {"DrugIDs":"101 204 708 406 190"}

   ```
   Accept:application/json
   Content-Type:application/json
   ```
   
   ```
   POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/ark:/99999/0123456789/result
   
   ```
   
The output should be 5.




