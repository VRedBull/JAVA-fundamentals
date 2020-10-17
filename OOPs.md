# Object Oriented Programming System (OOPs)

Java Is a OOP language.

OOP concepts are:-

- Objects
- Classes
- Inheritance
- Polymorphism
- Abstraction
- Encapsulation

**The Four Pillars of OOPs are**

- Inheritance
- Polymorphism
- Abstraction
- Encapsulation

## Objects And Classes

- There can be only **one public class** in a single java file.
- You can have many Objects of a single class
- But you can't have many class of single object.
- Class(except the public class of the file) doesn't itself take memory but...while creating a object it does.

**Think of Class as a Blueprint of a building, and now after creating a blue print you can have many buildings of it (with different properties such as different number of rooms, windows, doors)...But a Single Building can't have many Blue prints.**

```java
public class ClassObjects {
        public static void main(String...args){

            Cat cat1 = new Cat();       //Creating a object cat1 of Class Cat
            Cat cat2 = new Cat();       //Creating a object cat2 of Class Cat

            //Using the description method/behaviour of class Cat for different objects
            cat1.eat();
            cat2.walk();

            //Using the legs property of class Cat

            cat1.legs = 3;
            cat2.legs = 4;

            cat1.eyes = 2;
            cat2.eyes = 3;

            cat1.name = "Jimmy";
            cat2.name = "Fury";

            cat1.hasFur = false;
            cat2.hasFur = true;

            //Using the description method/behaviour of class Cat for different objects
            cat1.description();
            cat2.description();

        }
}

class Cat{
    int legs, eyes;     //Properties of Cat class
    String name;
    boolean hasFur;

    public void eat(){
        System.out.println("Your cat is eating.");
    }
    public void walk(){
        System.out.println("Your cat is sleeping.");
    }
    public void description(){
        System.out.printf("Your cat %s is with %d legs and %d.%n",name, legs, eyes);
    }

}
```

Another example

```java
//Added Another class

public class ClassObjects {
    public static void main(String... args) {
        Dog dog1 = new Dog();
        Dog dog2 = new Dog();

        dog1.name = "Tom";
        dog2.name = "Jerry";

        dog1.jump();
        dog2.jump();

        dog1.description();
        dog2.description();

    }
}
class Cat{
    int legs, eyes;     //Properties of Cat class
    String name;
    boolean hasFur;

    public void eat(){
        System.out.println("Your cat is eating.");
    }
    public void walk(){
        System.out.println("Your cat is sleeping.");
    }
    public void description(){
        System.out.printf("Your cat %s is with %d legs and %d.%n",name, legs, eyes);
    }

}

class Dog{
    String breed, name;
    public void jump(){
        System.out.println("You Dog named "+name+" has jumped");
    }
    public void description(){
        System.out.println("The name of dog is "+name+"it's breed is "+breed+".");
    }
}
```

## Methods

- There can be only one Public class(which is same as the file name) and inside that class only there will be the **main method.**

- Should write static method for calling in the main method (as main method is static itself)

  ```java
  public class MethodsIntro {
      public static void main(String...args){
          System.out.print(maxOf(2,3));	//Calling the method and passing arguments
      }
  
      static int maxOf(int a, int b){
          if(a>b){            //Same as return a>b ? a:b
              return a;
          }else{
              return b;
          }
      }
  }
  ```

- A Void method (returns no data)

  ```java
  static void sayHi(){		//no parameters
          System.out.println("Hi");
          System.out.println("What's Up, bro?");
      }
  ```

- calling a method in main method is as simple as 

  ```java
  public class MethodsIntro {
      public static void main(String...args){
          System.out.println(maxOf(2,3));
          sayHi();		//Calling sayHi method
      }
  
      static int maxOf(int a, int b){
          if(a>b){            //Same as return a>b ? a:b
              return a;
          }else{
              return b;
          }
      }
      static void sayHi(){
          System.out.println("Hi");
          System.out.println("What's Up, bro?");
      }
  }
  ```

### Method Overloading

- When a class have same name but different parameters are known as method overloading.

- It doesn't matter if it's a return type or void method the formal parameters should be different.

  Example of Method Overloading

  ```java
  //Parameters should always be different.
  public class MethodsIntro {
      public static void main(String...args){
          int addition = operation(4,5);
          double divide = operation(4.0,5.0);
          System.out.println("addition = "+addition + " division = "+divide);
          operation(2,3,4);
      }
      static int operation( int a, int b){
          return a+b;
      }
      static double operation(double a, double b){
          return a/b;
      }
      static void operation( int x, int y, int z){
          System.out.println("multiplied = "+x+"*"+y+"*"+"*"+z+"="+x*y*z);
      }
  }
  ```
  
  **Method OverLoading can be also done on the main method**. 

**Java is a pass by value language**

- It means that in Java when we pass the argument there will be a copy of the variable made inside the method which was called.

- And we can change the value of the copy made inside the method which was called and it won't affect the original value which was passed originally from another method(original method can be the main method).

  ```java
  //For eg.
  public static void main(String...args){
      int x = 25;
      fun(x);		//Here the method is called by passing the value of 25 
  }
  static void fun(int a){		//Here it received the value of 25 ...and then here it made a = 25
      a = 10;		//Here we changed the value to 10...and this won't affect the value of x in main method
      System.out.print(" a = "+a);		//it print a = 10;
  }
  ```

