# IT Jobs Watch Data

## Introduction
The aim of the project was to take a python application made in Sparta global and get my first experiance in constructing a DevOps pipeline. The first step in my project was to provision a VM on which the python appliaction could run. I initally achived this through simple shell scripting of an Ubuntu vm (using vagrant) before moving on to provsioning via chef cookbooks, this allowed me to utilise the the built in spec testing and unit testing offered by the software.

The next step for this project was to create two pipelines in Jenkins

## Software/tools used
* Python 3.x
* ChefDK
* Packer
* git/git bash
* Jenkins
* AWS

## The Chef cookbook
The necessary packages needed to run this program should automatically be picked up by pycharm. You may find a a few pop ups within the IDE that state there are dependencies missing, if you simply install these through the IDE you should be set up correctly.  

### Running tests

To test whether the program will work from your machine:

 * Ensure the `config.ini` file has the test environment set to `live`
 * Click the `Terminal` icon which can be found on the menu in the bottom left of Pycharm.
* Ensure you're in the root path of the project and type `python -m pytest tests/`

This should execute the tests if any fail you may have issues with this program.

### Running and using the program
To use the program simply right click on the `main.py` file and then click `Run 'main'`. This will run the command line user interface.

Follow the instructions to download via the various options given.

# Next steps
* Adding a job details search option (essentially be able to search for a specific role and return the details in a CSV)
* create a connected database for full deployment
* Build a scheduler as part of a full deployment to poll and add to the database
