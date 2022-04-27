
# @author : 7elmie

    -Difference between self and __init__ ?

    self :

self represents the instance of the class.
By using the "self" keyword all the attributes and methods of the python class can be accessed.

    __init__ :

    "__init__" 

is a reserved method in python classes.
It is known as a constructor in object oriented concepts.
This method is called when an object is created from the class
and allows the class to initialize class attributes ..

# Use self when:

    you define an instance method, since it is passed automatically as the first parameter when the method is called;
    you reference a class or an instance attribute from inside an instance method;
    you want to refer to instance variables and methods from other instance methods.

#  Don’t use when:

    you want to call an instance method normally;
    referencing a class attribute inside the class definition but outside an instance method;
    you are inside a static method.

# Conclusion:

Let us recap the key points we have covered in this article, namely:
    
    -Instances and Classes in Python.
    -Self variable and its importance.
    -The explicitness of the self variable.
    -Python class self constructor.
    -Passing self as a method.
    -Skipping self in Python.
    -Variables used for Class methods and Static methods.
    -Bounding of self to the current instance.
    -When to use and when not to use self in Python.



# what is Self in Python ?

    Unlike this variable in C++, self is not a keyword rather it is more of a coding convention. It represents the instance or objects of a class and binds the attributes of a class with specific arguments. The use of self variable in Python helps to differentiate between the instance attributes (and methods) and local variables.
    If you do not want the variables of your class to be shared by all instances of the class, you can declare variables within your class without self.

# Let us understand this with an example:

    class Car:
    def __init__(self, model):
        self.model = model
    def Car_info(self):
        print("Model : ", self.model)

Here, we have declared a class Car with one instance variable self.model = model.
The value of the instance variable will be unique to the instance objects of the class that might be declared.
However, if you want the variables to be shared by all instances of the class, you need to declare the instance variables without self.
Otherwise, it would be ambiguous since all cars will have the same model.


# Need for Self in Python :

The self variable is used to represent the instance of the class which is often used in object-oriented programming.
It works as a reference to the object.
Python uses the self parameter to refer to instance attributes and methods of the class.
Unlike other programming languages, Python does not use the “@” syntax to access the instance attributes. 
This is the sole reason why you need to use the self variable in Python.
The language contains methods that allow the instance to be passed automatically but not received automatically.


# What is a Python class self constructor?
The self variable in Python can also be used to access a variable field within the class definition. 
Let us understand this with the help of example code:

class Student:

    def __init__(self, Alex):
        self.name = Alex    #name created in constructor
    def get_student_name(self):
        return self.name

In the example above, self refers to the variable age of the class Student.
The variable age is local to the method. While the method is running, the variable age exists within the class.
If there is a variable within a method, the self variable will not work.
If you wish to define global fields, you need to define variables outside the class methods.