- In pass by reference we keep passing the same memory location instead of creating a new copy in the method which was called...this doesn't happen in java.

- While this a bit different for non-primitive data types...for eg.

  ```java
  public class PassByValue {
  
      public static void main(String...args){
          Dog jim = new Dog();		//Created a new object of Dog class called jim
          jim.legs = 4;		//jim got 4 legs
          System.out.println("Original no. of legs="+jim.legs);	//Here jims legs are 4
          fun(jim);	//we called fun method and passed the jim reference
          System.out.println("After calling the fun method no. of legs="+jim.legs);	//Now after aron's leg //became 6 in fun method it also became same for jim...(since aron is same jim but, jim is aron for fun method //only )
      }
  
      static void fun(Dog aron){	//now here jim's name is replaced by aron, and treat it as jim but only for fun 									//method.
          aron.legs = 6;		//now jim's leg(for this method aron's) are 6.
      }
  }
  
  class Dog{	//We created the Dog class
      int legs;	//Gave it a property of legs
  }
  //OutPut
  Original no. of legs=4
  After calling the fun method no. of legs=6
  ```

  

- So, **JAVA is a pass by value language**.

# Constructor's in JAVA

- Constructor's in java look similar to methods

- They don't have any kind of return.

- The name of the Constructor must be same as the name of the class.

- **It's basically used to instantiate the properties/variables/state of class.**

- Constructor can be instantiated like this...

  ```java
  public class MyConstructor {
      MyConstructor(){    //Name of the Constructor should always be equal to name of the class
  		
      }
      public static void main(String...args){		This is the main method
  
      }
  }
  ```

- Making a new object for the class.

  ```java
  public class MyConstructor {
      MyConstructor(){    //Name of the Constructor should always be equal to name of the class
          System.out.print("Constructor is created.");
      }
      public static void main(String...args){
  
          MyConstructor obj = new MyConstructor();    //This is a bit like calling the Constructor 
      }
  }
  ```

### No argument Constructors

- We can instantiate the property/state of class in a constructor like this...

  ```java
  public class MyConstructor {
      MyConstructor(){    //Name of the Constructor should always be equal to name of the class
          System.out.println("Constructor is created.");
      }
      public static void main(String...args){
  
          MyConstructor obj = new MyConstructor();    //This is a bit like calling the Constructor
  
          Vehicle car = new Vehicle();	//can create many objects but the wheel property will remain same.
          Vehicle car2 = new Vehicle();	//we can change the property by doing car2.wheels = 2
  
          System.out.println("wheels = "+car2.wheels);
      }
  }
  
  class Vehicle{
      int wheels;	 //Initially the value will be zero..if it was a string then null for boolean it's false...etc.
  	Vehicle(){		//Constructor is created
          wheels = 4;		//property wheels is initialized
      }
  }
  ```

  **NOTE** : If we have made any kind of Constructor then also we can create objects for that class...as the java compiler creates a default constructor and sets all the default values for the properties of class...Like for String null is default value, Boolean is false...etc.

### Parameterized Constructors

- We pass parameters in a Constructor like we do for methods.

- So we can change the values of properties in the class

- For eg..

  ```java
  public class MyConstructor {
      public static void main(String...args){
          Vehicle car = new Vehicle(4);	//Passing the paramerter
          Vehicle scooty = new Vehicle(2);
          System.out.println("Car wheels = "+car.wheels);
          System.out.println("scooty wheels = "+scooty.wheels);
      }
  }
  
  class Vehicle{
      int wheels;
  	Vehicle(int noOfWheels){	//The formal parameter
          wheels = noOfWheels;	//wheels will be equal to according the int value passed in the prameter 
      }
  
  }
  ```

### "this." Keyword

- This keyword is used if the name the local variable created in the constructor have's the same name as the instance(global variable for that class) variable in the class.

- This keyword refers to the current object

- For eg....

  ```java
  class Vehicle{
      int wheels;		//The property(instance variable) of class is created
  
      Vehicle(int wheels){	// here the formal parameter is a creation of a local variable wheels
          wheels = wheels;	// here both the wheels(variables on both sides) refer to the local variable 
      }					// created by the constructor parameter...So the value of instance variable 	
  }						// is still zero(which is by default zero)...only the local variable changed after 
  						//passing the argument
  ```

- If we use the above code for execution of a program

  ```java
  public class MyConstructor {
      public static void main(String...args){
          Vehicle car = new Vehicle(4);
          Vehicle scooty = new Vehicle(2);
          System.out.println("Car wheels = "+car.wheels);
          System.out.println("scooty wheels = "+scooty.wheels);
      }
  }
  
  class Vehicle{
      int wheels;
  	Vehicle(int wheels){	
          wheels = wheels;	
      }
  }
  //OutPut
  Car wheels = 0
  scooty wheels = 0
  ```

  

- For this we use "this" keyword.

- For eg.

  ```java
  class Vehicle{
      int wheels;
  
      Vehicle(int wheels){
          this.wheels = wheels;	//Here on LHS thi.wheels refer to the instance variable of class...and RHS 
      }						  //is the value passed by argument.	
  }
  ```

