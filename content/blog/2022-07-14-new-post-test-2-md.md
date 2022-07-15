---
layout: blog
title: New Post Test 2 MD
date: 2022-07-14T19:09:00.671Z
thumbnail: /src/images/blog.png
code:
  code: var x = 10
  lang: javascript
---
# What is Lorem Ipsum?
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,

Indented code

 
    line 1 of code
    line 2 of code
    line 3 of code

**Howdie, folks!** Today we are going to learn a bit about the vast world of **inheritance** from the realms of the Object Oriented Programming: Are you guys ready for this amazing adventure? If so, let's get ready to rumble, pals!
## What is inheritance?
Perhaps you are now thinking in that old grumpy auntie of yours that always pulled your cheeks when you were little and that recently passed away and left a fortune for some of her relatives. If that was your case, then let me tell you that we are going to talk about a different type of inheritance.
In the programming world, inheritance allows us to define a class that could possibly and positively inherit all of the methods and properties from another class, usually called the parent.

**Parent class** is the class being inherited from, also known as base class. We usually call it **Padre** in Spanish.
**Child class** this one inherits properties and methods from another class, also known as derived class. This is **Hija**.
### Parent Class Creation
We will start building the parent class first. Any class can be a parent, hence, we will proceed to write the code using the regular classes syntax and structure, as any other class.
```python
# Represents any school member.
class SchoolMember:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        print(f"Initialized SchoolMember for: {self.name}")
    # Tell my details.
    def tell(self):
        print(f"Name: {self.name} Age: {self.age}")
```
You see? it was not that hard, pal! Now we have this blueprint of a school member that we could use as much as we want. But what happens if I just want to create another class and keep the parent structure plus some other features I might want to have in it? Well, that is where the Child class takes place to save the day.
### Child Class Creation
If we would like to integrate the functionality and characteristics from another class in our own class, we need to pass the **Parent class or Clase Padre** as a parameter when creating this class that we will call the Child class, or better yet, **La Clase Hija**.
In the example below, we will create two new classes called Teacher and Student, both with the existing Parent properties from the initial **SchoolMember Class**, but also creating some additional features of their own.
```python
# Represents a teacher.
class Teacher(SchoolMember):
    def __init__(self, name, age, salary):
        SchoolMember.__init__(self, name, age)
        self.salary = salary
        print(f"Initialized Teacher: {self.name}")
    def tell(self):
        SchoolMember.tell(self)
        print(f"Salary: {self.salary}")
# Represents a student.
class Student(SchoolMember):
    def __init__(self, name, age, marks):
        SchoolMember.__init__(self, name, age)
        self.marks = marks
        print(f"Initialized Student: {self.name}")
    def tell(self):
        SchoolMember.tell(self)
        print(f"Marks: {self.marks}")
```
At this stage of the article, You might be wondering how to do when we already had a class and we would've liked to add additional properties and methods from another one, without losing its own independence as a class.
Well, this can be done by overriding the inheritance from a parent class using for this the **__init__() function**. This function is automatically invoked every time the class is being used to create a new object. Let's take a look at this in the following example.
```python
class Counselor(SchoolMember):
    def __init__(self, name, age):
        SchoolMember.__init__(self, name, age)
```
Now we have successfully added the **__init__() function**, keeping the inheritance of the parent class, we are now ready to add functionality inside this function.
## The Super Function
The time has come for us to use some of the magic of the Object Oriented Programming and unleash one of its secret powers: There is a fantastic function called **super()** that allows the child class to inherit all the methods and properties from its parent.
If it happens in real life with our kids with the parent characteristics and abilities, why not in programming with OOP classes as well, right folks?
Keep in mind that when using this function, you do not have to use the name of the parent element, it will automatically inherit the methods and properties from its parent.
```python
class Principal(SchoolMember):
    def __init__(self, name, age):
        super().__init__(name, age)
```
## Additional Properties and Methods
**Wait a minute:** All of this sounded great and stuff but, how do we go about adding our own methods and properties after this step? Do we still have a chance to do that or not?
Well, pals, we actually can! let's learn about it in the following example where we will add the phone property to it:
```python
class Nurse(SchoolMember):
    def __init__(self, name, age, phone):
        SchoolMember.__init__(self, name, age)
        self.phone = phone
```
As you might've noticed, the phone property cannot be fixed, and passed into the Nurse class when creating SchoolMembers objects. So, the question arises: how do we pass the non-fixed value to it? Well, we simply add another argument in the __init__() function as the example shows.
Whenever feasible, We can definitively add methods to this class. Let's take a look at the updated example below:
```python
class Nurse(SchoolMember):
    def __init__(self, name, age, phone):
        SchoolMember.__init__(self, name, age)
        self.phone = phone
    def greet(self):
        print(
            "Hello, ",
            self.name,
            ".\nYour Age is ",
            self.age,
            " years old and your Phone is: ",
            self.phone,
        )
```
Ok, enough technicality already: let's test this bad boys out by creating several instances of these classes and adding their respective parameters as needed.
```python
# Let us put these babies in action by creating instances, shall we?
sm = SchoolMember("Bill Gates", 56)
t = Teacher("Guido Van Rossum", 64, 95000)
s = Student("Alvison Hunter", 41, 900)
c = Counselor("Mark Zuckerberg", 34)
p = Principal("Evan You", 23)
n = Nurse("Sarah Drasner", 24, 99887766)
```
Next, we need to create a list with all these instances to iterate over each of them afterwards, just as follows:
```python
# Declare an list containing all these instances
members = [t, s, c, p, n]
for member in members:
    # Let's print each of their details
    member.greet() if(member == n) else member.tell()
```
## Final Source Code:


