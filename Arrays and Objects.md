# Arrays

## The Structure of array

- An array is a finite sequence of elements of some common data type, where an element of an array can be accessed by combing the name given to the array and the position of the element in the sequence, called index.

- This how you **make an array**

  ```java
  int [] myIntegers;
  int [] myString;
  ```

- You can specify **how many elements** are there in your array..by doing this

  ```java
  myIntegers = new int [10];
  myString = new String[19];
  ```

- You can know what is **length of your array** i.e. how many elements are there in your array.

  ```java
  System.out.println(myIntegers.length);
  System.out.println(myString.length);
  //OutPut
  10
  19
  ```

- You can directly put values in an array like this

  ```java
  int [] marks = {30, 40, 60 ,80};
  ```

- You can change the value of a specific position by

  ```java
  marks[2] = 50;		//the value of index 2 in marks array is changed from 60 to 50
  ```

- You can also print a specific location value by doing this-

  ```java
  double [] marks = {3.1, 4.7, 9.3};
  marks[1]=2.4;
  System.out.print(marks[1]);
  ```

- To print the whole array we use loops

  ```java
  for (int i =0; i<marks.length; i++){		//The marks.length specifies the length of the array
              System.out.println(marks[i]);
          }
  ```

- A program to print average.

  ```java
  System.out.print("Enter how many students you have=");
          int n = sc.nextInt();
          int [] marks = new int[n];
          int total=0;
          for(int i=0; i<marks.length; i++){
              System.out.print("Enter marks of your Student=");
              marks[i]=sc.nextInt();
              total+=marks[i];
          }
          double x=total/n;	
          System.out.println("Average="+x);
  ```


### Using of Multiple arrays

- ```java
  //Input names and scores then ask the lower and upper limit you wanna print the names and scores. 
  int num;
          System.out.print("Enter number of people=");
          num = sc.nextInt();
          String [] names = new String[num];
          double [] scores = new double[num];
          boolean [] flag = new boolean[num];
  
          for(int i = 0; i<num; i++){
              System.out.printf("Enter name %d=",i);
              sc.nextLine();
              names[i]=sc.nextLine();
              System.out.printf("score of the person %d=",i);
              scores[i]=sc.nextDouble();
          }
          String ans;
          do
          {
              double upper, lower;
              System.out.print("Enter the lower and upper limits=");
              lower = sc.nextDouble();
              upper = sc.nextDouble();
  
  
              for (int j = 0; j < num; j++) {
                  if (scores[j] >= lower && scores[j] < upper) {
                      System.out.printf("Name = %s, Score = %f%n", names[j], scores[j]);
                  }
              }
              System.out.print("Continue(y/n)");
              ans = sc.next();		//Here it'll wait for the input if y is entered then it'll 													//continue...otherwise end operation.
  
           }while(ans.startsWith("y"));		
  ```

  

## The Class Arrays and Resizing Arrays

### The Class Arrays

Arrays is a class that provides static methods for manipulating and examining arrays. The class Arrays belongs to the package java.util, so the class must be imported.

```java
import java.util.Arrays;		//OR
import java.util.*;
```

​		Let T be any Data type

- **boolean** Arrays.equals( T[ ] x, T[ ] y ) 

  This method returns a boolean value representing whether or not the two arrays x and y have the same lengths, and the elements are equal between x and y at all positions.

- **void** Arrays.fill( T[] x, T v ) 

  This method fills the array x with the value v.

- **void** Arrays.fill( T[] x, int fromIndex, int toIndex, T v )

  The method stores v in the elements x[ fromIndex ], ..., x[ toIndex - 1].

- **void** Arrays.sort( T[] x )

  This method rearranges the elements of x in increasing order. If T is a primitive data type.

- **void** Arrays.sort( T[] x, int fromIndex, int toIndex )

  This is a variant of sort. Sorting is applied only on the elements having indexes between fromIndex and toIndex - 1.

### Do the arrays(Chapter 13) part again for better understanding  of data structures and algorithms.

## 

## Multidimensional Arrays

There can be 2D, 3D arrays too. Till now only 1D were there.

- We can define 2D arrays by ...

  ```java
   int [][] a = new int[4][3];	//we made a 2D array of 4 rows and 3 columns..think of it as a matrix 
  							  //Total 4*3 12 elements
   System.out.print(a[1][2]);		//we accessed the 2nd row and 3rd column element 
  ```

- We can print 2D array by...

  ```java
  //printing 2D arrays
  
          int [][] b = {
                  {2,3,4,5},
                  {5,7,8,9,95,2},
                  {45,67,23,54}
          };
          for(int i = 0; i<b.length; i++){
              for(int j = 0; j<b[i].length; j++){
                  System.out.print(b[i][j]+" ");
              }
              System.out.println();
          }
          System.out.println("2nd row 3rd column="+b[1][2]);
  //OutPut
  2 3 4 5 
  5 7 8 9 95 2 
  45 67 23 54 
  2nd row 3rd column=8
  ```