- If we use the above code for execution of a program

  ```java
  public class MyConstructor {
      public static void main(String...args){
          Vehicle car = new Vehicle(4);
          Vehicle scooty = new Vehicle(2);
          System.out.println("Car wheels = "+car.wheels);
          System.out.println("scooty wheels = "+scooty.wheels);
      }
  }
  
  class Vehicle{
      int wheels;
  	Vehicle(int wheels){	
          this.wheels = wheels;	//using this keyword
      }
  }
  //OutPut
  Car wheels = 4
  scooty wheels = 2
  ```

### Constructor Overloading

Constructor overloading it's just like the method overloading....The parameters should always be different.

For eg.

```java
public class MyConstructor {
    public static void main(String...args){
        Vehicle car = new Vehicle(4);
        Vehicle scooty = new Vehicle(2, "red");
        System.out.println("Car wheels = "+car.wheels);
        System.out.println("scooty wheels = "+scooty.wheels+" and color is "+scooty.color);
    }
}

class Vehicle{
    int wheels;
    String color;
    Vehicle(int wheels){	//formal parameter of only int wheels
        this.wheels = wheels;
    }
    Vehicle(int wheels, String color){	//formal parameter of color and wheels (Constructor overloading)
        this.wheels = wheels;
        this.color = color;
    }	//we use the former(1st) constructor when the color is not given to us(it can be changed later)
}		//we use the latter(2nd) constructor when the color is specified already(though it can changed later)
```

**NOTE** - We cannot call the default constructor(in which all values are null) after making one or more constructor of the class.

But If we still want to call the default constructor for a new object(as we may require every property to be null or zero or false)...so for that we can make a new constructor where we put no argument no body or anything just empty brackets

for eg...

```java
public class MyConstructor {
    public static void main(String...args){
        Vehicle car = new Vehicle(4);
        Vehicle scooty = new Vehicle(2, "red");
        System.out.println("Car wheels = "+car.wheels);
        System.out.println("scooty wheels = "+scooty.wheels+" and color is "+scooty.color);
        
        Vehicle random = new Vehicle();	//We cannot call thhe default constuctor(which will have the default
        							//values) until & unless we create a new null constructor
        System.out.print("random wheels="+random.wheels);
    }								
}

class Vehicle{
    int wheels;
    String color;
    Vehicle(int wheels){	
        this.wheels = wheels;
    }
    Vehicle(int wheels, String color){	
        this.wheels = wheels;
        this.color = color;
    }	
    Vehicle(){	//This is the new null Constructor...which will give the default values to the random object
        }
}   
//OutPut
Car wheels = 4
scooty wheels = 2 and color is red
random wheels=0		//The default value of int property is zero
```

# Encapsulation

- Encapsulation also known as **data hiding**. It means to wrap code in a single unit/class and make it hidden from other classes.
- When you want to access the classes of a certain package in a class in another package you'll have.

### Access Modifiers

The Access Modifiers defines the scope of a field or a method, constructor or a class...we can change the access level by changing the access modifiers applied to it.

- There are four types of access Modifiers in java
- **Private** - Only accessible from within the class, can't be accessed from outside the class
- **Default** - The access level remains till only inside the package. If we do not specify any access modifiers then it'll be default access....and it can't be accessed from outside the package.
- **Protected**  - It's Only accessible to the child class. And the child class can be any package.
- **Public** - This can be accessed from any where from any class and from any package.

### How to achieve **encapsulation**

1. Declare the variables in the class as private and methods(getter & setter) as public.

2. Provide public getter and setter methods that'll be used to write and read these variable values.

3. That's it.

4. For eg.

   ```java
   package Encapsulation;
   public class EncapsulationIntroduction {
       public static void main(String[]args){
           Student obj = new Student();
           obj.setAge(21);
           System.out.print(obj.getAge());
       }
   }
   ```

   Another class from which age property is being used and modified as per the object in the above class.

   ```java
   package Encapsulation;
   
   public class Student {
       private int age;		//Declaring the variables as private
       private String name;
   
       public int getAge(){        //This is the getter method which is public
           return age;
       }
       public void setAge(int age){       //This is the setter method 
           if(age>20){
               System.out.println("You are too old");
           }
           else{
               this.age = age;
           }
       }
   }
   ```

   The getter and setter methods can be directly made in an IDE like IntelliJ or Eclipse.

   By right clicking on source code in the IDE then generate then select getter and setter methods.

### Why Encapsulation?

- Encapsulation makes our code more readable and cleaner.
- It helps in modification of our data fields. So that the properties of a particular class cannot be modified by any other class in any way.
- If there's a defect in a particular class then it won't effect other things there.

### Encapsulation vs data hiding 

- Encapsulation refers to the bundling of related fields and methods together. This allows us to achieve data hiding. Encapsulation itself is not data hiding.

### Reversing a String word by word.

My version of reversing string alphabet by alphabet.

```java
public class StringRev {
    public static void main(String[]args){
        String str = "Vikas";
        StringBuffer strRev = new StringBuffer();//StringBuffer Let's us do append, insert and all sort of things 												//with string
        for(int i = str.length()-1; i >= 0; i--){
            strRev = strRev.append(str.charAt(i));
        }
        System.out.println("Original string = "+str);
        System.out.println("reversed = "+strRev);
    }
}
//Output
Original string = Vikas
reversed = sakiV
```

## Static Keyword

- Static keyword is related to class.

- The values of Static methods/variables/nested class/blocks doesn't change.

- Static keyword is used on variables, methods, blocks, nested class.

- **If Static variables values are changed then it changes for all the objects of that class.** 

- We can use the static variable or methods even before making objects of it.

