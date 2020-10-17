# JAVA Basics

## Data Types



1.Formally, the range of lines in which a variable declaration is valid is called the scope of the variable.

2.For printing decimal number we can use either "float" or "double" keywords

​		Eg. 	float x=4.4**F**;

​				   double=4.4;  

//We can use float and double keywords in the above format

3.For printing very large integer values we use "long" keyword in the below format:

​		long=123431497343649**L**;

4.The Remainder Operator **%** gives us the remainder for eg.

​		double w=10%3;

​		//OUTPUT = 1

5.Dividiing two numbers:

​		we use the **/** operator.

​		is our answer is in decimal the we use float....using double or int will not give numbers after decimals 

​		for Eg.

​		float w=12/123F;

​		//ouptut=0.09756

​		//but using int or double ...

​		double w=12/123;

​		//output=0.0

Moving a constant outside the method, thereby changing it from a local constant to a global constant.

******Note that the static attribute must be attached to the declaration.**

we have to declare the type of variable only one time .....if we change the value of the variable without changing it's 

name we don't have specify the type of variable again.

for Eg.

double myWeight=123.45;

myWeight=234.56;

### Strings

1. String is an object type that encompasses a series of char data along with an int value representing the length of the series.

## Reading Keyboard Inputs & Methods

1. Source code library of JDK is a hierarchical (tree-like) structure. We call the top-level of the hierarchy the root. Underneath the root exists a number of projects. A project is a collection of packages, where a package is a collection of classes.

2. . Popular projects include java and javax. Popular packages in the project java are lang, io, and util. The standard Java package lang belongs to the project java.

3. The class Scanner enables reading data from the keyboard.

4. So, import ***java.util.Scanner;*** must be used for keyboard inputs

5. it means-- the class Scanner in package util in project java.

6. we can import multiple classes specifying each and every class like...

   - import java.util.Scanner;

   - import java.util.ArrayList; 

   - import java.util.LinkedList;

   - import java.io.File;

     **OR**

     *JUST* import java.util.*;

     The asterisk, meaning “everything”.

7. //Code for taking and printing something

```java
import java.util.Scanner;		//or just import everything by using java.util.*;
public class method{
	public static void main (String[]args){
	Scanner a=new Scanner(System.in);
	//for integer or float or double or boolean it's the same
	System.out.print("Enter your Integer=");
	int x=sc.nextInt();
```

​	

```java
//for String which is a non-primitive data type
System.out.print("Enter your String=");
String y=sc.nextLine();

System.out.println("Your Integer is="+x+"and your String is="+y);
}
}
```
8. //Code For procedural decomposition of methods

   ```java
   public class Rect{
       public static void main(String[]args){
           rect();
           rect();
       }
       public static void rect(){
           System.out.print("Hello!");
       }
   }
   //output it prints Hello! two times
   ```

9. //Example of an infinite loop using procedural decomposition

   ```java
   public class Main{
       public static void one(){
           System.out.println("one");
           two();
       }
       public static void two(){
           System.out.println("two");
           three();
       }
       public static void three(){
           System.out.println("Three");
           one();
       }
       public static void main(String[]args){
           one();
       }
   }
   
   
   
   ```

10. We can also Access Method of one class in another class.

    ```java
    public class Main{
        public static void one(){
            System.out.println("one");
        }
    }
    ```

    

```java
public class DataTypes {
    public static void main(String[]args){
            Main.one();
            System.out.println("Hello!");
        }
}
//Output is 
//one
//Hello!
```

11.//Methods that work with parameters.

```java
public static void had(String name){
    System.out.print("Hello my name is "+name);
}
public static main (String[]args){
    had("Vikas");
    had("Vivaan");
    //or
    //String name="Vikas1";
    //had(name);
}
//OUTPUT
//Hello my name is Vikas
```

12. Method Overloading

    Java permits multiple methods having the same names appear in the same code unit as long as their parameter type signatures are different. We call this method overloading.

    ```java
    public static void a(String data){
        System.out.print("My name is "+data);
    }
    public static void a(int data){
        System.out.print("My age is "+data);
    }
    public static void a(double data){
        System.out.print("My Height is "+data);
    }
    public static void main(String[]args){
        String name="Vikas";
        a(name);
        int age=19;
        a(age);
        double height=5.92;
        a(height);
        float myheight=12.112f;
        a(myheight);
    }
    //output
    My name is Vikas
    My age is 19
    My Height is 5.92
    My Height is 12.112000465393066
    ```

13.Returning a value from method

```java
import java.util.*;
 public class BmiCalc {
     public static final double BMI = 703.12;		//declaring global variables
     public static final int FEET_TO_INCHES=12;		
		
     	 public static double bmiFormula ( double weight, double height){
         return BMI * weight/(height * height);		//The BMI formula
     }
        public static double combineheight(double feet,double inches){
             return FEET_TO_INCHES*feet+inches;  	
        }
         public static void oneInter(){
             Scanner a=new Scanner(System.in);
             System.out.print("Enter height in feet=");
             double feet=a.nextDouble();
             System.out.print("Enter height in inches=");
             double inches=a.nextDouble();
             System.out.print("Enter weight=");
             double weight=a.nextDouble();

             double bmi1 = bmiFormula(weight,combineheight(feet,inches));  //calling method 																	//bmiFormula and combineheight
             System.out.println("BMI="+bmi1);									
}
        public static void main(String[]args){
             oneInter();
        }
}
```

## Class Math

1. There is only one Math method that takes no parameters: Math.random().

   ​	The method Math.random() returns under a uniform distribution a random double value between 0 and 1.

   ```java
       public static void main(String[]args){
            System.out.println("PI="+Math.PI);
            System.out.println("e="+Math.E);
            System.out.println("Random double value 1 between 0 & 1="+Math.random());
            System.out.println("Random double value 2 between 0 & 1="+Math.random());
        }
   }
   //ouput
   PI=3.141592653589793
   e=2.718281828459045
   Random double value 1 between 0 & 1=0.6188547395346707
   Random double value 2 between 0 & 1=0.9284124812744101
   ```

   

2. Math.round, there are two versions. The return type of Math.round that takes a double parameter is long, and the return type of Math.round that takes a float parameter is int.

3. For Math.abs, there are four versions. The types of their input parameters are double, float, long, and int. For each version of Math.abs, the return type is identical to the parameter type.

4. **Program that demonstrates the use of Math functions**

   ```java
   public static void a(String name,double real,double value){
            System.out.print("Math function is="+name);
            System.out.print("Input value="+real);
            System.out.print("result="+value);
        }
        public static void a(double real2,double value2){
            System.out.print("2nd Input value="+real2);
            System.out.print("result of pow="+value2);	//pow is (real2)^real
   	 }
        public static void main(String[]args){
            Scanner x=new Scanner(System.in);
            System.out.print("Enter a value=");
            double real=x.nextDouble();
            a("square root",real,Math.sqrt(real));	//Just doing a squareRoot
            System.out.print("Enter 2nd value=");
            double real2=x.nextDouble();
            a(real2,Math.pow(real,real2));	//pow a Math function that take two parameters in
        }
   //The code uses method overloading
   

   ```
   
   *Java has a convenient way of adjusting the numbers to appear on the screen: a special print command System.out.printf.*
   
   ```java
   int a=20;
   int b=21;
   System.out.printf("a=%d, b=%d%n",a,b);		//instead of %d we can also use %s
   										//%n is used to go to next line as to replace println
   //output
   a=20, b=21
   ```
   
    

## Condition and it's Evaluation(If & else)

- Conditional formula act as mathematical formulae  **!, ||, and && acting as -, +, and ***, respectively.

  ```java
   public static void main(String[]args){
       Scanner key=new Scanner(System.in);
       System.out.println("Enter from the below choices:");
       System.out.println("1,2,3,4");
       System.out.print("Enter your marks=");
     		 int marks=key.nextInt();
  	if (marks<0 || marks>100){
          System.out.println("your marks are invalid");
      }
      else if(marks>=75 && marks<=100){
          System.out.printf("You marks %d are excellent%n",marks);
      }
      else if(marks>=40 && marks<=75){
          System.out.println("your marks "+marks+" are not great"+" not terrible ");
      }
       else{
          System.out.printf("you have failed with marks %d miserably",marks);
      }
  }
  ```

- Ternary Operator [ **variable=condition ? If condition is true : else** ]

  ```java
  //finding greatest of 3 integers
  int marks1,marks2,marks3;
  marks1=10;
  marks2=20;
  marks3=30;
  //using ternary operator
  int result=marks1>marks2?marks1>marks3?marks1:marks3 : marks2>marks3?marks2:marks3;
      System.out.print("Greatest"+result);
  //below is the expansion of the above code
  
  if(marks1>marks2){
      if(marks1>marks3){
          result=marks1
      }else{
          result=marks3
      }
  }else{
      if(marks2>marks3){
          result=marks2
      }else{
          result=marks3
      }
  }
   System.out.print("Greatest"+result);
  ```

- **Switch Case:**

- ```java
  //Basic Layout
  variable=value'n'
      switch(variable){
              case value1:				//acts like if condition
              	//statement
              break;						//if value1 is satisfied it'll come out of loop
          	case value2:				//acts like else if or if condition	
              	//statement
              break;			
              .......
              .......
                  default:					//acts like else
              		//statement
      }
  ```

- ```java
  //for merging 2 cases...i.e. to print something same for two different values
  
  switch(variable){
          case value1:
      	case value2:
          	//statement
          break;
      	case value3:
          	//statement
          break;
      	default:
  }
  ```

- Calculator made using Switch case

- ```java
  public static void main(String[]args){
      Scanner key=new Scanner(System.in);
      
      System.out.print("Enter your num1=");
      double num1=key.nextInt();
           System.out.print("Enter your num2=");
      double num2=key.nextInt();
      
      System.out.println("What you wanna do?");		//next line of code is taking a string
      	key.nextLine();    //this is used as the scanner won't take a string after it has taken 								//two integers...if before taking intergers we take string 									//then we can directly simply do it
           String op=key.nextLine();
           double result=0;
      switch (op){
          case "*":
              result=num1*num2;
              break;
          case"+":
              result=num1+num2;
  			break;
          case  "/":
              result=num1/num2;
              break;
          case "-":
              result=num1-num2;
              break;
          default:
              System.out.print("out of scope");
           }
  	System.out.print("result is = "+result);
  }
  
  ```

  

## JAVA Methods

Methods from taking parameters to returning functions in JAVA

```java
public class HelloWorld{

     public static void main(String []args){
    
  
 int step1Result = add( 5, 9);
  
 int step2Result = multiply(step1Result, 5);
  
 double finalResult = step2Result / 3;
  
 System.out.print(finalResult);
  

     }
     
     public static int add(int n1, int n2){	//We gotta specify the data type we are returning in this case it's int
         return n1+n2;
     }
     public static int multiply( int a,int  b){
         return a*b;
     }
}
```

