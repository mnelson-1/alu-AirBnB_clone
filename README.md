# The AirBnB Clone Project
![AirBnB Logo](https://www.pngitem.com/pimgs/m/132-1322125_transparent-background-airbnb-logo-hd-png-download.png)

## Project Description
This is the first part of the AirBnB clone project, where we worked on the project's backend while interfacing it with a console application with the help of the cmd module in Python.

Data (python objects) generated are stored in a JSON file and can be accessed with the help of the JSON module in python.

## Description of the command interpreter:
The application's interface is just like the Bash shell except that this has a limited number of accepted commands that were solely defined for using the AirBnB website.

This command line interpreter serves as the frontend of the web app where users can interact with the backend, which was developed with Python OOP programming.

Some of the commands available are:
- show
- create
- update
- destroy
- count

As part of the implementation of the command line interpreter coupled with the backend and file storage system, the following actions can be performed:
-   Creating new objects (ex, a new User or a New Place)
-   Retrieving an object from a file, a database, etc…
-   Doing operations on objects (count, compute stats, etc…)
-   Updating attributes of an object
-   Destroying an object

## How to start it
These instructions will get you a copy of the project up and running on your local machine (Linux distro) for development and testing.

## Installing

You will need to clone the repository of the project from Github. This will contain the simple shell program and all of its dependencies.

```
git clone https://github.com/mnelson-1/alu-AirBnB_clone.git
```
After cloning the repository, you will find a folder called alu-AirBnB_clone. In here there will be several files that allow the program to work.

> /console.py: The main executable of the project is the command interpreter.
>
> models/engine/file_storage.py: Class that serializes instances to a JSON file and deserializes JSON file to instances
> 
> models/__ init __.py:  A unique `FileStorage` instance for the application
> 
> models/base_model.py: Class that defines all common attributes/methods for other classes.
> 
> models/user.py: User class that inherits from BaseModel
> 
>models/state.py: State class that inherits from BaseModel
>
>models/city.py: City class that inherits from BaseModel
>
>models/amenity.py: Amenity class that inherits from BaseModel
>
>models/place.py: Place class that inherits from BaseModel
>
>models/review.py: Review class that inherits from BaseModel



## How to use it
It can work in two different modes:


**Interactive** and **Non-interactive**.

In **Interactive mode**, the console will display a prompt (hbnb) indicating the user can write and execute a command. After the command is run, the prompt will reappear and wait for a new command. This can go on indefinitely if the user does not exit the program.

```
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb) 
(hbnb) 
(hbnb) quit
$
```

In **Non-interactive mode**, the shell must be run with a command input piped into its execution so that the command is run as soon as the Shell starts. No prompt will appear in this mode, and no further input will be expected from the user.


```
$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$
```

## Format of Command Input

To give commands to the console, these must be piped through an echo in case of  **Non-interactive mode**.

In  **Interactive Mode**, the commands must be written with a keyboard when the prompt appears and will be recognized when an enter key is pressed (new line). As soon as this happens, the console will attempt to execute the command through several means or show an error message if the command didn't run successfully. The console can be exited in this mode using the **CTRL + D** combination,  **CTRL + C**, or the command **quit** or **EOF**.

## Arguments

Most commands have several options or arguments that can be used when executing the program. For the Shell to recognize those parameters, the user must separate everything with spaces.

Example:

```

user@ubuntu:~/AirBnB$ ./console.py
(hbnb) create BaseModel
49faff9a-6318-451f-87b6-910505c55907
user@ubuntu:~/AirBnB$ ./console.py

```

or

```
user@ubuntu:~/AirBnB$ ./console.py $ echo "create BaseModel" | ./console.py
(hbnb)
e37ebcd3-f8e1-4c1f-8095-7a019070b1fa
(hbnb)
user@ubuntu:~/AirBnB$ ./console.py
```

## Available commands and what they do

The recognizable commands by the interpreter are the following:

|Command| Description |
|--|--|
| **quit or EOF** | Exits the program |
| **Usage** | By itself |
| **-----** | **-----** |
| **help** | Provides a text describing a command's use.  |
| **Usage** | By itself --or-- **help <command\>** |
| **-----** | **-----** |
| **create** | Creates a new instance of a valid `Class`, saves it (to the JSON file) and prints the `id`.  Valid classes are BaseModel, User, State, City, Amenity, Place, and Review. |
| **Usage** | **create <class name\>**|
| **-----** | **-----** |
| **show** | Prints the string representation of an instance based on the class name and `id`  |
| **Usage** | **show <class name\> <id\>** --or-- **<class name\>.show(<id\>)**|
| **-----** | **-----** |
| **destroy** | Deletes an instance based on the class name and `id` (saves the change into a JSON file).  |
| **Usage** | **destroy <class name\> <id\>** --or-- **<class name>.destroy(<id>)** |
| **-----** | **-----** |
| **all** | Prints all string representations of all instances based or not on the class name.  |
| **Usage** | By itself or **all <class name\>** --or-- **<class name\>.all()** |
| **-----** | **-----** |
| **update** | Updates an instance based on the class name and `id` by adding or updating an attribute (saves the changes into a JSON file).  |
| **Usage** | **update <class name\> <id\> <attribute name\> "<attribute value\>"** ---or--- **<class name\>.update(<id\>, <attribute name\>, <attribute value\>)** --or-- **<class name\>.update(<id\>, <dictionary representation\>)**|
| **-----** | **-----** |
| **count** | Retrieve the number of instances of a class.  |
| **Usage** | **<class name\>.count()** |

## Authors
Marvelous Nelson <m.nelson@alustudent.com>