- For eg....

  ```java
  class Emp{
      int eId;		//Vairous properties of Emp class
      int salary;
      static String ceo;		//As the ceo for all employees remain the same, static keyword is used
  
      public void info(){		//A method to print the values of all the objects
          System.out.printf("%d : %d : %s%n",eId,salary,ceo);
      }
  }
  public class StaticKeyword {
      public static void main(String...args){		//main method is also static
          Emp vikas = new Emp();	//new object of Emp class
          vikas.eId = 4;	//eId and Salaray will be different for every object, so not static
          vikas.salary = 3000;
         // vikas.ceo = "pradhan";	//here we can say that the ceo of vikas object is "pradhan" so it's changes 							//for all the objects of Emp class to "pradhan".
  
          Emp vivaan = new Emp();	//vivaan object of Emp class
          vivaan.eId = 5;
          vivaan.salary = 4000;
          //vivaan.ceo = "pradhan";	//we would have done this for every object if ceo was not static
  
          Emp.ceo = "pro";	//as the ceo is static we should directly set the value through class without using 						//onjects
  
          vikas.info(); 	//printing all the values of objects
          vivaan.info();
      }
  }
  //output
  4 : 3000 : pro
  5 : 4000 : pro
  ```

  ### Static block

  - We use Static blocks to initialize things before reaching the main method.

  - The static blocks will run according to their sequence as they're arranged...but they'll be executed first as soon as we run our program.

  - For Eg.

    ```java
    public class A{
    	static{
    		System.out.println("static 1");
    	}
    	static{
    		System.out.println("static 2");
    	}
    	public static void main(String...args){
    		System.out.println("method");
    	}
    	static{
    		System.out.println("static 3")
    	}
    }
    //OutPut
    static 1
    static 2
    static 3
    method
    ```

    

  ```java
  class Emp{
      int eId;
      int salary;
      static String ceo;
  
      static{     //This is static block used for static values and executed only once
          ceo = "pradhan";
          System.out.println("static");       //The static block is is executed only once for a class 
      }
      public Emp(){      //Constructor is used for when you create an object and used for every object
          eId = 1;
          salary = 2000;
          System.out.println("Constructor");      //The Emp class is executed for every objected created
      }
  
      public void info(){
          System.out.printf("%d : %d : %s%n",eId,salary,ceo);
      }
  }
  public class StaticKeyword {
      public static void main(String...args){
          Emp vikas = new Emp();
  	    Emp vivaan = new Emp();
           
          vikas.info();
          vivaan.info();
      }
  }
  //Output
  static		//printed static only once as it executes static block only once for every class
  Constructor	//printed constructor twice as for two objects it executed constructor two times
  Constructor
  1 : 2000 : pradhan
  1 : 2000 : pradhan
      
  //Note - the static block will be executed first irrespective of it's position in code
  ```

  - **Conclusion** - Static variables are same for all objects

       - Non static variables are different for all objects

       - Cannot use non-static variables in static block.

         For eg....

         ```java
         //This code will error as the variable inside method main is not static
         public class Main{
          
         int i = 0;
         	public static void main(String...args){
         		i = 9;
         	}
         }
         ```

         We can fix this by adding the static keyword before the variable...as it'll be used in the static main method

         ```java
         public class Main{
          
         static int i = 0;	//will have to use static keyword if we gonna use it inside a static method
         	public static void main(String...args){		//main method is static method...it's a static block
         		i = 9;	
         	}
         }
         ```

         - We cannot Declare a top-level class with static modifier, but we can declare a nested class as static.

         - Nested class is a class inside another class.

         - For eg.

           ```java
           class OuterClass{
           ....
           	static class StaticNestedclass{
           		....
           	}
           	class InnerClass{
           		
           	}
           }
           ```

         ### Now Why inner Static class?

         - We need inner static  so that we can make object of it directly...without accessing the outer class.

         - But the non-static inner class cannot be accessed without first making the object of the outer class then using the object of outer class to make the object of inner class.

         - For Eg.

           ```java
           public class StaticNestedClass {
               A objA = new A();    //Making the object of A to make a new object for B
               A.B objB = objA.new B();	//Making the object of B using Object of A
               A.C objC = new A.C();	//Only accessing the class A for making object of C not accessing the 							//object of A
           }
           
           class A {	//Outer class
               class B{	//Inner non-static class
               }
               static class C {	//Static inner class
               }
           }
           ```

           

# Inheritance

- Inheritance can be defined as to inherit properties and methods of parent class by another child class.

- By inheriting we can use to protected properties and methods as well.

- **In JAVA, all the class are a child of the object class**(which have many properties, that we use).

- In JAVA, it is a IS-A, HAS-A relationship...For eg. A DOG is a Animal so Dog class have inherited from the Animal class. There is a bucket in the bathroom, so Bathroom class HAS-AN object of Bucket class.

- We can Inherit a class by using the **extends** keyword.

- For eg....

  ```java
  class Child extends Parent{}	//left of extend is child class which is gonna inherit and on right of extends 								//it's Parent class from which it's inherting
  ```

