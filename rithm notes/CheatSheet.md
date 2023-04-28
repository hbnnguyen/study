
## dir()
- shows methods and attributes if the object
- q to quit

## help()
- shows methods and attributes + their descriptions of the object
- q to quit

## common exception types
AttributeError
	-  Couldn’t find attr: `o.missing`
KeyError
	-   Couldn’t find key: `d["missing"]`
IndexError
	- Couldn’t find index: `lst[99]`
NameError
	- Couldn’t find variable: `not_spelled_right`
OSError
	- Operating system error: can’t read/write file, etc
ValueError
	- Incorrect value (tried to convert “hello” to int, etc)

## Using Pip to install a new package:


```
$ pip3 install forex_python
#... pip output here...

$ ipython
In [1]: from forex_python.converter import convert
In [2]: convert("USD", "GBP", 10)
7.6543
```

### Creating a Virtual Environment
```
cd my-project-directory
$python3 -m venv venv
```

### Using Your Virtual Environment
```
$ source venv/bin/activate
(venv) $  # <-- notice shell prompt!
```
- use pip3 install in the venv

## Tracking Required Libraries

To see a list of installed libraries in a venv:
```
$ pip3 freeze
# ... list of installed things...
```
It’s helpful to save this info in a file (typically named “requirements.txt”):
```
$ pip3 freeze > requirements.txt
```
## Recreating a Virtual Environment

When using a new Python project:
```
$ git clone http://path-to-project
$ cd that-project
$ python3 -m venv venv
```

Then, as usual when working with a venv:
```
$ source venv/bin/activate
(venv) $ pip3 install -r requirements.txt
# ... pip output here ...
```

## Leaving Virtual Environments

Use the deactivate shell command to leave the virtual environment:
```
$ source venv/bin/activate
(venv) $ deactivate
$ # ... back to regular terminal ...
```