- 3D arrays are defined

  ```java
  int [][][] a = new int [x][y][z];	//here 3D array is initialized with x*y*z elements.
  System.out.print(a[x2][y3][z2]);	//accessing the element in 3D array
  ```

- Printing 3D array

  ```java
  int [][][] a = new int[4][4][4];    //we created a 3D array of 64 elements
          for(int i =0; i<4; i++){
              for(int j=0; j<4; j++){
                  for(int k=0; k<4; k++){
                      System.out.print(a[i][j][k]+" ");
                  }
                  System.out.println();
              }
              System.out.println();
          }
  //Output 
  will print 64 zeroes
  ```

### Jagged Arrays

- We use Jagged arrays when number of Rows are defined but no. of Columns are not....eg.

  ```java
  int [][] a = new int [3][];     //here we define only no.of Rows but leave no. of columns
  
          a[0]= new int[3];       //here we define no. of columns for row 1
          a[1]= new int[2];       //here we define no. of columns for row 2
          a[2]= new int[4];       //here we define no. of columns for row 3
  ```

  

### Enhanced For Loops

- Enhanced For Loops are mostly used with arrays or collections and will be used only when required to print the whole array.

- ```java
  int a []={1,2,3,4,5};
          for(int j : a){		
              System.out.print(j);	//Note that here the values are j not the index.
          }
  //Output
  12345
  ```

### Bubble Sort

- Most easy way of sorting an array.

- And, the most inefficient way.

- It's just checking if the array element after the position i is greater than position i+1. If a[i] > a[i+1] then the positions of those elements are swapped.

  ```java
          //Bubble Sort
  
          int [] a = {7,9,5,4,3,2,1};
          int n = a.length;	//If there are n elements then sorting will be done in n-1 iterations
          for(int i = 0; i<n-1; i++){
              for ( int j=0; j<n-1; j++){		//we can also do iteration till n-1-i here for optimization
                  if(a[j]>a[j+1]){
                      int x = a[j+1];
                      a[j+1]=a[j];
                      a[j]=x;
                  }
              }
          }
  
          for(int k : a){     //for each loop
              System.out.print(k+" ");
          }
  //Output
  1 2 3 4 5 6 7 
  ```

  ```java
  //Optimzed Bubble sort
  
  int [] a = {7,9,5,4,3,2,1};
          int n = a.length;           //If there are n elements then sorting will be done in n-1 iterations
          for(int i = 0; i<n-1; i++){
              boolean sorted = true;		//Boolean element for checking if sorting is done or or not
              for ( int j=0; j<n-1-i; j++){
                  if(a[j]>a[j+1]){
                      int x = a[j+1];
                      a[j+1]=a[j];
                      a[j]=x;
                      sorted = false;     //Continue iteration even if 1 element is swaped
                  }
                  if(sorted) break;		//If sorted come out of the loop.
              }
          }
  
          for(int k : a){     //for each loop
              System.out.print(k+" ");
          }
  //Output
  7 9 5 4 3 2 1 
  ```

- Just the same bubble sort in python

  ```python
  a = [7,2,3,4,9,1,3,20]
  
  x=len(a)
  
  for i in range(x-1):
      for j in range(x-1):
          if(a[j]>a[j+1]):
              y = a[j]
              a[j]=a[j+1]
              a[j+1]=y
  print(a)
  ```


### Selection Sorting

- Here, we first search for the lowest number in the array.

