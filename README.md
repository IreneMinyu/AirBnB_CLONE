## ![Logo](https://i.pinimg.com/originals/3c/bf/be/3cbfbe148597341fa56f2f87ade90956.png)

# AirBNB Clone Description

## Documentation

This team project is part of the ALX School Full-Stack Software Engineer program. It's the first step towards building a first full web application: an AirBnB clone. This first step consists of a custom command-line interface for data management, and the base classes for the storage of this data.

- A command interpreter to manipulate data without a visual interface, like in a Shell (perfect for development and debugging)
- A website (the front-end) that shows the final product to everybody: static and dynamic
- A database or files that store data (data = objects)
- An API that provides a communication interface between the front-end and your data (retrieve, create, delete, update them)

---

    Development Framework

## ![Logo](https://camo.githubusercontent.com/0d7a5070dc4c0e87164d7766f63ba5e061db61a0e2c7afe33933219387407652/68747470733a2f2f692e696d6775722e636f6d2f39576b4d396e6e2e706e67)

    Data Diagram

## ![Logo](https://camo.githubusercontent.com/4ece18420517a1209258579d7812ba3818867b218a925fa642be96dfd1fe7d22/68747470733a2f2f692e696d6775722e636f6d2f49375655524e522e6a7067)

# Usage

The console works both in interactive mode and non-interactive mode, much like a Unix shell. It prints a prompt and waits for the user for input. The application is composed of:

- A command interpreter to manipulate data without a visual interface, like in a Shell (perfect
  fordevelopment and debugging).

- A website (the front-end) that shows the
  final productto everybody - static and dynamic

- A database or files that store data (data = objects)

- An API that provides a communication interface between
  the front-end and your data (retrieve, create, delete, update them)

## Command Line interpreter

This is the first step towards building the first full web application: the AirBnB clone. This first step is very important because we will use what we build during this project with all other following projects: HTML/CSS templating, database storage, API, front-end integration

## Definition of a Command Line interpreter

Do you remember the Shell? It’s exactly the same but limited to a specific use-case. In our case, we want to be able to manage the objects of our project:

- Create a new object (ex: a new User or a new Place)
- Retrieve an object from a file, a database etc…
- Do operations on objects (count, compute stats, etc…)
- Update attributes of an object
- Destroy an object

## Learning Objectives

- How to create a Python package
- How to create a command interpreter in Python using the cmd module
- What is Unit testing and how to implement it in a large project
- How to serialize and deserialize a Class
- How to write and read a JSON file
- How to manage datetime
- What is an UUID
- What is \*args and how to use it
- What is \*\*kwargs and how to use it
- How to handle named arguments in a function

## File Structure

| Type       | Description                                                                                                                                                                                                                                                          |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| console.py | command interpreter to manage your AirBnB objects: Create a new object (ex: a new User or a new Place) ; Retrieve an; object from a file, a database etc… ; Do operations on objects (count, compute stats, etc…); Update attributes of an object; Destroy an object |
| models     | directory of all the classe                                                                                                                                                                                                                                          |
| tests      | directory of console test and class tests                                                                                                                                                                                                                            |

---

## Console

| Commands   | Description                                                                                                                                                                                                                     |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| quit       | Exit the program                                                                                                                                                                                                                |
| EOF        | Exit the program                                                                                                                                                                                                                |
| empty line | Do nothing                                                                                                                                                                                                                      |
| create     | create a class instance                                                                                                                                                                                                         |
| show       | Prints the string representation of an instance based on the class name and id                                                                                                                                                  |
| destroy    | Deletes an instance based on the class name and id (save the change into the JSON file)                                                                                                                                         |
| all        | Prints all string representation of all instances based or not on the class name                                                                                                                                                |
| update     | Updates an instance based on the class name and id by adding or updating attribute (save the change into the JSON file). If there are more commands, the command interpreter will only count the first attribute with its value |
| count      | Retrieve the number of instances of a class                                                                                                                                                                                     |