- Practical Eg...

  - A person cat eat, sleep, walk.
  - But Some persons are teacher and they teach.
  - Some are footballer and can play football.
  - So we make a Person class which can eat, sleep, walk.
  - A child of person class Teacher class which can teach.
  - A child of person class Footballer class which can play football.

  Person class

  ```java
  public class Person {
      protected String name;	//All persons have different names
  						//All persons can do these common activites i.e. all child of person class can 								//eat(),sleep() and walk().
      public void eat(){
          System.out.println(name+ " Eating now");
      }
      public void sleep(){
          System.out.println(name+" Sleeping now");
      }
      public void walk(){
          System.out.println(name+" Walking now");
      }
  }
  ```

  Teacher class

  ```java
  public class Teacher extends Person {
      public void teach(){	//This Person class's child can also teach
          System.out.println(name+" Teaching a class");
      }
  }
  ```

  FootBaller class

  ```java
  public class Footballer extends Person{
      public void playsFootball(){	//This Person class's child can also play football
          System.out.println(name+" Playing football");
      }
  }
  ```

  The Main class where the program will be executed

  ```java
  public class Main {
          public static void main(String...args){
          Footballer f = new Footballer();
          f.name = "Ronaldo";
          f.playsFootball();
          f.eat();
          f.walk();
          f.sleep();
  
          System.out.println();
          Teacher t = new Teacher();
          t.name = "feynman";
          t.teach();
          t.eat();
          t.walk();
          t.sleep();
  
      }
  }
  ```

- **In Java a Parent class can have multiple children but a child cannot have multiple parents the child can have only one parent.**

# Method Overriding

- Sometimes it may happen that there will be a same function in the Superclass(parent class) as in the subclass(child class).

- In method overriding the parameters remain same. (unlike method overloading).

- **In that case the Subclass method will override the method in Superclass**.

- For eg..In the above example we created the Person as the parent class and teacher and footballer as the child class.

- The Person class have the eat(), sleep(), walk() methods we will override the eat method in teacher and footballer class.

- We can also use the keyword @**Override** before writing the method in the child class...so that it'll give compile time error if we do make a mistake while writing the name of the method(which needs to be same as the method name in parent class).

  Note - that the Person class and the main class remain the same as the above example.

  ```java
  //footballer subclass of Person class
  public class Footballer extends Person{
      public void playsFootball(){
          System.out.println(name+" Playing football");
      }
      public void eat(){		//Method overriding
          System.out.println("Footballer "+name+ " Eating now");
      }
  }
  ```

  ```java
  //Teacher subclass of Person class
  public class Teacher extends Person {
      public void teach(){
          System.out.println(name+" Teaching a class");
      }
      @Override		//Using this keyword is optinal...we use this so that we don't make a mistake while writing
   //the name of the same method as in the parent class, so that it'll give compile time error instead of runtime
      public void eat(){		//Method overriding
          System.out.println("teacher "+name+ " Eating now");
      }
  }
  ```

  The Out will be...

  ```java
  //OutPut
  Ronaldo Playing football
  Footballer Ronaldo Eating now	//The eat method of super class(Person) was ignored and eat() of footballer
  Ronaldo Walking now				//was executed
  Ronaldo Sleeping now
  
  feynman Teaching a class
  teacher feynman Eating now		//Here also the method of SubClass overrides the method of SuperClass
  feynman Walking now
  feynman Sleeping now
  
  ```

**UpCasting** and **Downcasting** do again and read it in java fundamentals book in Polymorphism topic (pg. 446).

## TypeCasting 

```java
Object o = new String();	//Parent p = new Child();...so this is a object of Child class. Here, Object is parent P d = new E();							//and String is child
StringBuffer sb = (StringBuffer)o;
A b = (C)d;
```

P d = new E();			[ P = Object, d = o, E = String()]

A b = (C)d;				 [ A = StringBuffer, b = sb, C = StringBuffer, d = o]

**1st Rule: Compiler Checking** 

- The Compiler is gonna check If C and d have a relationship like if they are parent-child or child-parent or same.

**2nd Rule: Compiler Checking**

- The Compiler is gonna check if the C and A have a relationship (i.e......If C is the child of A or C is same as A only).

**3rd Rule: Run Time Checking**

- In Run time it's gonna check if the object d's internal object ( d is internally type a String type object) should either be same type as C or child of C

- In this case String is not related to StringBuffer ...So it's Going to give a Run-time error of ClassCastException.

- This is the Right example

  ```java
  Parent p = new Child();		//Basically Upcasting
  Child c = (Child)p;			//This is DownCasting
  ```

  **OR**

  ```java
  Object o = new String();
  String s = (String)o;
  ```

  The Above two examples are Right.

Also this is explained in the Inheritance video no.29 of apni kasha name Inheritance video (up and down casting) start from 20th minute.

### Super KeyWord

We use the super keyword when we need to access the parent class properties inside the child class.

for eg... We called the eat() method of Person class inside of eat() method in Footballer class using the super keyword.

```java
//The Person class(Parent class) 
public class Person {
    protected String name;

    public void eat(){	//The eat() method of Person class
        System.out.println(name+ " Eating now");
    }
}
```



```java
//The subclass of Person Footballer class
public class Footballer extends Person{
    public void playsFootball(){
        System.out.println(name+" Playing football");
    }
    public void eat(){
        super.eat();
        System.out.println("Footballer "+name+ " Eating now");
    }
}
//Here due to method overriding when we call eat() the subclass eat() gets called...but there inside eat() method of Footeballer the eat() of Person class is called using the super keyword...so...OutPut is 
//Output
Ronaldo Eating now
Footballer Ronaldo Eating now
```

