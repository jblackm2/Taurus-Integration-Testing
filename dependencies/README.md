**Taurus integration testing that I developed an internship, for use with web-based APIs. The actual URLs that were used for the testing have been redacted.**

Background:
This repository is an attempt to write useful automated testing for ServiceEdge APIs.
There are several scenarios that I am attempting to link together.
The basic idea is to create a new customer, have that customer get a new vehicle, and create an appointment for that vehicle.

How:
The YAML files to perform these actions are in the run/dependencies folder.
They are the newCustomer.yml, newVehicle.yml, and newAppointment.yml files.
The data folder contains JSON objects that will be passed in the POST messages for these first three files. They are not fully implemented yet.
The other files should use data extracted from these first three files, and each other, to perform their tests.

Main.yml is the file that describes how the execution of the "run" scenario will be performed.
It may be better to break this scenario up into several different ones; for example:

create a new customer, get the customer name, phone #, email, etc, use this data to perform a customer search and test that it returns the correct values.
This could be one scenario, and then a separate scenario could use a newAppointment to check to make sure that the appointment is returning the correct vehicle Id, make, model, etc.

Running:
The batch file run.All.cmd controls which files are to be linked at run time.
To run the scenario as is, just type "run.All.cmd", on the command line. This will run Taurus and fire up Blazemeter to show the results of the tests.
To stop some tests from running, simply remove the corresponding .yml file from the batch file.

How to get Taurus:
http://gettaurus.org/docs/Installation/

Taurus Manual:
http://gettaurus.org/docs/Index/

A helpful tutorial on Taurus:
https://cdinsight.wordpress.com/2015/10/21/try-taurus-for-narrative-readable-and-maintainable-loadperformance-tests/

