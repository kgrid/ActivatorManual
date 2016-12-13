# Getting Started

### Basic Steps

1. Find the knowledge objects ArkID. The ArkID can be found on ObjectTeller.

2. Using REST API commands, add knowledge object to shelf.

   ```
   PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/ark:/ArkID
   ```

3. Check the shelf to make sure the knowledge object ArkID was properly added. If your ArkID of interest is not on the shelf, double check you have the correct ArkID and re-do step 2.

   ```
   GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/
   ```

4. Add body \(input parameters\) and tests \(optional\). Execute the  knowledge object.

   ```
   POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/ark:/ArkID/result
   ```


### Example

Now, let's try using an actual knowledge object: [Total Prescriptions](http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ObjectTeller/object/ark:/99999/fk4rf60z9w). The knowledge object takes in a list of Drug IDs \(RxCUIs\) and outputs the total number of prescriptions with in that list.

Find the knowledge objects ArkID from the ObjectTeller Library: [http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ObjectTeller/object/ark:/99999/fk4rf60z9w. ](http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ObjectTeller/object/ark:/99999/fk4rf60z9w)

The Object ID for this KO is: **ark:/99999/fk4rf60z9w**

Using REST API commands, add knowledge object to shelf.

Open your REST API client and run the ADD/UPDATE command.

       `PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/Shelf/ark:/99999/fk4rf60z9w`

Check the shelf to make sure the knowledge object was properly added.  
1. \`\`\`  
   PUT [http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf](http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf)

```
If the ArkID is not on the shelf, double check you have the correct Object ID and re-do step 2.
       The output should look something like this: ![](/assets/Screen Shot 2016-12-13 at 12.34.43 PM.png)

Add body \(input parameters\). Execute the knowledge object.

Let's add a basic body that was included in the test function within the Total Prescriptions script.

    body = {"DrugIDs":"101 204 708 406 190"}
```

```
POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/ark:/99999/fk4rf60z9w/result
```

The output should be 5.



