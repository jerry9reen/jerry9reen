Suppose, you want to check if a file exists on a filesystem. Typically, you can do the following:
```python
import os

# Is it a file?
os.path.isfile(filename) 
```

For any valid paths on the FS, you can do:

```python
import os

# Does it exist?
os.path.exists(path) 
```

In this case, directories, files, symlinks and any other valid existing path return True.

Object oriented way to do the same

```python
import pathlib
# For Python 2.7
# import pathlib2

a_path = my_file = Path("/path/to/something")
a_path.is_file() # returns True if the path is a file
a_path.is_dir() # returns True if the path is a directory
a_path.exists() # returns True if the path actually exists
```

Note, if you plan to `if a_path.exists():` and then `open('path/to/file')`, consider to use `try except` approach. The reason is that file might be deleted between the calls.

```python
try:
    f = open('path/to/file')
except FileNotFoundError as e:
    # Handle exception here
    pass
```