**super**() keyword used inside constructor

Below Constructors made inside their respective classes.

```java
public Footballer(){
        super();    //This called the Parent class
        System.out.println("Inside Football Constructor");

    }
```

```java
public Person(){
        System.out.println("Inside the Person Constructor");
    }
```

And Then made a object of Footballer class (called the footballer constructor) in Main class in main method.

```java
        Footballer f = new Footballer("Ronaldo");
```

The Output was 

```java
Inside the Person Constructor //First the constructor of Person class was called
Inside Football Constructor	//then it inside and printed the footballer constructor
```

Also The super keyword must be first thing in the constructor body...though it can by anywhere inside method body

When we pass an argument inside the super keyword for the Parent constructor ...all the children class must call the Parent class using the super keyword and using the same argument.

For eg....When we tried to pass name argument in the super keyword in the footballer constructor .... it gave a run-time error and said that we also have to make same type of constructor in the teacher class(as the teacher class was also a child) using the same argument and call the parent class constructor using super keyword passing the same argument.

```java
//Footballer class constructor
public Footballer(String name){
        super(name);    //This called the Parent class
        System.out.println("Inside Football Constructor");
}
```

```java
//The parent class of Footballer and Teacher class
public Person(String name){
        System.out.println("Inside the Person Constructor");
    }
```

Then it gave a run time error and said to  make the same type of constructor in teacher class

```java
//Teacher class constructor
public Teacher(String name) {
        super(name);
    }
```

### super keyword simplified version

```java
package Inheritance;

class A{
    public A(){	//1st constructor of A
        System.out.println("in A");
    }
    public A(int i){	//2nd Constructor of B
        System.out.println("int in A");
    }
}

class B extends A{
    public B(){
        super();		//There's always a super() in every child constructor by default...That's why whenever we 					//make a object of a child class the constructor of parent class automatically gets called.
        System.out.println("in B");
    }
    public B(int i){
        super(i);		//But when we need to call the 2nd Constructor A which have a parameter then we need to 
        				//write the super keyword and pass the argument in it.
        System.out.println("int in B");		
    }
}

public class SuperKeyword {
    public static void main (String...args){
        B b = new B(2);
    }
}
```

**Basically we can use super() as a parent class object.**

