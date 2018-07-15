# 3. I/O with streams
* Streams : Ordered sequence of data, unidirectional
* bytestream and text stream : bits and unicode(32 bits)
  - piped : reader-writer (chaining of stream)

## Stream realities
* cleanup : automatic
  - not reliable as
    * streams are backed by physical storages existing outside java runtime
  - reliable cleanup
    * closeable interface : at end, very verbose
    * autocloseable interface 
      - try-with-resources : best way to go
      	* automate resource cleanup for resources implementing AutoCloseable
        * in try () call, add the resources within braces
* error handling :
  - java gives only first exception, rest are suppressed.
  - loop through e.getSuppressed() to print them

## Chaining stream
  - Close higher stream and lower stream gets closed

# File and Buffered Streams
## Buffered Steams
* direct file access is inefficient, buffer content in memory
 - perform read/writes in large chunks, reduces underlying stream interactions
* understand usage of \n or \r\n depending on OS.

## Accessing Files with the java.nio.file Package
* preferred goto, newer and better
* beneficials over java.io (deprecated now)
	- better exception reporting
	- scalability
	- better support for new file systems

* Path and Paths types
	- works only for default file system
	- Paths is factory for Path instances
* Files Type


## File System Types
* URIs = Univeral resource identifier
* Path types works with default normal file system
* zip file system for example can't be used directly, need to mention properties of that file system
* URI of zip is jar:file

* Methods to create/open file system

# 4. Mod : String formating and regex

## String Joiner
* chaining of joins
* different start and ending strings
* Edge cases : it takes care of them
	- handling single string
	- when no string added (empty case)
* can customize empty case
	- when add method is never called, not "" (no string)

## Format specifiers
* String.format : use %d, %.1f etc like C
* Other methods also exist Formatter.format (writes contents to any type that implements Appendable interface)
	- String.format use this underhood

## %[arg ind] [flags] [width] [precision] conversion 

* Format flag 
	1. /# : radix : base for number
	2. 0 and - : leading zero and left padding 

## REGEX
* method
	- replaceAll 
	- split
	- matches
* //b for /b, / is escape character in Java like python

## regex are processing intensive
## Pattern class : compile for faster processing

---
# 5. Collections
Collections are more powerful than arrays
They hold Object types
	1. iterable
	2. type safety
	3. dynamic
	4. special properties unique to each collection

#### Java8 collection methods
Lambda expression :
	+ forEach 
	+ removeIf

# 6. Controlling App Execution and Environment
## command line argument
String [] args in main 
for file with space in name use quotes to open that in IDE's box  eg: "file 1.txt"

## Properties Persisted as Simple Text
* name with .properties suffix

One key/value pair written per line
* key/value seperated by = or :
* whitespace surrounding =,: are ignored
* whitespace act as seperator if = or : is not present
* to escape whitespace, =, : by \
* comment with # or !


## XML
* .xml suffix
* date and time not added automatically
* key/value pair are used
* all lie under <property> field
* comments are made using <comment> field

## default values

## class path
* java searches in current directory

* to have java search at other paths
+ Environment variable : don't use it, as it's global variable
* set CLASSPATH=\setToReqDir
+ java command option
* java -cp /pathToDir com.saurav.pathOfClass
* use : for unix and ; for windows

## using jar option
* to lock the directory : tighter control

## Execution Environment Info
Ways :
* system properties
 + accessed by System.getProperties
 + user data, OS data
* environment vars
 + app-specific vars
 + System.getenv(), returns Map<String, String>

# Log System
* Only one app-wide log manager : 1 global instance
* create only one global logger at top of Main class
* Log levels
    + 7 levels : 
    + select a threshold level, all the levels below it will ignored in log

## types of Log methods
* simple
* level convenience
* precise : print the class, calling class as mentioned
* precise convenience : above finner level 
* parameterized 
  + to print list, vars

## log component
* logger
* handler
* formatter


---
# 8. Concurrency and Multi threading
Thread class : Low level, everything is user defined
Runnable interface : everything is user defined

## BETTER alternatives
ExecutorService 
	+ abstract thread management details
	+ thread pools
Callable interface 
Future interface

Dealing with synchronization
+ synchronized method : significant overhead
    - protect modification by multiple threads
    - reading value that might be modified by another thread

All Java objects have a lock, synchronization uses lock on variables.

+ synchronized statement blocks
    * flexibility in non thread safe classes
    * sometime needed to get work done

## java.util.concurrent
+ semaphore
+ java.util.concurrent.atomic : eg - getAndAdd is single atomic operation
----
	
# 9. Run time Information
## Reflection
* examination of types at runtime
* dynamically execute & access members

Needed for 
* no type specific source code
* type not known at compile time
* accessing them
Used in :
* ide for figuring out class type of a object

## Type as type
Class class : boxes for 
* name
* fields
* constructors
* methods
It defines how a class is modeled, consider video again

## Accessing a Type's Class Instance
* from Type Reference
 - call getClass method
 - use "?" as no info for class type is available in class ...
* from String name or type literal
 - string name : Class <?> c = Class.forName("com.jwh.fin.Bank");
 - literal : Class <?> c = Bank.class;

* all are referring to equivalent class instance

## Type Access Information
* interface
* modifiers 
 + has getModifiers method
 + returns int, use bit and/or to get value

## Interacting with Object Instances
* can access and invoke members
 - start with getting class
 - get methods of class, and use that method
* reflection is slower than direct invocation of class method, no optimization occurs

---
# 10. Adding Type Metadata with annotations
* to express the intent :
 - comment
 - documentation
* above are not adequate, so use annotation

## Ex: @Override to override a class definition

---
# 11. Persistent Object
* store objects as byte streams, 
 - to file system
 -  to save database, on RDBMS or Object based databases
 - pass the object over network

* Serialization : object -> bytestream
* deserialization : bytestream -> object 

* Being Serializable : implements serializable
 - if all types are serializable, then object is serializable.
 - string is also
 - primitive type are already serializable

## Class version incompatibility
* after making changes to class definition, the hash values changes that results in incompatibility.

* To make compatible
 - use serialver
 - add extra field that is private, static, final, long
 - calculate the value for class with it's complete name
 - assign it.
ex : private static final long serialVersionUID = itsFukingVal

## customizing serialization
* if some new field is added later on, it's default value will be used if called after serialization and before it when load a saved instance.
* this is not desired as we clearly want to seperate instances with no values and value which was saved when class was in earlier state.

## Transient fields
* transient fields are not serialized.
* used for fields that can be calculated from other values.
* only deserialization part needs to be changed, so make a custom function for it.


----
---x------x------x------x------x------x---