All right, folks, we have come to the end of this article. Your adventure started with a quick look at single inheritance and then we learned how to call superclass methods and properties easily with super() function.


This is only the beginning of a very deep topic, full of more interesting features, however, we have tried to put together enough information to at least cover the basic starting point of this.


Please find below the final source code for you guys to test it out and play with it. Please leave your comments with some other approaches or better solutions, to update the post if needed.


Last but not least, If you are a **Python enthusiast**, I kindly invite you to take a look at my [Python and JavaScript](https://bit.ly/3p9hpqj) YouTube Channel tutorials and subscribe whenever possible to help our community grow.


I'd like to give a special shout-out to my sister **Kathya** for bringing Python to my head today. This event got me inspired to write this article after I spoke to hear about the beauty of this fantastic programming language.


---

```python
# Represents any school member.
class SchoolMember:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        print(f"Initialized SchoolMember for: {self.name}")
    # Tell my details.
    def tell(self):
        print(f"Name: {self.name} Age: {self.age}")
# Represents a teacher.
class Teacher(SchoolMember):
    def __init__(self, name, age, salary):
        SchoolMember.__init__(self, name, age)
        self.salary = salary
        print(f"Initialized Teacher: {self.name}")
    def tell(self):
        SchoolMember.tell(self)
        print(f"Salary: {self.salary}")
# Represents a student.
class Student(SchoolMember):
    def __init__(self, name, age, marks):
        SchoolMember.__init__(self, name, age)
        self.marks = marks
        print(f"Initialized Student: {self.name}")
    def tell(self):
        SchoolMember.tell(self)
        print(f"Marks: {self.marks}")
class Counselor(SchoolMember):
    def __init__(self, name, age):
        SchoolMember.__init__(self, name, age)
class Principal(SchoolMember):
    def __init__(self, name, age):
        super().__init__(name, age)
class Nurse(SchoolMember):
    def __init__(self, name, age, phone):
        SchoolMember.__init__(self, name, age)
        self.phone = phone
    def greet(self):
        print(
            "Hello, ",
            self.name,
            ".\nYour Age is ",
            self.age,
            " years old and your Phone is: ",
            self.phone,
        )
# Let us put all of these babies in action by creating instances, shall we?
sm = SchoolMember("Bill Gates", 56)
t = Teacher("Guido Van Rossum", 64, 95000)
s = Student("Alvison Hunter", 41, 900)
c = Counselor("Mark Zuckerberg", 34)
p = Principal("Evan You", 23)
n = Nurse("Sarah Drasner", 24, 99887766)
# Declare an list containing all these instances
members = [t, s, c, p, n]
for member in members:
    # Let's print each of their details
    member.greet() if(member == n) else member.tell()
```
:corazón: If you've enjoyed this article, that motivates to write more!
:cara_de_unicornio: If you truly consider this article helped you wholly!
:marcador: If you need to check back on this article later on.
:cara_pensativa: Please leave your comment, your opinion very important.