**Note - JAVA Do not support multiple inheritance i.e. a single child class cannot have more than one parent...as it may pose the threat of Diamond problem(which is that the child class can't choose which parent to choose when calling a method with same name).**

Read about Singleton Pattern later.



# Polymorphism (more than one form)

The word polymorphism means having many forms. 

The word “poly” means many and “morphs” means forms, So it means many forms.

**Real life example of polymorphism:** A person at the same time can have different characteristic. Like a man at the same time is a father, a husband, an employee. So the same person posses different behavior in different situations. This is called polymorphism.

**In Java polymorphism is mainly divided into two types:**

- Compile time 
- Run time

### Compile Time Polymorphism -

- It is also known as static polymorphism. 
- This type of polymorphism is achieved by **function overloading** or operator overloading.

### Run time Polymorphism - 

- It is also known as Dynamic Polymorphism(Method Dispatch). 
- It is a process in which a function call to the overridden method is resolved at Runtime. This type of polymorphism is achieved by **Method Overriding.**





## toString(); method 

- **Object class is a parent to every class in java either directly or indirectly.** The Object class contains toString method.

- Whenever we create a class object and try to print the object the toString() method will get invoked and...we will get something like ClassName@1b6d3586.

- We print something like this because the default method of toString in Object class is like this...

  ```java
  public String toString() {		//default toString method in Object class
          return getClass().getName() + "@" + Integer.toHexString(hashCode());
      }
  ```

- But, we can override this method in our class...Like this...

  ```java
  class Vikas{
  
      int age;
      String name;
  
      Vikas(int age, String name){		//Constructor
          this.age = age;
          this.name = name;
      }
  	
      @Override
      public String toString(){		//Overriding the default Object class toString method
        return   age+" " + name;
      }
  }
  ```

  Printing the Object

  ```java
  public class MainClass {
  
      public static void main(String...args){
          Vikas v = new Vikas(19, "Vikas");
          System.out.println(v);	
      }
  }
  //OutPut
  19 Vikas
  ```





## instanceof keyword

- The instanceof keyword is used before doing Object casting as it would help us to tell whether we Could do the type casting or not.

- printing instanceof keyword will give use a boolean value.

- For eg...

  ```java
  // Java program to demonstrate working of instanceof 
  
  // Creating sample classes with parent Child 
  // relationship 
  class Parent { } 
  class Child extends Parent { } 
  
  class Test 
  { 
  	public static void main(String[] args) 
  	{ 
  		Child cobj = new Child(); 
  
  		// A simple case 
  		if (cobj instanceof Child) 
  		System.out.println("cobj is instance of Child"); 
  		else
  		System.out.println("cobj is NOT instance of Child"); 
  
  		// instanceof returns true for Parent class also 
  		if (cobj instanceof Parent) 
  		System.out.println("cobj is instance of Parent"); 
  		else
  		System.out.println("cobj is NOT instance of Parent"); 
  
  		// instanceof returns true for all ancestors (Note : Object 
  		// is ancestor of all classes in Java) 
  		if (cobj instanceof Object) 
  		System.out.println("cobj is instance of Object"); 
  		else
  		System.out.println("cobj is NOT instance of Object");		 
  	} 
  } 
  //OutPut
  cobj is instance of Child
  cobj is instance of Parent
  cobj is instance of Object
  ```

  **A parent object is not an instance of Child**

  ```java
  // A Java program to show that a parent object is 
  // not an instance of Child 
  
  class Parent { } 
  class Child extends Parent { } 
  
  class Test 
  { 
  	public static void main(String[] args) 
  	{ 
  		Parent pobj = new Parent(); 
  		if (pobj instanceof Child) 
  		System.out.println("pobj is instance of Child"); 
  		else
  		System.out.println("pobj is NOT instance of Child"); 
  	} 
  } 
  //OutPut
  pobj is NOT instance of Child
  ```

  



# Abstraction

- It's can be described as hiding certain details and showing only what's essential.
- For e.g. when we use a fridge ... the only thing we care about it as a user is that it will make things cold when we put something inside....we don't care what are the mechanics, laws and other things that made the fridge possible to cool things.
- Hiding what is not important is called Abstraction.
- It can be achieved by either classes or interfaces.

### Abstract Method 

- The abstract methods have no implementation only declaration.(i.e. no body only declaration).

- We declare a abstract method by using the abstract keywod.

- Since There is no body there will be no Curly braces...only () and semicolon ;

- ```java
  public abstract String method_name();
  access_modifier abstract return_type method_name();		//Standard abstract method
  ```

  

### Abstract class

- A class can be declared as Abstract using the abstract keyword.
- An Abstract class can have abstract methods (without body) and non-abstract regular methods(with body).
- A normal class (non-abstract class) cannot have abstract methods.
- It is not compulsory to have abstract methods in an abstract class...an abstract class can have zero abstract methods. But a abstract method should always be inside a abstract class.
- Abstract methods do not have curly braces.
- An abstract class cannot be initialized, which means **we cannot create objects of an abstract class.**
- **Abstract class must be extended.**
- **Methods of abstract class must be overridden by child classes.**  
- If all abstract methods of Parent class are not implemented in child class then we have to make the child class as abstract and then make the next level child class where all methods of the parent class are implemented.

### Abstraction vs Encapsulation

| Abstraction                                                  | Encapsulation                                                |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| It's about hiding unwanted details and showing only the most essential information. | It's about hiding the Information and mechanics of something for security reasons. |
| Abstraction focuses on what the information of what the object should contain | Encapsulation is for binding code and data into a single unit. |
| Abstraction solves issues at design level                    | Encapsulation solves issues at implementation level.         |

for Eg...

```java
// Java program to illustrate the 
// concept of Abstraction 
abstract class Shape 
{ 
	String color; 
	
	// these are abstract methods 
	abstract double area(); 
	public abstract String toString(); 	//Abstract methods do not have curly braces.
	
	// abstract class can have constructor 
	public Shape(String color) { 
		System.out.println("Shape constructor called"); 
		this.color = color; 
	} 
	
	// this is a concrete method 
	public String getColor() { 
		return color; 
	} 
} 
class Circle extends Shape 
{ 
	double radius; 
	
	public Circle(String color,double radius) { 

		// calling Shape constructor 
		super(color); 
		System.out.println("Circle constructor called"); 
		this.radius = radius; 
	} 

	@Override
	double area() { 
		return Math.PI * Math.pow(radius, 2); 
	} 

	@Override
	public String toString() { 
		return "Circle color is " + super.color + 
					"and area is : " + area(); 
	} 
	
} 
class Rectangle extends Shape{ 

	double length; 
	double width; 
	
	public Rectangle(String color,double length,double width) { 
		// calling Shape constructor 
		super(color); 
		System.out.println("Rectangle constructor called"); 
		this.length = length; 
		this.width = width; 
	} 
	
	@Override
	double area() { 
		return length*width; 
	} 

	@Override
	public String toString() { 
		return "Rectangle color is " + super.color + 
						"and area is : " + area(); 
	} 

} 
public class Test 
{ 
	public static void main(String[] args) 
	{ 
		Shape s1 = new Circle("Red", 2.2); 
		Shape s2 = new Rectangle("Yellow", 2, 4); 
		
		System.out.println(s1.toString()); 
		System.out.println(s2.toString()); 
	} 
} 
//OutPut
Shape constructor called
Circle constructor called
Shape constructor called
Rectangle constructor called
Circle color is Redand area is : 15.205308443374602
Rectangle color is Yellowand area is : 8.0
```



## Inheritance and constructors

- In Java, constructor of base class with no argument gets automatically called in derived class constructor.

  ```java
  // filename: Main.java 
  class Base { 
  Base() { 
  	System.out.println("Base Class Constructor Called "); 
  } 
  } 
  
  class Derived extends Base { 
  Derived() { 		//Here while calling this constructor(i.e. making a object of this class) the constructor 						//of the parent class automatically gets called
  	System.out.println("Derived Class Constructor Called "); 
  } 
  } 
  
  public class Main { 
  public static void main(String[] args) { 
  	Derived d = new Derived(); 
  } 
  } 
  //OutPut
  Base Class Constructor Called
  Derived Class Constructor Called
  ```

  But, if we want to call parameterized constructor of base class, then we can call it using super(). The point to note is **base class constructor call must be the first line in derived class constructor**. For example, in the following program, super(_x) is first line derived class constructor.

  ```java
  // filename: Main.java 
  class Base { 
  int x; 
  Base(int _x) { 
  	x = _x; 
  } 
  } 
  
  class Derived extends Base { 
  int y; 
  Derived(int _x, int _y) { 
  	super(_x); 
  	y = _y; 
  } 
  void Display() { 
  	System.out.println("x = "+x+", y = "+y); 
  } 
  } 
  
  public class Main { 
  public static void main(String[] args) { 
  	Derived d = new Derived(10, 20); 
  	d.Display(); 
  } 
  } 
  //Output
  x = 10, y = 20
  ```



## Final Keyword

You can assign final keyword to methods, variables and clasees

- A final variable value cannot be changed
- A final method cannot be overriden
- A final class cannot have anymore children....(It cannot be extended).

Final Variables

```java
final String bro = "asddsa";		//Decalaration and assignment of a final String variable
```

If you didn't assign a final variable anything ... and left it blank .... you can initialize it only inside a block( normal curly braces like this {} ) or inside a Constructor.

```java
final String name;		//Blank final variable
    
    //A normal block
    {
        name = "asd";	
    }
    //Constructor
    public Student(){
        name = "ad";
    }
```

You Can write a final method like this, so it can't be overridden in another child class.

```java
public final void getData(){
        System.out.println("You're right!");
    }
```

Declaring a class with final keyword ... so that it can't be extended. (So that it can't have a child class.)