## Model file Structure

| File         | Descripton                          | Recommendations                                                                                                                                                   |
| ------------ | ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| engine       | directory of Store first object     | The first way you will see here is to save these objects to a file with dictionaries:` <class 'BaseModel'> -> to_dict() -> <class 'dict'> -> <class 'BaseModel'>` |
| init.py      | initialization code for the package | files are required to make Python treat the directories as containing packages; this is done to prevent directories with a common name                            |
| amenity.py   | Amenity class                       | Inherits from BaseModel and contains specific public attributes                                                                                                   |
| basemodel.py | Base Model class                    | Defines all common attributes/methods for other classes sach as id, datetime                                                                                      |
| city.py      | City class                          | Inherits from BaseModel and contains specific public attributes                                                                                                   |
| place.py     | Place class                         | Inherits from BaseModel and contains specific public attributes                                                                                                   |
| state.py     | State class                         | Inherits from BaseModel and contains specific public attributes                                                                                                   |
| user.py      | User class                          | Inherits from BaseModel and contains specific public attributes                                                                                                   |

## Engine Structure

Every time that the program is launched, we will save these objects to a file: In this project, we converted the dictionary representation to a JSON string. JSON is a standard representation of a data structure. With this format, humans can read and all programming languages have a JSON reader and writer.

The flow of serialization-deserialization is:

`<class 'BaseModel'> -> to_dict() -> <class 'dict'> -> JSON dump -> <class 'str'> -> FILE -> <class 'str'> -> JSON load -> <class 'dict'> -> <class 'BaseModel'> `

| File            | Descripton                          | Recommendations                                                                                                                        |
| --------------- | ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| file_storage.py |                                     |
| init.py         | initialization code for the package | Files are required to make Python treat the directories as containing packages; this is done to prevent directories with a common name |

## Test file structure

All files, classes, and functions must be tested with unit tests

```
guillaume@ubuntu:~/AirBnB$ python3 -m unittest discover tests
...................................................................................
...................................................................................
.......................
----------------------------------------------------------------------
Ran 189 tests in 13.135s

OK
guillaume@ubuntu:~/AirBnB$
```

Unit tests should be passes in non-interactive Model

```
guillaume@ubuntu:~/AirBnB$ echo "python3 -m unittest discover tests" | bash
...................................................................................
...................................................................................
.......................
----------------------------------------------------------------------
Ran 189 tests in 13.135s

OK
guillaume@ubuntu:~/AirBnB$
```

| File            | Descripton                          | Recommendations                                                                                                                        |
| --------------- | ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| test_models     | Test of the model classes           |
| init.py         | Initialization code for the package | Files are required to make Python treat the directories as containing packages; this is done to prevent directories with a common name |
| test_console.py | Test of the console                 |

## Test_models structure

| File               | Descripton                                                                                                                                                                  |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| test_engine        | Directory where the project tests all the tests for the storage of the program                                                                                              |
| init.py            | Initialization code for the package: files are required to make Python treat the directories as containing packages; this is done to prevent directories with a common name |
| test_amenity.py    | Testing Amenity class- Expected outputs and documentation                                                                                                                   |
| test_base_model.py | Testing BaseModel- Expected outputs and documentation                                                                                                                       |
| test_city.py       | Testing City Class - Expected outputs and documentation                                                                                                                     |
| test_place.py      | Testing Place Class- Expected outputs and documentation                                                                                                                     |
| test_review.py     | Testing Review Class - Expected outputs and documentation                                                                                                                   |
| test_state.py      | Testing State Class - Expected outputs and documentation                                                                                                                    |
| test_user.py       | Testing User Claass- Expected outputs and documentation                                                                                                                     |

## Authors

- [@Stephen Muchendu Maina](https://www.github.com/muchendumaina)

- [@Wangari Minyu](https://www.github.com/IreneMinyu)
