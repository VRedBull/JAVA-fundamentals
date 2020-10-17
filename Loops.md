# Loops

- There are four types of loops in Java For, while, do-while, for-each

## For Loop

1. Example of For loop

   ```java
   public static void main(String[]args){
           int i;
           for (i=1; i<=10; i+=1){		//will execute hello() body 10 times 
               System.out.println("This round is "+i);		//will print value of i each time
               hello();
           }
       }
       public static void hello(){
           System.out.println("Hello");	//prints Hello 10 times
       }
   ```

2. The header part of a for-loop has three components with a semicolon in between: 

   The Header part of for loop takes the form of   **for(initialization; continuation condition; update)  {....}**

   • initialization

   • continuation (termination) condition

   • update

   ```java
   //Code For calculating the BMI
   public static final double BMI1=23.1231;
       public static void main(String[]args){
           int i;
           for (i=1;i<=2;i+=1){
               System.out.println("This round is "+i);
               oneInt();
           }
       }
       public static double BMI( double height, double weight){
           return BMI1*height*weight;
       }
       public static void oneInt(){
           double weight, height;
           Scanner sc=new Scanner(System.in);
           System.out.print("Enter weight=");
           weight = sc.nextDouble();
           System.out.print("Enter height=");
           height=sc.nextDouble();
           double bmi=BMI(height,weight);
           System.out.println("Your BMI is="+bmi);
       }
   ```

3. The initialization is an assignment to a variable (usually an integer), the termination condition is a comparison involving the variable, and the update is a modification to the variable. We call such a variable an iteration variable.

### Iteration with an Auxiliary Variable

1. Repetitions can be generated using an auxiliary variable.

2. ```java
   int i,a;
           for (i=0; i<=14; i++){
               a=i/3;
               System.out.println(a);
           }
   //Output  000111222333444
   ```

   

### Double for Loops

1. Looks kind of like a nested loop

   ​	

   ```java
   for(){						//External Loop
   		for(){				//Internal Loop
   			Loop Body..
   		}
   }
   ```

