# Activator Manual

A knowledge object has not reached its full potential until it is able to be executed, particularly against applicable data, such as data collected from electronic health records \(EHR\). If you have questions about how KO are created or managed, reference the [Authoring & Managing Knowledge Objects Manual](http://kgrid.org/AuthoringManual).

An activator allows knowledge objects to be executable against collected data. The basic steps to execute a knowledge object include \(1\) Add Knowledge Object to Shelf, and \(2\) Execute Knowledge Object Against Data. There are two ways to utilize the activator: \(1\) Load to the Activator \(pull from library\), and \(2\) Download Payload and Direct Upload.

After a public knowledge object has been added to the Knowledge Grid Library, other users can "checkout" that object by pulling from the library. To "checkout" means to add the knowledge object information to the "shelf". Here we refer to the shelf as a particular user's stack of knowledge objects they would like to execute. Once the knowledge object is added to the shelf, they can be executed with the data through the REST API. Downloading the payload and directly uploading works similar except the activator directly recieves the information versus making a call to the library.

This manual includes information on the process of executing a knowledge object, from adding the knowledge objects to the shelf, to executing the KO with your collected data. Throughout all documentation, knowledge objects will simply be refereed to as KO.

In the "Getting Started" section, we will walk through a basic example of using the execution stack.

This documentation is being maintained on git book. The git book documentation can be accessed at: [https://www.gitbook.com/book/kgrid/execution-manual](https://www.gitbook.com/book/kgrid/execution-manual/).

Additional questions beyond the information given can be directed to: dlhs.knowledge.grid@umich.edu.

Copyright © University of Michigan, Department of Learning Health Sciences.

