# Data Structures | Collection Framework



## Data Structures

- A **data structure** is a particular way of organizing data in a computer so that it can be used effectively.

## Collection Framework

- Collection framework is just a bunch of classes and interfaces that help in solving questions that apply data structures.
- The set of classes and interfaces follow a certain hierarchy by inheritance.

**Hierarchy of the collection framework.**          ( There are photos of this in Java fundamentals folder on desktop)

- **COLLECTION** (i)									(i - interface, c - class)

  - List(i)

    - ArrayList(c)
    - LinkedList(c)
    - Vector(c)
      - Stack(c)

  - Set(i)

    - Hashed Set(c)
    - Linked Hash Set(c)

    - Sorted set(i)
      - Tree Set(c)

  - Queue(i)

    - Priority Queue(c)
    - Deque(i)
      - Array Deque(c)

  - Iterable(i)

    - ListIterator



- **Map**(i)
  - Hash Table(c)
  - Sorted Map(i)
    - Navigable(i)
      - Tree Map(c)
  - Abstract Map(i)
    - Hash Map(c)
    - Enum Map(c)



**1. <u>Collection Interface</u>:** This interface implements the iterable interface and is implemented by all the classes in the collection framework. This interface contains all the basic methods which every collection has like adding the data into the collection, removing the data, clearing the data, etc. All these methods are implemented in this interface because these methods are implemented by all the classes irrespective of their style of implementation. And also, having these methods in this interface ensures that the names of the methods are universal for all the collections. Therefore, in short, we can say that this interface builds a foundation on which the collection classes are implemented.	

Java, doesn't provide direct implementation of the collection interface but provides implementation of it's sub-interfaces like, List, Queue and Set.

**Methods of Collection** - Some methods of Collection are add(), size(), remove(), iterator(), addAll(), removeAll() etc.

**Note** - All of the below interfaces extends the Collection interface.