2. Example of a double or nested for loop

   ```java
   for (int x=1; x<=height; x++){
               width--;
               for(int y=width; y>=1; y--){
                   System.out.print("*");
               }
               System.out.println();
           }
   //OutPut
   *****
   ****
   ***
   **
   *
       //Upside Right Triangle
   int a=0;
           for(int x=1; x<=height; x++ ){
               for(int y=0; y<=width-(width-a); y++){
                   System.out.print("*");
               }
               System.out.println();
               a++;
          }
   //OutPut
   *
   **
   ***
   ****
   *****
   ******
   ```

   ### Fibonacci  Series

   ```java
   Scanner sc=new Scanner(System.in);
           System.out.print("Enter till what you wanna print your Fibbonaci Series=");
           int n=sc.nextInt();
           int a,b,c;
           a=1;
           b=1;
                                                     
           System.out.println(a);
           System.out.println(b);
           for(int x=1; x<=n; x++){
               c=a+b;
               System.out.println(c);
               a=b;
               b=c;
           }
   //Output    1 1 2 3 5 8 13 21 34 55 89 ......
   ```

   

   **For displaying an error use--**

   ```java
   throw new IllegalArgumentException("Type your error data in string...i.e....something is valid");
   ```

   **For getting a number between a & b use--**

   ```java
   int x = a + (int)(b*Math.random())
       //the (int)(b*Math.random()) will give a number that only occuring before the decimal point
       //like (int)(54*Math.random()) will give (if Math.random()=0.98) 52 even though 54*0.98=52.92 
   ```

   ### The Betting Game

   ```java
   int possession,betType,betAmount,number;
           Scanner sc=new Scanner(System.in);
           possession=50;
           for(int i=1; i<=10; i++){
           System.out.println("You are in round "+i);
           System.out.println("You have "+possession+" coins");
           System.out.print("Enter amount of coins you wanna bet=");
           betAmount=sc.nextInt();
           if(betAmount<1){
               betAmount=1;   //Since you cannot bet less than 1 coin
           }
           else if(betAmount>possession){
               betAmount=possession; //Since you cannot bet more than you have
           }
           System.out.println("Your bet amount is="+betAmount); 
           System.out.print("Enter type of bet you wanna place -1 for odd, 0 for even OR 1 to 6 for exact number=");
           betType=sc.nextInt();   //User enters the bet type -1 or 0...or the exact number
           number=1+(int)(6*Math.random()); //Random number genrated between 1 and 6
           if (betType==-1 && number%2==1 || betType==0 && number%2==0){  
               System.out.println("You won");
               possession+=betAmount; //the amount that you bet is given back to you
           }
           else if(betType==number){
               System.out.println("You won Big Time");
               possession+=betAmount*5; //the bet amount is given back to you increased by 5 times 		}
           else{
               System.out.println("you have lost");
               possession-=betAmount; //the bet amount is decreased from your possession
               if(possession==0){  //You lost all your coins
                   break;		//Terminates the whole for loop and Game is ended
               }
           }
           System.out.println("The Exact number was="+number);
           }
    //after 10 rounds (Outside of for loop)
               System.out.println("you ended up with "+possession+" coins");
   ```

   

   ###  The Statements continue and break

   - Two important statements that can be used in a for-loop body are **continue and break**.

     1. **The statement continue instructs the program to skip the remainder of the loop-body and move on to the next round of the loop.**

     2. **The statement break instructs the program to terminate the execution of the loop immediately, ignoring the remainder of the present round and all the remaining rounds.**

        *break statement is viewed in the betting game as well* 

     3. An example of this..

        ```java
        for (int i=1; i<=11; i++){
                    if(i%2==0){
                        continue;
                    }
                    if(i>10){
                        break;
                    }
                    System.out.println("Hello");
                }
        //OutPut 
        //Hello is printed 5 times only
        ```

   ## Formatted Printing Using printf

   - **IllegalFormatConversionException** error also occurs when the number of data supplied and the number of placeholders do not agree, as well as when a placeholder is incorrectly written

   - To include the percent character in a part that is not a placeholder, the **%%** is used via escaping.

     ```java
     System.out.printf("%%Hello");
         //output	%Hello
     ```

   - To specify a new line use **%n** at the end

     ```java
     System.out.printf("Hello %n");
     System.out.printf("World");
     	//output	Hello
     	//		    World
     ```

   - "%-10s" specifies that the String data must be printed in flush left using at least ten character spaces, and "%10.5s" specifies that only the first five characters must be printed in flush right using at least ten character spaces.

     ```java
     System.out.printf( "Message=%-10.5s-Mike", "Table tennis is fun!" );
     //output	Message=Table --Mike
     ```

   - %c is used to format a char data.

   - To print leading zeros

     ```java
int n = sc.nextInt();
     System.out.printf("%03d",n);
//Input			Output
     3				002
83				083
     ```

     
   
     ### Methods for obtaining Information on String data
     
     - **length()** returns the length of the given string as an Int.
     
     - **charAt()** receives an int value as a parameter, and returns the character of the String data at the character position represented by the parameter.
     
     - *In Java, a position count starts from 0, instead of from 1.*
     
     - The next following code gives the index at which the char is present
     
       ```java
       Scanner sc= new Scanner(System.in);
           System.out.print("Enter your String=");
           String st=sc.nextLine();
           int n=st.length();
           for(int i=0; i<=n-1; i++){	//here it's i<=n-1 OR i<n because java indexing starts from 0 so last 									//char is at n-1 position
               System.out.println("Character at="+i+" is\""+st.charAt(i)+"\"");
           }
       //OutPut 
       Enter your String=Hello
       Character at=0 is"H"
       Character at=1 is"e"
       Character at=2 is"l"
       Character at=3 is"l"
       Character at=4 is"o"
       ```
     
     ### String Comparison
     
     - String has two methods for content equality and content comparison.
      - Those are methods **equal**(return bool value) and **compareTo**(returns int value).


```java
    //for equals to method
   String s,t;
           s="Hello";
           t="Hello";
           boolean x;
           System.out.print(s.equals(t));
   //Will print a simple true or false .... in this case it's true.
  

   
   //for compareTo() method
   String s,t;
           s="Hello";
           t="Hello";
           boolean x;
           System.out.print(s.compareTo(t));
   //OutPut 0
   String s,t;
           s="Hello";
           t="Hello123"; //Note here s is a prefix of t
           boolean x;
           System.out.print(s.compareTo(t));
   //Output -3
   String s,t;
           s="Hello123";
           t="Hello";
           boolean x;
           System.out.print(s.compareTo(t));
   //Output  3
   
   
```


​       

- *s.compareTo( t ) + t.compareTo( s ) is equal to 0.*

### Prefix and Suffix tests

 - String offers prefix and suffix tests, called startsWith and endsWith.	(both returns a bool value)

```java
   //startsWith method is used to text a prefix
   String s,t;
   s="123Hello";
   t="123";
   System.out.print(s.startsWith(t));
   //Output in this case it will return true
   

   //endsWith method is used to text a suffix
   String s,t;
   s="Hello123";
   t="123";
   System.out.print(s.endsWith(t));
   //Output in this case it will return true
   
```

### Pattern in String

- Can use **lastIndexOf** and **indexOf** to check where the string is at position

- both methods take 2 parameters **lastIndexOf(string, position)** & **indexOf(string, position)**

- both methods return a int data

  ```java
  String s,t;
  s="Hello, World!";
  t="World";
  int x=s.indexOf(t);
  //OutPut
  6		//note that in java index position starts from 0
  
  ```

  

### String.format()