- Then, we make the lowest value come to forward position.

  ```java
  //Best Method
  
  int [] a = {2,5,1,6,-1,0,3,6,8,-4,-1,23,765,-7,34,0,23};
          int n = a.length;
  
          for( int i = 0; i<n; i++){
              int minInd=i;
              for(int j=0; j<n; j++){
                  if( a[j]>a[minInd]){
                      int temp = a[j];
                      a[j] = a[minInd];
                      a[minInd] = temp;
                  }
              }
          }
          for( int e : a){
              System.out.print(e+" ");
          }
  //OutPut
  -7 -4 -1 -1 0 0 1 2 3 5 6 6 8 23 23 34 765 
  ```

  ```java
  //2nd Method
  
  int [] a = {2,5,1,6,-1,0};
          int n = a.length;
  
          for(int i = 0; i<n-1; i++){
              int minInd = i;
              for(int j = i; j<n; j++){
                  if(a[j]<a[minInd]){
                      minInd = j;
                  }
              }
              int temp = a[i];
              a[i] = a[minInd];	//Here If the value minInd = j then only this will work otherwise i=j
              a[minInd] = temp;
          }
  
          for(int e: a){
              System.out.print(e+" ");
          }
  ```

  Note - **Do String Anagram again**(HackerRank and all for practice)

  

  ## Class File 

  - Import java.io.File;
  - Make a new object of File class.
  - Specify the directory.

  ```java
  import java.io.File;		//You have to import this
  
  public class FileHandling {					
      public static void main (String...args){	//Below make a new object f1 for class File
          File f1 = new File("C:/Users/Vikas/IdeaProjects\\Arrays and objects\\src");	//Can Use "/" OR "\\" for 																				//navigation.
          boolean x = f1.canRead();	//use method/properties of class File using the object.
          							//Many methods available like canWrite, isFile, isDirectory, exists etc.
          System.out.print(x);
      }
  }
  //OutPut
  true
  ```

  *More File methods are at page 372 Of the Book also a screenShot is there in the java Fundamentals folder.*

  

  

  # Exception Handling

  There are two ways to handle an error...Throwing error, Catch method.

  ####  Error Handling Imposed by the Compiler

  - A throws declaration is a declaration attached to the header of a method. It formally associates a runtime error type with the method.

  - For an error type E, the declaration takes the form of throws E and appears immediately after the closing parenthesis of the parameter declaration in the method header.

  - If an error of type E occurs during the execution of its code, M reports the error back to its direct superior. If the present execution of M is due to a method call to M appearing in another method Q, then the superior is Q. If there is no such Q, M must be the method main of some program, so the superior is JVM. In the latter case, JVM terminates the program after reporting the error on the screen.

    *Screen Shot the flow chart of error handling is there in Java fundamentals folder.*

  - A method cannot have more than one throws declaration. This limitation creates an issue when a method makes calls to multiple methods and they have different error types in their throws declarations

  - For this Java have a Tree like Structure for errors, so for any error a common ancestor(or Root Error) can be used in the **throws** declaration.

  - For eg. Exception is the error type at the root of the tree, so in a situation where different run-time errors need to be handled, Exception can be used.

  #### “Catching” a Run-Time Error
  
  - The other way to handle a formally declared run-time errors is to “catch” the error.
  
    ```java
    try{
    ... N(...)
    }
  catch(E e){	//As soon as the error occurrs an exception object is created here the object is e.
    ...
    }
    ```
  
  - Multiple catch clauses can be attached to one try block, if none of the error types appearing in the multiple catch clauses are ancestors of another.

**The difference between throwing and catching is that the former immediately terminates the execution of the method while the latter does not.**

**Regardless of which approach is used to handle IOException, the class IOException needs to be imported. IOException is in the java.io package.**

### A Demonstration of  Try-Catch



```java
public static void main(String... args) {
Scanner sc = new Scanner(System.in);

        //A Demonstration of Try-Catch
        String a, b;
        System.out.print("Enter the 1st file path=");
        a = sc.nextLine();
        System.out.print("Enter the 2nd file path=");
        b = sc.nextLine();

    //The method call should be encased in try and catch.
        try {
            File f = new File(a);	//New File Objects f,b
            File g = new File(b);
            creationPlay(f, g);		//Calls the method creationPlay with parameters f,g 
            System.out.println("Operations completed without errors");

        } catch (IOException e) {	//The catch should contain type IOException
            e.printStackTrace();	//This presents the chain of method calls that has led to the run-time error. 
            System.out.println("---Program terminated ---");
        }


    }

    public static void showExistance(File f, File g) {
        boolean x = f.exists();
        boolean y = g.exists();
        System.out.printf("%s=%s, %s=%s%n", f, x, g, y);	//prints true or false
    }

    public static void creationPlay(File f, File g) throws IOException {

        System.out.print(" " + f.getCanonicalPath());
        System.out.print(" " + g.getCanonicalPath());

        showExistance(f, g);

        boolean x2 = f.createNewFile();
        boolean y2 = g.createNewFile();

        showExistance(f, g);

        boolean x3 = f.renameTo(f);

        showExistance(f, g);

        boolean x4 = f.renameTo(f);
        boolean y4 = g.renameTo(g);

        showExistance(f,g);

        boolean x5 = f.mkdir();
        boolean y5 = g.mkdir();

        showExistance(f,g);

        boolean x6 = f.mkdir();
        boolean y6 = g.mkdir();
        showExistance(f,g);

    }
```

### The Finally Block in try catch.

```java
try{
            int i=10,j=2;
            int x = i/j;
            System.out.println(x);
        }catch( Exception e){	

            System.err.println("ERROR!!!");   //We can type err instead of out to get red color
        }
        finally{	//This block executes regardless of an exception
            System.out.println("BYE!!!");
        }
```

