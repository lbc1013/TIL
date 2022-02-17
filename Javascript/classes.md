# Classes

> - It was introduced in the ES6 version, classes are nothing but syntactic sugars for constructor functions.
> - They provide a new way of declaring constructor functions in Javascript.

### Before ES6 version, using constructor functions

````javascript
function Student(name,rollNumber,grade,section){
  this.name = name;
  this.rollNumber = rollNumber;
  this.grade = grade;
  this.section = section;
}

````
### Way to add methods to a constructor function

````javascript
Student.prototype.getDetails = function(){
  return 'Name: ${this.name}, Roll no: ${this.rollNumber}, Grade: ${this.grade}, Section:${this.section}';
}

````
````javascript
let student1 = new Student("Vivek", 354, "6th", "A");
student1.getDetails();
// Returns Name: Vivek, Roll no:354, Grade: 6th, Section:A
````

### ES6 version classes

````javascript
class Student{
  constructor(name,rollNumber,grade,section){
    this.name = name;
    this.rollNumber = rollNumber;
    this.grade = grade;
    this.section = section;
  }

// Methods can be directly added inside the class
  getDetails(){
    return 'Name: ${this.name}, Roll no: ${this.rollNumber}, Grade:${this.grade}, Section:${this.section}';
  }
}
````

````javascript
let student2 = new Student("Garry", 673, "7th", "C");
student2.getDetails();
// Returns Name: Garry, Roll no:673, Grade: 7th, Section:C
````

> - Unlike functions, classes are not hoisted. A class cannot be used before it is declared.
> - A class can inherit properties and methods from other classes by using the extend keyword.
> - All the syntaxes inside the class must follow the strict mode(‘use strict’) of javascript. Error will be thrown if the strict mode rules are not followed.