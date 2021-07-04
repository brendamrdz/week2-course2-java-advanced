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

[aqui](https://docs.oracle.com/javase/7/docs/technotes/tools/windows/javadoc.html#code )
