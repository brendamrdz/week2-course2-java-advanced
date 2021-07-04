# week2-course2-java-advanced

| Inheritance                                                                                                                                  | Interfaces                                           | Abstract                                                       |
|----------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|----------------------------------------------------------------|
| Classes may not need to inherit the implementation of a method. Sometimes we don't need to instantiate a parent class, because is so generic | Sometimes we don't need to implement all the methods | We will not implement all methods We will not create instances |

## Abstract Classes
To define an abstract class, use the keyword "abstract"
An abstract class will always be a parent class that can inherit methods, in this type of classes it is not necessary that all its methods are inherited.
To indicate the methods necessary to inherit the same word "abstract" is used. As long as you have an abstract method, the class must always be abstract.
Syntax of an abstract class and mandatory method to implement
Note: As a requirement the method must have a public access modifier. 

```bash
Public abstract class Figura {
	abstract void dibujate()
}
```

## Javadoc
Generates HTML documentation from Java code based on comments.

| //a comment             | Everything on that line will be ignored by the computer               |
|-------------------------|-----------------------------------------------------------------------|
| / * a comment block * / | Everything inside will be ignored                                     |
| /**documentation*/      | All that is inside will be a documentation comment called doc comment | 

###Comments parameters: 
```bash
How to document a class?
/ **
*[short description]
* <p>
*[long description]
*
* [author, version, params,
returns, throws, see, other tags]
* [see also]
* / 
```

### Java docs tags 
|       Tag      | Descripción                                                                                                                                                                                                                                                                          |
|:--------------:|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| @author        | Developer name.                                                                                                                                                                                                                                                            |
| @version       | Version of the method or class.                                                                                                                                                                                                                                                        |
| @param         | Definition of a method parameter, it is required for all method parameters.                                                                                                                                                                                          |
| @return        | Reports what the method returns, it cannot be used in constructors or "void" methods.                                                                                                                                                                                            |
| @throws        | Exception thrown by the method, it has a synonym of name @exception                                                                                                                                                                                                              |
| @see           | Associate with another method or class.                                                                                                                                                                                                                                                       |
| @since         | Specifies the version of the product                                                                                                                                                                                                                                                    |
| @serial        |  Describes the meaning of the field and its acceptable values. Other valid forms are @serialField and @serialData                                                                                                                                                                    |
| @deprecated    | Indicates that the method or class is old and its use is not recommended because it will possibly disappear in later versions.                                                                                                                                                     |
| @link          | Inserts an in-line link with visible text label that points to the documentation for the specified package, class or member name of a referenced class.                                                                                                                              |
| @inheritDoc    | Inherits (copies) documentation from the "nearest" inheritable class or implementable interface into the current doc comment at this tag's location.                                                                                                                                 |
| {@code view()} | Displays text in code font without interpreting the text as HTML markup or nested javadoc tags. |
| @see           | It is used when there is a multiple inheritance or when there is implementation of multiple inferfaces                                                                                                                                                                                             |
| @exception     | Exception thrown by the method, posse a synonym of name @throws                                                                                                                                                                                                                 |