**2. [List Interface:](https://www.geeksforgeeks.org/list-interface-java-examples/)** This is a child interface of the collection interface. This interface is dedicated to the data of the list type in which we can store all the **ordered collection** of the objects. This also allows duplicate data to be present in it. This list interface is implemented by various classes like [ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/), [Vector](https://www.geeksforgeeks.org/java-util-vector-class-java/), [Stack](https://www.geeksforgeeks.org/stack-class-in-java/), **<u>LinkedList</u>**.

**3. [Set Interface](https://www.geeksforgeeks.org/set-in-java/):** A set is an unordered collection of objects, it also provides mathematical set in Java. This collection is used when we wish to **avoid the duplication** of the objects and wish to store only the unique objects. This set interface is implemented by various classes like [HashSet](http://www.geeksforgeeks.org/hashset-in-java/), [TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/), [LinkedHashSet](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/), **<u>EnumSet</u>**.

**4. [Queue Interface](https://www.geeksforgeeks.org/queue-interface-java/):** As the name suggests, a queue interface maintains the **FIFO(First In First Out)** order similar to a real-world queue line. This interface is dedicated to storing all the elements where the order of the elements matter. For example, whenever we try to book a ticket, the tickets are sold at the first come first serve basis. Therefore, the person whose request arrives first into the queue gets the ticket. There are various classes like [PriorityQueue](https://www.geeksforgeeks.org/priority-queue-class-in-java-2/), [Deque](https://www.geeksforgeeks.org/deque-set-1-introduction-applications/), [ArrayDeque](https://www.geeksforgeeks.org/arraydeque-in-java/), etc.

**5. [Map Interface](https://www.geeksforgeeks.org/map-interface-java-examples/):** A map is a data structure which supports the **key-value pair** mapping for the data. This interface doesn’t support duplicate keys because the same key cannot have multiple mappings. A map is useful if there is a data and we wish to perform operations on the basis of the key. This map interface is implemented by various classes like [HashMap](http://www.geeksforgeeks.org/java-util-hashmap-in-java/), [TreeMap](https://www.geeksforgeeks.org/treemap-in-java/), [SortedMap](https://www.geeksforgeeks.org/sortedmap-java-examples/), **<u>LinkedHashMap, WeakHashMap, EnumMap</u>** .



## ArrayList

- ArrayList implements List and List extends Collection.
- **ArrayList are mainly used because it is resizable....unlike array the size changes as elements are added to it.**
- Also we can just print all the elements of the ArrayList without using a loop
- ArrayList is present in Java.util package.
- Unlike array, when elements are added and removed from it ...it automatically adjusts it self's size.
- Hence it is also known as dynamic arrays.
- ArrayList can not be used for primitive types, like int, char, etc. We need a wrapper class for such cases....we instead use (Integer for int)

Declaring an ArrayList with initial size of n

```java
        ArrayList<String> fruits = new ArrayList<String>(n);	//Note that specifying the size of arrayList is not 															//mandatory
```

We can also declare the same ArrayList as:

```java
        ArrayList<String> fruits = new ArrayList<>();
```

Since ArrayList implements List...we can use List as the reference type when we instantiate a ArrayList object.

```java
List<String> fruits = new ArrayList<>();
```



### Methods of ArrayList:

- add(element)	-	Adds elements to the ArrayList (similar to append in python)

  ```java
  public static void main(String[]args){
          ArrayList<String> fruits = new ArrayList<>();
  
          fruits.add("Paneer");
          fruits.add("Paratha");
          fruits.add("Mojito");
  
          System.out.println(fruits);
      }
  //Output
  [Paneer, Paratha, Mojito]
  ```

- add(index, element)    -    Adds elements to and we can specify in which index exactly we want to add the element to.

  ```java
  ArrayList<String> fruits = new ArrayList<>();
  
          fruits.add("Paneer");
          fruits.add("Paratha");
          fruits.add("Mojito");
          fruits.add(3,"Dahi");
          fruits.add(4,"Puri");
          fruits.add(5,"Chicken");
  
          System.out.println(fruits);
  ```

  Since ArrayList is a dynamic array when we add or remove a element from the array it auto adjusts the whole array accordingly by itself....for eg...

  ```java
  ArrayList<String> fruits = new ArrayList<>();
  
          fruits.add("Paneer");
          fruits.add("Paratha");
          fruits.add("Mojito");
          fruits.add(3,"Dahi");
          fruits.add(4,"Puri");
          fruits.add(5,"Chicken");
          
          fruits.add(3,"Vada");		//This will add "Vada" at index 3 and will push "Dahi" to 4 then "Puri" to 									 //5 and next accordingly
          System.out.println(fruits);
  
  //OutPut
  [Paneer, Paratha, Mojito, Vada, Dahi, Puri, Chicken]
  ```

- ### Declaration and assignment of ArrayList in same line

  ```java
  ArrayList<Integer> num = new ArrayList<>(Arrays.asList(1,2,3,4));		//Also note we use non-primitive data 													//type in collection i.e we used Integer instead of int
  ```

  Another method to declare a ArrayList is:

  ```java
  ArrayList<String> gfg = new ArrayList<String>() {
              {
                  add("Geeks");
                  add("for");
                  add("Geeks");
              }
          };
  
          // print ArrayList
          System.out.println("ArrayList : " + gfg);
  
  //OutPut
  ArrayList : [Geeks, for, Geeks]
  ```

   

- addAll(Collection) - When we need to add one collection to another collection we use addAll().

  ```java
   ArrayList<String> fruits = new ArrayList<>();
          ArrayList<String> nums = new ArrayList<>();
  
          fruits.add("Paneer");
          fruits.add("Paratha");
          fruits.add("Mojito");
          fruits.add(3,"Dahi");
          fruits.add(4,"Puri");
          fruits.add(5,"Chicken");
  
          nums.add("1");
          nums.add("2");
          nums.add("3");
          fruits.addAll(nums);
          System.out.println(fruits);
  //Output
  [Paneer, Paratha, Mojito, Dahi, Puri, Chicken, 1, 2, 3]
  ```

- addAll(index, Collection) - When we need to add a Collection to another collection at an particular index we use addAll(index, Collection)

  ```java
  ArrayList<String> fruits = new ArrayList<>();
          ArrayList<String> nums = new ArrayList<>();
  
          fruits.add("Paneer");
          fruits.add("Paratha");
          fruits.add("Mojito");
          fruits.add(3,"Dahi");
          fruits.add(4,"Puri");
          fruits.add(5,"Chicken");
  
          nums.add("1");
          nums.add("2");
          nums.add("3");
          fruits.addAll(2,nums);
          System.out.println(fruits);
  //Output
  [Paneer, Paratha, 1, 2, 3, Mojito, Dahi, Puri, Chicken]
  ```

  

- get(index) - We use this get() method when we need a particular element from the ArrayList by specifying the index

  ```java
  ArrayList<Integer> nums = new ArrayList<>((Arrays.asList(1,2,3,4)));
  System.out.println("ArrayList elements using the get function:"+nums.get(0)+" "+nums.get(1));
  
  //Output
  ArrayList elements using the get function:1 2
  ```

  

- set(index,value) - Replaces the element at the specified position in this list with the specified element.

  ```java
  ArrayList<String> gfg = new ArrayList<String>() {
              {
                  add("Geeks");
                  add("for");
                  add("Geeks");
              }
          };
          gfg.set(1,"AND");
          // print ArrayList
          System.out.println("ArrayList : " + gfg);
  ```

  

- remove(index)  -   In order to remove an element from an ArrayList, we can use the [remove() method](https://www.geeksforgeeks.org/arraylist-linkedlist-remove-methods-java-examples/). This method is overloaded to perform multiple operations based on different parameters. They are:

  - **remove(Object):** This method is used to simply remove an object from the ArrayList. If there are multiple such objects, then the first occurrence of the object is removed.

  - **remove(int index):** Since an ArrayList is indexed, this method takes an integer value which simply removes the element present at that specific index in the ArrayList. After removing the element, all the elements are moved to the left to fill the space and the indices of the objects are updated.

    ```java
     ArrayList<String> gfg = new ArrayList<String>() {
                {
                    add("Geeks");
                    add("for");
                    add("Geeks");
                    add("is");
                    add("coding");
                    add("website");
                }
            };
            
            gfg.remove("is");
            gfg.remove(4);
            // print ArrayList
            System.out.println("ArrayList : " + gfg);
    
    //OutPut
    ArrayList : [Geeks, for, Geeks, coding]
    ```

    

- removeAll()  -  This method is used to remove a collection from another collection.....

  ​		for eg. if c1 is a subset of c2...then **c2.removeAll(c1)** will remove the c1 elements from c2.

  ```java
  ArrayList<String> gfg = new ArrayList<String>() {
              {
                  add("Geeks");
                  add("for");
                  add("Geeks");
                  add("is");
                  add("coding");
                  add("website");
                  add("for");
                  add("students");
              }
          };
  
          ArrayList<String> gfg1 = new ArrayList<>(Arrays.asList("is","for","coding", "Geeks"));
          gfg.removeAll(gfg1);
          // print ArrayList
          System.out.println("ArrayList : " + gfg);
  
  //Output
  ArrayList : [website, students]
  
  ```

  

- clear()  -    This method is used to remove all elements from any list.

  ```java
  ArrayList<String> gfg = new ArrayList<String>() {
              {
                  add("Geeks");
                  add("for");
                  add("Geeks");
                  add("is");
                  add("coding");
                  add("website");
                  add("for");
                  add("students");
              }
          };
  
          gfg.clear();
          // print ArrayList
          System.out.println("ArrayList : " + gfg);
         
  //OutPut
  ArrayList : []
  ```

  

- size()  - Returns the number of elements in the list.

  ```java
  ArrayList<String> gfg = new ArrayList<String>() {
              {
                  add("Geeks");
                  add("for");
                  add("Geeks");
                  add("is");
                  add("coding");
                  add("website");
                  add("for");
                  add("students");
              }
          };
  
          // print ArrayList
          System.out.println("ArrayList elements: " + gfg.size());
  
  //Output
  ArrayList elements: 8
  ```

  

- contains(element) - Returns a boolean value if this element is present in the ArrayList.

  ```java
  ArrayList<String> gfg = new ArrayList<String>() {
              {
                  add("Geeks");
                  add("for");
                  add("Geeks");
                  add("is");
                  add("coding");
                  add("website");
                  add("for");
                  add("students");
              }
          };
  
          // print ArrayList
          System.out.println("ArrayList contains elements: " + gfg.contains("is"));
  
  //output
  ArrayList contains elements: true
  ```

  

- isEmpty() - Returns true if the element contains no element.

  ```java
   ArrayList<String> gfg = new ArrayList<String>() {
              {
                  add("Geeks");
                  add("for");
                  add("Geeks");
                  add("is");
                  add("coding");
                  add("website");
                  add("for");
                  add("students");
              }
          };
          gfg.clear();
  
          // print ArrayList
          System.out.println("ArrayList is empty: " + gfg.isEmpty());
          gfg.add("Geek");
          System.out.println("ArrayList is empty: " + gfg.isEmpty());
  //Output
  ArrayList is empty: true
  ArrayList is empty: false
  ```

  

- toArray()  -  This method is used to return an array containing all the elements in the list in correct order.

  

  