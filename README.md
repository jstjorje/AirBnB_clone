# The AirBnB Clone Project
![AirBnB Logo](https://www.pngitem.com/pimgs/m/132-1322125_transparent-background-airbnb-logo-hd-png-download.png)

# AirBnB Clone - The Console

Welcome to the AirBnB clone project! This project is part of the Holberton School curriculum. It focuses on creating a basic clone of the AirBnB website. This initial phase involves creating a command-line interpreter to manage the backend of the application.

## Table of Contents

- [Description](#description)
- [Command Interpreter](#command-interpreter)
- [How to Start](#how-to-start)
- [How to Use](#how-to-use)
- [Examples](#examples)
- [Project Structure](#project-structure)
- [Testing](#testing)
- [Contributing](#contributing)
- [Authors](#authors)

## Project Description
## Description of the command interpreter:
This project is a simplified version of the AirBnB website. It includes a custom command-line interface (CLI) that allows users to create, update, delete, and retrieve instances of the application's models. The project focuses on understanding and implementing the following concepts:

- Python packages and modules
- Object-oriented programming
- File handling and serialization
- Unit testing
- Command-line interface design
Some of the commands available are:
- show
- create
- update
- destroy
- count

And as part of the implementation of the command line interpreter coupled with the backend and file storage system, the folowing actions can be performed:
-   Creating new objects (ex: a new User or a new Place)
-   Retrieving an object from a file, a database etc…
-   Doing operations on objects (count, compute stats, etc…)
-   Updating attributes of an object
-   Destroying an object

## How to start it
## Command Interpreter

### How to Clone the Repository

To get started, you need to clone the repository to your local machine. Use the following commands:

```sh
git clone https://github.com/jstjorje/AirBnB_clone/AirBnB_clone.git
cd AirBnB_clone
```
To start the command interpreter, navigate to the project directory and run: ./console.py
Ensure that the script has execute permissions. If not, you can add them using: chmod +x console.py
In here there will be several files that allow the program to work.

> /console.py : The main executable of the project, the command interpreter.
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
Once the command interpreter is running, you can use the following commands to interact with the application:

quit: Exits the program
EOF: Exits the program (end-of-file)
create <class>: Creates a new instance of a class and prints its id
show <class> <id>: Prints the string representation of an instance based on class name and id
destroy <class> <id>: Deletes an instance based on class name and id
all [<class>]: Prints all string representations of all instances, optionally filtered by class name
OBOBOBupdate <class> <id> <attribute name> <attribute value>: Updates an instance based on class name and id by adding or updating an attribute
It can work in two different modes:

OBOBOB
**Interactive** and **Non-interactive**.

OBOBOBIn **Interactive mode**, the console will display a prompt (hbnb) indicating that the user can write and execute a command. After the command is run, the prompt will appear again a wait for a new command. This can go indefinitely as long as the user does not exit the program.

```
$ ./console.py
OBOBOB(hbnb) help

Documented commands (type help <topic>):
OBOBOB========================================
EOF  help  quit

(hbnb) 
(hbnb) 
(hbnb) quit
$
```

In **Non-interactive mode**, the shell will need to be run with a command input piped into its execution so that the command is run as soon as the Shell starts. In this mode no prompt will appear, and no further input will be expected from the user.


```
$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
OBOBOB(hbnb) 
$
$ cat test_help
help
OBOBOB$
$ cat test_help | ./console.py
(hbnb)

OBOBOBDocumented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$
OBOBOB```

## Format of Command Input
OBOBOB
In order to give commands to the console, these will need to be piped through an echo in case of  **Non-interactive mode**.

OBOBOBIn  **Interactive Mode**  the commands will need to be written with a keyboard when the prompt appears and will be recognized when an enter key is pressed (new line). As soon as this happens, the console will attempt to execute the command through several means or will show an error message if the command didn't run successfully. In this mode, the console can be exited using the **CTRL + D** combination,  **CTRL + C**, or the command **quit** or **EOF**.
OBOBOB
## Arguments

Most commands have several options or arguments that can be used when executing the program. In order for the Shell to recognize those parameters, the user must separate everything with spaces.

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
OBOBOBe37ebcd3-f8e1-4c1f-8095-7a019070b1fa
(hbnb)
user@ubuntu:~/AirBnB$ ./console.py
```
OBOBOB
## Available commands and what they do

The recognizable commands by the interpreter are the following:
OBOBOB
|Command| Description |
|--|--|
OBOBOB| **quit or EOF** | Exits the program |
| **Usage** | By itself |
| **-----** | **-----** |
OBOBOB| **help** | Provides a text describing how to use a command.  |
| **Usage** | By itself --or-- **help <command\>** |
| **-----** | **-----** |
OBOBOB| **create** | Creates a new instance of a valid `Class`, saves it (to the JSON file) and prints the `id`.  Valid classes are: BaseModel, User, State, City, Amenity, Place, Review. |
| **Usage** | **create <class name\>**|
| **-----** | **-----** |
OBOBOB| **show** | Prints the string representation of an instance based on the class name and `id`  |
| **Usage** | **show <class name\> <id\>** --or-- **<class name\>.show(<id\>)**|
| **-----** | **-----** |
| **destroy** | Deletes an instance based on the class name and `id` (saves the change into a JSON file).  |
| **Usage** | **destroy <class name\> <id\>** --or-- **<class name>.destroy(<id>)** |
| **-----** | **-----** |
| **all** | Prints all string representation of all instances based or not on the class name.  |
| **Usage** | By itself or **all <class name\>** --or-- **<class name\>.all()** |
| **-----** | **-----** |
| **update** | Updates an instance based on the class name and `id` by adding or updating attribute (saves the changes into a JSON file).  |
| **Usage** | **update <class name\> <id\> <attribute name\> "<attribute value\>"** ---or--- **<class name\>.update(<id\>, <attribute name\>, <attribute value\>)** --or-- **<class name\>.update(<id\>, <dictionary representation\>)**|
| **-----** | **-----** |
| **count** | Retrieve the number of instances of a class.  |
| **Usage** | **<class name\>.count()** |

## Author

George Izu Iwuji