```java
try{
            int []a = new int[3];
            a[4] = 34;
            int i=10,j=2;
            int x = i/j;
            System.out.println(x);
        }catch( ArithmeticException e){

            System.err.println("ERROR!!!");   //We can type err instead of out to get red color
        }
        catch( Exception e){        //You cannot put this catch before ArithmeticException, since this ArithmeticException is a descendant of this Exception
            System.out.println(e);      //This way you can view which type of exception has occurred
        }
        finally{
            System.out.println("BYE!!!");
        }
```

The logic to find an exception handler is : 

- If the exception is found at a function C then it'll check if the exception is handled there or or the previous called method...like if A calls B and B calls C then exception handler will try to catch C then B then A for catching the error....for eg.

- ```java
  public void A(){
  	B();
  }
  public void B(){
  	C();
  }
  public void C(){
  	//Exception occurrs then it'll 1st check C for try-catch block then B then A
  }
  ```

## throw Keyword

This **throw** keyword in the cases where the  program is gonna definitely gonna crash...we don't use it much, but circumstances are unavoidable then we use this keyword.

For Eg...

```java
public static void f1(){
	boolean isDanger = true;

        if(isDanger){
            throw new ArrayIndexOutOfBoundsException("ERROR!!!!!!");    //Here new Object of Exception is created
        }
}

public static void main(String...args){
    f1();
}
//OutPut
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: ERROR!!!!!!
	at ExceptionPacakage.Exception.f1(Exception.java:26)
	at ExceptionPacakage.Exception.main(Exception.java:12)
```

 

## throws keyword 

**throws** keyword is written in the signature of a method .... if we know the particular method is gonna throw an exception then we handle the exception in the caller method by using the try-catch block.

For Eg....

```java
public class Exception {
    public static void main(String...args){
        f1();
    }

    public static void f1()
    {
        try
        {
            f2();
        }catch(ArrayIndexOutOfBoundsException e){
            System.out.println(e.getMessage()+" occurred");
        }

    }
    public static void f2() throws ArrayIndexOutOfBoundsException{
        boolean isDanger = true;
        if(isDanger){
            throw new ArrayIndexOutOfBoundsException("ERROR!!!!!!");    
        }
    }
}
//OutPut
ERROR!!!!!! occurred
```



## File Handling

- In Java you can create file.
- Then get the information about the file (like size of file in bytes).
- Can Write inside the file.
- Can read what's in the file.

### Creating a File

```java
//Creating a File
        try{
            File f = new File("C:\\Softwares\\NEWfile.txt");    //Creates a new file of name NEWfile.txt
            if(f.createNewFile()){      //IF it's created then...
                System.out.print("Created = "+f.getName());     //prints the name of the file which is NEWfile.txt

            }else{
                System.out.print("It already exists");      //If executing the code 2nd time or file already exists
            }
        }catch(IOException e){
            System.out.println("ERROR!!!");
            e.printStackTrace();
        }
//OutPut

```

### File Information

```java
//File Information

        File f = new File("C:\\Softwares\\NEWfile.txt");
        if(f.exists()){
            System.out.println("File name:"+f.getName());
            System.out.println("Absolute Path:"+f.getAbsolutePath());
            System.out.println("Writable:"+f.canWrite());
            System.out.println("Readable:"+f.canRead());
            System.out.println("File size in bytes:"+f.length());
        }else{
            System.out.print("The File doesn't exist");
        }

//OutPut
Absolute Path:C:\Softwares\NEWfile.txt
Writable:true
Readable:true
File size in bytes:0
```

### Writing To Files

We gotta use the FileWriter Class for wirting in files.

```java
try{
            FileWriter writeThis = new FileWriter("C:\\Softwares\\NEWfile.txt");
            writeThis.write("0123456789");	//Writes this text inside the file
            writeThis.close();		
            System.out.println("YES!!!");
            File abc = new File("C:\\Softwares\\NEWfile.txt");
            System.out.println(abc.length());   //Outputs the size file

        }catch( IOException e ){
            System.out.println(e);
    		e.printStackTrace();
        }
```

### Reading From Files

to read from files we gotta use the Scanner method.

```java
//Reading From Files

        try {
            File f = new File("C:\\Softwares\\NEWfile.txt");
            Scanner reader = new Scanner(f);
            while(reader.hasNextLine()){	//Will run this code till it have string data
                String x = reader.nextLine();
                System.out.print(x);
            }
        }catch(Exception e ){
            e.printStackTrace();
        }
```

## Design Object Classes

- Instance variable are those variables which are written as global variable in Object class(classes other than main classes).