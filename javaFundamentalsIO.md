# 1. Intro
* Java I/O organized as
	- reader writer : reader reads characters from file
	- input and output streams : input reads bytestreams from file
	Two utility classes
	- file : older. ex: File file = new File("files/data.txt");
		* more than 30 method, above code doesn't create file on disk.
		* path can relative or absolute.
	- path : nio in java7, better, can't access os specific or file system interfaces.
		* normalize() : removers redundant elements
		* relativize() : path from source to destinantion
			- path can be relative or absolute both
			- if one is relative and other is absolute then error

# 2. Reading Characters
* when reading buffer, if no of read chars is less than size of buffer that does not mean that no more chars are left to be read.
* use while loop with comparision with -1 to check if everything is read

* close the reader always
* direct closing is cumbersome
* always use try with resource : present sfter java7
	- interface must have autoClosable 

* all reader do not support reset i.e. go back to start, and no way exist to check this

* path uses factory pattern

* closing decorated reader will close it's lower reader

# 3. Writer
* abstract class : ?

## In java string is not same as array of chars, string is immutable 

* doesn't return anything
* throws exception :P

* Buffered writer extends writer, and is build on an instance of Writer

* Java 7 patterns, standardOpenOptions

* flush is necessary at end for networks and disk from memory

# 4. Bytes
* while reading a buffer, 
	int number = is.read();
	- here number is no. of byte readed, if 0 bytes are readed then -1 comes, as it returns number of bytes read-1, so 0-1 = -1
* Types
	+ disk
	+ in memory
	+ network socket

* Declarative pattern : ???
that nested reader and reader thing ?

* Compressed stream
	- Gzip : for 1 file, size limit due to OS
	- zip  : for multi files(archive)

## Code example for decorative pattern, streams, zip stream :
```java
String pathname = "files/ints.bin";
File file = new File(pathname);

try (OutputStream os = new FileOutputStream(file);) { // use ; at end of resource
	DataOutputStream dos = new DataOutputStream(os);

	dos.wrtieUTF("Hello");
} catch (IOException e) {
	e.printStackTrace();
}
```

* to write double use 10d as argument

# lambda in java :)
```java
IntStream.range(1, 100).forEach( i -> { try { dos.writeInt(i); } catch (IOExceptipon e) {} );
```

* to make it gzip
 - change extension by adding .gz
 - decorate the stream with 
        `GZIPOutputStream gzos = new GZIPOutputStream(os);`
 - make change in dataOutputStream by replacing *os* with *gzos*
 - finally move these streams to try block or *there exception would not be caught*

---
* always define streams in try 
---
