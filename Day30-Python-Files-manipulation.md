Python has several functions for creating, reading, updating, and deleting files.

**File Handling**
The key function for working with files in Python is the open() function.

The **open()** function takes two parameters; filename, and mode.

There are four different methods (modes) for opening a file:

"r" - Read - Default value. Opens a file for reading, error if the file does not exist

"a" - Append - Opens a file for appending, creates the file if it does not exist

"w" - Write - Opens a file for writing, creates the file if it does not exist

"x" - Create - Creates the specified file, returns an error if the file exists

In addition you can specify if the file should be handled as binary or text mode

"t" - Text - Default value. Text mode

"b" - Binary - Binary mode (e.g. images)

========================================================================================================================

**Syntax**
1. To open a file for reading it is enough to specify the name of the file:

f = open("demofile.txt")

To open the file, use the built-in **open() ** function.

The **open()** function returns a file object, which has a read() method for reading the content of the file:

**Example**

f = open("demofile.txt")
print(f.read())


**Example 2**
Open a file on a different location:

f = open("D:\\myfiles\welcome.txt")
print(f.read())

You can also use the **with** statement when opening a file:

with open("demofile.txt") as f:
  print(f.read())

  Then you do not have to worry about closing your files, the with statement takes care of that.

If you are not using the with statement, you must write a close statement in order to close the file:

f = open("demofile.txt")
print(f.readline())
f.close()

=======================================================================================================

By default the **read()** method returns the whole text, but you can also specify how many characters you want to return:

with open("demofile.txt") as f:
  print(f.read(5))

===================================================================================================

You can return one line by using the **readline()** method:

with open("demofile.txt") as f:
  print(f.readline())

===================================================================================================

By looping through the lines of the file, you can read the whole file, line by line:

with open("demofile.txt") as f:
  for x in f:
    print(x)
================================================================================================

**Write to an Existing File**
To write to an existing file, you must add a parameter to the open() function:

"a" - Append - will append to the end of the file

"w" - Write - will overwrite any existing content

with open("demofile.txt", "a") as f:
  f.write("Now the file has more content!")

#open and read the file after the appending:
with open("demofile.txt") as f:
  print(f.read())

=====================================================================================================

To overwrite the existing content to the file, use the w parameter:

with open("demofile.txt", "w") as f:
  f.write("Woops! I have deleted the content!")

#open and read the file after the overwriting:
with open("demofile.txt") as f:
  print(f.read())

=========================================================================================================

Create a New File
To create a new file in Python, use the open() method, with one of the following parameters:

"x" - Create - will create a file, returns an error if the file exists

"a" - Append - will create a file if the specified file does not exists

"w" - Write - will create a file if the specified file does not exists


f = open("myfile.txt", "x")

===========================================================================================================

**Delete a File**
To delete a file, you must import the OS module, and run its os.remove() function:

import os
os.remove("demofile.txt")

Check if File exist:

import os
if os.path.exists("demofile.txt"):
  os.remove("demofile.txt")
else:
  print("The file does not exist")

To delete an entire folder, use the os.rmdir() method:

import os
os.rmdir("myfolder")