- We can use this method to mimic the action of printf and receive the result as a return value, instead of printing it on the screen. 

  ```java
  int a,b;
          a=10;
          b=20;
          String out = String.format("a=%d, b=%d",a,b);
          System.out.print(out);
  //Output	
  // a=10, b=20
  ```

### String Pool area and Heap area

1. There are two methods to create a String 

   - By Just assigning it in double quotes 

     ```java
     String a = "Vikas";		//Here only one copy of this string is made in String Pool
     ```

   - By making it an Object

     ```java
     String b = new String("Pradhan");  //by making an object we create two copies of this String
     								//One in String Pool and One in Heap area
     								//If we have already assigned a String by previous method then only one 
     								//Copy will be created in the Heap area.
     ```

   ***Strings are Immutable** But we can make them Mutable by using **StringBuilder** and **StringBuffer**.*

### StringBuffer & Strin**gBuilder**

- We **always prefer StringBuffer over StringBuilder**.	(Because StringBuilder isn't Syncronization safe)

- StringBuffer & StringBuilder are mostly the same except the above difference.

- StringBuffer can append, delete, trim, replace, insert, etc.

  ```java
  StringBuffer st = new StringBuffer("Hello, Vikas Pradhan.");
          st.delete(3,6);
          st.append("Vivaan");
          st.insert(4,"ABC");
          st.replace(6,9,"Red");
  		
  	    System.out.print(st);
  //OutPut	Hel ABRedkas Pradhan.Vivaan
  ```

*To represent a String we Use Double quotations "This is String.", but to represent a char we use single quotations 'A'.*

*We use nextLine() to Take an input as a String, we can also use next()....Only Difference that next() will only only Store the String Value till there is a Space.*

```java
Scanner sc = new Scanner(System.in);
        System.out.print("Enter Your Sentence=");
        String sentence = sc.nextLine();
        System.out.println("You entered line = "+sentence);

        System.out.print("Enter Your Sentence=");
        String word = sc.next();
        System.out.print("Your entered 1st word is="+word);

//OutPut
Enter Your Sentence=The Fox is Brown.
You entered line = The Fox is Brown.
Enter Your Sentence=The Fox is White
Your entered 1st word is=The
```



## While Loops and Do-While Loops

### While Loop

it Basically says that...Until the given condition holds true keep executing the code.

```java
while(condition){
statement
}
```

​			

An example of while loop can be

```java
int i=0;
while(i<=10){
	System.out.println(i);
    i++;
}
//OutPut
0 1 2 3 4 ......10
```

Converting Decimal Numbers to Binary using while loop

```java
int n=5;
StringBuffer binary = new StringBuffer();
while(n>0){
    int x = n%2;
    binary.append(x);
    n=n/2;
    }
System.out.print("Binary="+binary.reverse());		//we shall reverse the String
//OutPut
Binary=101
```

Adding digits in a number

```java
int n = 12345;
int x = 0;

while(n%10 != 0){		//Can also use while(n>0)
	int a=n/10;
    int b=n%10;
    x = x+b;
    n=a;
}
System.out.print("Your addition of digits is="+x);
//OutPut
Your addition of digits is=14
```

To check how many digits are there in a number we can use (int)(Math.log10() + 1);

```java
int n = 12345;
System.out.println("Number of digits = "+(int) (Math.log10(n)+1));
//OutPut
Number of digits = 5
```

Check if the number is Palindrome Number(eg. if num1=12321 then it's a palindrome since it's reverse number is also same.)

```java
System.out.print("Enter a palindrome number=");
        int n=sc.nextInt();
        int x=0;
        double y=(int)(Math.log10(n)+1)-1;
        while(n>0){
            int a = n/10;
            int b = n%10;
            x += b * Math.pow(10, y);
            n=a;
            y--;
        }
        System.out.println("The reverse of the number is="+x);
```



### Do-While Loop

Format of Do-While Loop

```java
do{
Statements;
}while(condition);
```

In do while the statement will executed at-least once....after that it checks the condition

Converting Decimal Numbers to Binary using do-while loop

```java
 System.out.print("Enter your number=");
    int n=sc.nextInt();
    StringBuffer binary = new StringBuffer();		//StringBuffer so we append and reverse the String
    do{
        int x = n%2;
        binary.append(x);
        n=n/2;
    }while(n>0);
    System.out.print("Binary="+binary.reverse());
```

### CTRL-D

CTRL-D can be used to terminate a infinite program that requires a user input to stop that code.

For eg. we write a code where the loop runs for infinitely until the user enters a negative number.

But by using while (sc.hasNext()) in this the loop is terminated when the user enters CTRL-D.

```java
  int total=0,count=0,input;
        System.out.print("Enter inputs. End with CTRL-D=");
        while(sc.hasNext()){
            input = sc.nextInt();
            total+=input;
            count++;
        }
        System.out.printf("%4d is Total and you entered %d times.",total,count);
```