```java
public final class Student {
}
```

 

# Interfaces

- In Java, there is no support for multiple inheritance(like one child having multiple parents). But we can achieve this behavior  by using Interface.

- We can create an interface by simply using the interface keyword instead of using class.

  ```java
  public interface Football{
  }
  ```

- Interfaces specify what a class must do and not how. It is the blueprint of the class.

- So it specifies a set of methods that the class has to implement.

- A class implements an interface.

- To implement an interface we use keyword: **implements**

  ```java
  public class Person implements Football, Student{	//A class can implement more than one interface
  }
  ```

- It is used to provide **total abstraction**. That means all the methods in an interface are declared with an empty body(by default they are abstract and public as the subclasses will provide them implementation).

-  All attributes of a interface are public, final, and static..so we don't need to provide the access modifiers....but if we do then compiler doesn't complain about it either.

- **If a class doesn't Override(implements) all methods of an interface then it must be a abstract class.**

- You cannot make objects of interface(or instantiate it)...as it is kind of a pure abstract class form.

**Why do we use interface ?**

- It is used to achieve total abstraction.
- Since java does not support multiple inheritance in case of class, but by using interface it can achieve multiple inheritance .
- Interfaces are used to implement abstraction.

### Why use interfaces when we have abstract classes?

- The reason is, abstract classes may contain non-final variables, whereas variables in interface are final, public and static.

- **Interface can extend more that one interface.** But it can't extend another class.

- ```java
  public interface Youtuber extends as,df{ }	//Where as and df are other interfaces
  ```

  

- **A class can implement more than one interface.** 

- ```java
  public class Person implements Youtuber,Student { }		//Where Youtuber and Student are interfaces
  ```

  

### Example of interface 

Interface 1 (Youtuber)

```java
public interface Youtuber {
    void uploadVid();
    default void edit(){
        System.out.println("youtuber editing videos.");
    }
}
```

Interface 2 (Student)   

```java
public interface Student {
    void study();  
    default void exams(){
        System.out.println("Student is giving exam.");
    }  
}
```

Main Class  

```java
package Interfaces;
 
public class Person implements Youtuber,Student {
    public static void main(String...args) {
        Person p = new Person();

        Youtuber y = p;     //Upcasting so y object have access to methods of Youtuber interface but this
        Student s = p;      //an object of Person class. Just making references of Youtuber and Student

        p.uploadVid();
        p.study();

        y.edit();
        s.exams();
    }

    @Override
    public void uploadVid(){
        System.out.println("Person is gonna upload videos.");
    }

    @Override
    public void study(){
        System.out.println("Person is gonna study.");
    }
}
//Output
Person is gonna upload videos.
Person is gonna study.
youtuber editing videos.
Student is giving exam.
```



### Changes from JDK 1.8 onwards

- We can have some bodies of method by using a keyword **default.**
- We don't have to necessarily override them (Same as in abstract classes we don't we to override the concrete methods/non-abstract methods).
- But this may create a chance of posing a diamond problem.

```java
public interface Student {
    default void uploadVid(){		//A method in interface having a body using the default keyword
        System.out.println("Uploading videos student");
    } 
} 
```

- For eg. the **Diamond problem** in java :

  - Multiple Inheritance is a feature of object oriented concept, where a class can inherit properties of more than one parent class. The problem occurs when there exist methods with same signature in both the super classes and subclass. On calling the method, the compiler cannot determine which class method to be called and even on calling which class method gets the priority.

  for eg...

  ```java
  // First Parent class 
  class Parent1 
  { 
  	void fun() 
  	{ 
  		System.out.println("Parent1"); 
  	} 
  } 
  
  // Second Parent Class 
  class Parent2 
  { 
  	void fun() 
  	{ 
  		System.out.println("Parent2"); 
  	} 
  } 
  
  // Error : Test is inheriting from multiple 
  // classes 
  class Test extends Parent1, Parent2 
  { 
  public static void main(String args[]) 
  { 
  	Test t = new Test(); 
  	t.fun(); 
  } 
  } 
  ```

  

