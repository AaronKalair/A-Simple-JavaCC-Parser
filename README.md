About
=====

This is a simple parser that recognises a 'toy' language consisting of places and how they are related.


For example it would recognise:

* I see the cat and the dog.

* The dog is north of the cat.


It would also recognise:

* I see the cat, the dog.

* The dog is 5m north of the cat.


As well as ensuring the language meets the input specification it checks that it is semantically valid for example:

* I see the cat, the dog, the sheep.

* The dog is north of the cat.

* The cat is north of the dog.

Can obviously not be true so it would throw an error.


The file "examples.txt" shows some more examples of valid input.



Compiling and Using the Application
===================================

To compile the application you must first have JavaCC (http://javacc.java.net/) present on your computer and in your path.

Then execute the compile script, this will generate all of the nessecary files.

Finally to use the application pass it input via the standard input stream.

For example:

java Parser < examples.txt


Notes
=====
* All lines must either end with a "." or ";"
* A place can only be declared once.
* Lists can be seperated by either "and" or "," but not both.
* Specifing a distance is optional.
* Valid directions are "north of", "south of", "east of" and "west of".
* The language is case insensitive.
* Square brackets can be used to input places with names matching keywords. E.g. [north pole]
* Location declarations must start with "I see the"
* Locations be must delcared before they are used in a relation declaration.
* Lists must be followed by "are" not "is", in relation declarations.
* Valid distance units are "m", "km" and "miles"