Find all the labels in the official documentation [click here](https://docs.oracle.com/javase/7/docs/technotes/tools/windows/javadoc.html#code )

Advanced Classes - Nested Classes
Nested classes allow you to logically group classes that are only used in one place, thus increasing the use of encapsulation and making code easier to read and maintain.
⦁ Nested classes
⦁ Inner classes
⦁ Inner classes
⦁ Method local Inner classes
⦁ Anonymous Inner classes
⦁ Static Nested classes

```bash
Class ClassExterior {
  static class StaticNestedClass {
  }
  class InternalClass {
  }
} 

```
## Static Nested Classes 
As with class variables and methods, a static nested class is associated with its outer class. And just like static class methods, a static nested class cannot directly reference instance variables or methods defined in its outer class - you can only use them via an object reference. They can only call static methods.
Syntax
They are accessed using the name of the attached class.

```bash
ClassExternal.ClassNestedStatic
```
Example of how to create an object for the static nested class:
```bash
OuterClass.NestedClassStaticNestedObject = new OuterClass.NestedClassStatic (); 
```


## Nested Classes - Inner
Inner is used when you want to have access to some method of the parent class.

```bash
public class Outer {
  public class Inner {
  }
}
Out outer = new Outer ();
Outer.Inner inner = outer.new Inner ();  
```
## Interfaces
###Characteristics of the interfaces:
- New access modifiers (default and private). This allows overwrite methods and adding behavior to them . Methods with implementation and without implementation can be defined.
- Methods can be implemented in many class families. Therefore, it is not linear.
###When to use them:
- An interface is used when there are methods that can be implemented in many families (The relationship goes further between two classes).
- An interface is thought of when the focus is more on the actions that many objects may have in common.
- It will find actions like Drawable Drawable, Runnable, etc. 
- An interesting thing that happens in case of inheritance with interfaces multiple inheritance is allowed as shown below.

```bash
public interface Visualizable extends IReadable, Serializable {
  public void setViewed ();
  public Boolean isViewed ();
  public String timeViewed ();
  @Override
    default void read () {
    // TODO Auto-generated method stub
    }
  } 
```
## Enumerations
Enumerations are very special data types because it is the only data type that has a collection of constants, as they are constant we will be forced to write them with capital letters.
We will use enum every time we need to represent a fixed set of constants. For example the days of the week. public enum
```bash
Day {
SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY}
} 
```
Enumerations can have attributes, methods, and constructors 

## Map Interface
The Map interface does not inherit from the Collection interface because it represents a Mapping data structure and not a simple collection of objects. This structure is more complex, since each element must come in pairs with another piece of information that will function as the element's key.
Map <K, V>
- Where K is the key
- Where V is the value 
###Map has the following implementations:
- HashMap: Items are not sorted. They do not accept duplicate keys or null values.
- LinkedHashMap: Sorts the elements as they are inserted; causing searches to be slower than the other classes.
- TreeMap: The Map sorts it in a "natural" way. For example, if the key is integer values, order them from least to greatest.
To iterate any of these it will be necessary to use the Iterator interface and to go through it a while loop is used as shown: 
### HashMap:
```bash
Iterator it = map.keySet (). Iterator ();
while (it.hasNext ()) {
   Integer key = it.next ();
   System.out.println ("Key:" + key + "-> Value:" + map.get (key));
} 
```
### LinkedHashMap:
```bash
Iterator it = linkedHashMap.keySet().iterator();
while(it.hasNext()){
  Integer key = it.next();
  System.out.println("Clave: " + key + " -> Valor: " + linkedHashMap.get(key));
}

```
### TreeMap:
```bash
 Iterator it = treeMap.keySet().iterator();
while(it.hasNext()){
  Integer key = it.next();
  System.out.println("Clave: " + key + " -> Valor: " + treeMap.get(key));
}
```
## Error handling
- Throwable
  - Error: Caused by java virtual machine (JVM).
  -  Exception: Caused by the developer.
     - UNCHECKED: Errors that we do not know initially. Logic errors. For example, arimetics or adding to an index of an array that does not exist.
       - RuntimeException: At the moment the application is running.
     - CHECKED: Most Expected Errors.
       - SQLException: Error in database query syntax.
       - IOException: Error reading a file or data input / output.
       - FileNotFoundException: A file was not found. 

Handling Exceptions means adding a block of code to handle an error.
##Try-catch-finally
Each catch block is an exception handler that handles the type of exception indicated by its argument. The argument type, ExceptionType, declares the type of exception that the handler can handle and must be the name of a class that inherits from the Throwable class. The handler can refer to the exception with name.

```bash
try {
} catch (ExceptionType name) {
} catch (ExceptionType name) {
} 
```

```bash
finally{
	if(out != null){
		System.out.println("Closing PrintWriter");
		out.close();
	}else{
		System.out.println("PrintWriter not open");
	}
}
```

Try-with-resourses
Support for try-with-resources – introduced in Java 7 – allows us to declare resources to be used in a try block with the assurance that the resources will be closed when after the execution of that block.

```bash
BufferdReader reader = new BufferedReafer(new InputStreamReader(System.in));
try(reader){
//sentencias
} catch(Exception e){
}
```

##JDBC - Java Database Connectivity
API definition and composition
It is an API composed of several classes for database operations.
Classes:
DriverManager: Allows us to create an instance of the connection
Connection: Generates the session, manages the entire life cycle of a session when we connect to a database.
Statement: It helps us to fetch data from a table.
PreparedStatement: It does the same as Statement with the difference that it allows us to receive parameters for the where clause.
ResultSet: It is an interface that will help us manage the data obtained by converting the data into objects. 

CRUD

|          Method          | Returns                                | Used for                         |
|:------------------------:|----------------------------------------|----------------------------------|
| executeQuery(sqlString)  | ResultSet                              | SELECT statment                  |
| executeUpdate(sqlString) | int(rows affected)                     | INSERT, UPDATE, DELETE, or a DDL |
| execute (sqlString)      | boolean(true if there was a ResultSet) | Any SQL command or commands      |

## Declarative vs imperative paradigm
Paradigm: the form or series of rules in which a language has to be adjusted to solve a program.

-Imperative: Structured, Procedural, OOP, Other
- Declarative: Functional, Logical, Others

- Imperative Programming focuses on the How?
  - Approach: outline all the steps to solve the problem.
- Functional programming focuses on the What?
  - Approach: state what the program is doing

Core of functional programming:
input as function -> function as operation -> output as function 

## Lambdas:
Basic structure: (parameters) -> {body-lambda}
They are used only in case of:
- Code with a short life time.
- Encapsulate specific code. 

To define a lambda we can do it by implementing:
- Functional Interface
  - You must have a single abstract method without implementation (SAM).
  - It is indicated by the following annotation: @FunctionalInterface 
- Abstract classes: A class becomes abstract the moment an abstract method is included in it, at that moment the abstract modifier must be placed on the class. 

```bash
OnOneListener oneListener = new OnOneListener () {
	//Without lambda
	@Override
	public void onOne (String message) {
	// TODO Auto-generated method stub
	System.out.println ("One:" + message);
	}
	};

	//With Lamnda
	OnOneListener oneListener2 = (String message) -> {

	};

oneListener.onOne ("Without lambda");
oneListener2.onOne ("With Lamnda");

}
```

## Recursion with lambdas
lambda-oriented functional programming does not use iteration, recursion is used.
```bash
// collection of objects, forEach receives an action and the action will be the lambdas
objects.forEach ()
ArrayList <Film> films = new ArrayList ();
films.forEach (f -> System.out.println (f.toString ()));
```

## Stream and Filter
Sream is a method that was added to the collections to handle lambas.
```bash
objects.stream ().filter() 
```
