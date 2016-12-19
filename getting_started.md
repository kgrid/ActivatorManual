# Getting Started

There are two ways to utilize the execution stack: \(1\) load to the execution stack \(pull from the library\), and \(2\) download and direct upload. Direct upload may be useful when testing during development by eliminating the library steps. First, we will show how to load to the execution stack by pulling from the ObjectTeller library.

### Load to Execution Stack: Basic Steps

1. Find the knowledge objects ArkID. The ArkID can be found on ObjectTeller.

2. Using REST API commands, add knowledge object to shelf.

   ```
   PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/ark:/ArkID
   ```

3. Check the shelf to make sure the knowledge object ArkID was properly added. If your ArkID of interest is not on the shelf, double check you have the correct ArkID and re-do step 2.

   ```
   GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/
   ```

4. Add body \(input parameters\) and tests \(optional\). Execute the  knowledge object \(KO\).

   ```
   POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/ark:/ArkID/result
   ```

### Example 1:

Now, let's try using an actual knowledge object: [Total Prescriptions](http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ObjectTeller/object/ark:/99999/fk4rf60z9w). The knowledge object takes in a list of Drug IDs \(RxCUIs\) and outputs the total number of prescriptions with in that list.

1. Find the knowledge objects ArkID from the ObjectTeller Library: [http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ObjectTeller/object/ark:/99999/fk4rf60z9w. ](http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ObjectTeller/object/ark:/99999/fk4rf60z9w)The Object ID for this KO is: **ark:/99999/fk4rf60z9w**
2. Using REST API commands, add the knowledge object to the shelf. Open your REST API client and run the following ADD/UPDATE command.
   1. ```
      PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/ark:/99999/fk4rf60z9w
      ```
3. Check if the knowledge object is on the shelf. If the Ark ID is not on the shelf, double check you have the correct Ark ID and re-do step 2. 
   1. ```
      GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf
      ```
4. Now let's execute the knowledge object. Let's add a basic body that was included in the test function within the Total Prescriptions script. body = {"DrugIDs":"101 204 708 406 190"}.
   1. ```
      POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/ark:/99999/fk4rf60z9w/result
      ```

The output should be 5.

### Direct Upload to Execution Stack: Basic Steps

1. If you are downloading a payload from a KO, go to the ObjectTeller Library and find the KO of interest. Click download.
2. Go to your REST API client and use the PUT command to add the payload to the shelf. In order to add a payload to the shelf, an Ark ID must be defined. We suggest choosing a test Ark ID or one not in use to prevent confusion. 
3. Copy & Paste the payload into the body, and execute the PUT command
4. Check in the KO is on the shelf. If the Ark ID is not on the shelf, double check you have the correct ArkID and re-do step 2.
5. Add body \(input parameters\) and tests \(optional\). Execute the knowledge object \(KO\).

### Example 2:

Let's use the same KO we used in Example 1: Total Prescriptions.

1. Find the KO of interest from ObjectTeller, and download the payload.
2. Go to your REST API client and use the PUT command to add the payload to the shelf. Let's assign this KO the following ark **ID: ark:/99999/0123456789**
3. Copy & Paste or Upload the payload into the body, and execute the put command.
   1. ```
      PUT http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/ark:/99999/0123456789
      ```
4. Check if the KO is on the shelf.
   1. ```
      GET http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/shelf/
      ```
5. Add body \(input parameters\) and tests\(optional\). Execute the KO. body = {"DrugIDs":"101 204 708 406 190"}
   1. ```
      POST http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/ark:/99999/0123456789/result
      ```




