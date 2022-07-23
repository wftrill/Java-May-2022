## PPA 1

Given a class name as input, complete the Java code to print the count of public and declared methods, fields and constructors in the class. For each method in class ClassStats below,fill in the missing code as described in the comments. Each method takes the class name as input.
```

import java.lang.reflect.*;
import java.util.*;
class ClassStats{
public static int getPubMethodCount(String cname) {
        try {
            //add code to return the count of 
            //public methods in the given class	
        }catch(Exception e) { return -1; }
    }
    public static int getAllMethodCount(String cname) {
        try {
            //add code to return the count of all 
            //declared methods in the given class
        }catch(Exception e) { return -1; }
    }
    public static int getPubFieldCount(String cname) {
        try {
            //add code to return the count of 
            //public fields (instance variables) in the given class
        }catch(Exception e) { return -1; }
    }
    public static int getAllFieldCount(String cname) {
        try {
            //add code to return the count of 
            //all fields (instance variables) in the given class
        }catch(Exception e) { return -1; }
    }
    public static int getPubContCount(String cname) {
        try {
            //add code to return the count of 
            //public constructors in the given class
        }catch(Exception e) { return -1; }		
    }
    public static int getAllContCount(String cname) {
        try {
            //add code to return the count of 
            //all constructors in the given class
        }catch(Exception e) { return -1; }
    }
}

class FClass{
    public static void main(String[] args) {
        String cname;
        Scanner sc = new Scanner(System.in);
        cname = sc.nextLine();
        System.out.println("Constructor: " + 
                        ClassStats.getPubContCount(cname) + ", " + 
                        ClassStats.getAllContCount(cname));
        System.out.println("Fields: " + 
                        ClassStats.getPubFieldCount(cname) + ", " +
                        ClassStats.getAllFieldCount(cname));
        System.out.println("Methods: " + 
                        ClassStats.getPubMethodCount(cname) + ", " +
                        ClassStats.getAllMethodCount(cname));
    }
}
```
Test Case 1
```
java.lang.Object
```
Expected Output
```

Constructor: 1, 1
Fields: 0, 0
Methods: 9, 12
```

Test Case 2
```
java.lang.String
```
Expected Output
```

Constructor: 15, 18
Fields: 1, 9
Methods: 82, 90
```

## PPA 2

Complete the Java code given below that takes as input a string array, where each string is assured to be either an integer or a double in string format. Your code must segregate the two types - integer and double - and print the double values followed by the integer values. For this, your code must iterate through the input array, and add each element to the appropriate array based on its type. 
```

import java.util.Scanner;
class ConvertArrays{
	    public Double doubleArr[]=new Double[3];
	    public Integer intArr[]=new Integer[3];
	    public int x=0,y=0,z=0;
	    public void convert(String[] arr){
        //loop through the arr and store each element 
		//in the appropriate array
	    }
}
	    public <T> void display(T[] arr){
	        for(T elements:arr)
	    	        System.out.print(elements+" ");
	        System.out.println();
	    }
}
public class Programming {
	    public static void main(String[] args) {
		    Scanner scanner=new Scanner(System.in);
		    String arr[]= new String[6];
		    for (int i = 0; i < arr.length; i++) {
			        arr[i]=scanner.next();
		    }
	    ConvertArrays conArrays=new ConvertArrays();
	    conArrays.convert(arr);
	    System.out.println("===After conversion Arrays===");
	    conArrays.display(conArrays.doubleArr);
	    conArrays.display(conArrays.intArr);	    
	}
}
```
Test Case 1
```
10 
20 
30 
40.45 
50.56 
67.0
```
Expected Output
```

===After conversion Arrays===
40.45 50.56 67.0 
10 20 30 
```

Test Case 2
```
1.3
2.3
0.25
90
34
45
```
Expected Output
```

===After conversion Arrays===
1.3 2.3 0.25 
90 34 45 
```

## GRPA 1

Given as input two integers n_1,n_2 and two double values d_1,d_2 complete the Java code to form two complex numbers c_1 and c_2, as described below, and print their sum.
The real parts of c_1 and c_2 are n_1 and d_1 respectively, whereas their imaginary parts are n_2 and d_2, respectively.
Define a generic class ComplexNum with the following members.
Instance variables r and i
A constructor to initialize r and i	
A method add()to return the sum of the two instances of generic type ComplexNum
A method that overrides the toString() method in the Object class so that the format of the output is in accordance with those in the test cases. 
```

import java.util.*;
//Add your code for ComplexNum here


class FClass{
public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n1, n2;
        double d1, d2;
        n1 = sc.nextInt();
        n2 = sc.nextInt();
        d1 = sc.nextDouble();
        d2 = sc.nextDouble();
        ComplexNum<Integer> c1 = new ComplexNum<Integer>(n1, n2);
        ComplexNum<Double> c2 = new ComplexNum<Double>(d1, d2);
        ComplexNum<Double> c3 = c1.add(c2);
        System.out.println(c1 + " + " + c2 + " = " + c3);
    }
}
```
Test Case 1
```
10 20
13.3 5.12
```
Expected Output
```
10.0 + 20.0i + 13.3 + 5.12i = 23.3 + 25.12i
```
Test Case 2
```
6 10
10.3 15.6
```
Expected Output
```
6.0 + 10.0i + 10.3 + 15.6i = 16.3 + 25.6i
```
Test Case 3
```
10 15
5.4 1.6
```
Expected Output
```
10.0 + 15.0i + 5.4 + 1.6i = 15.4 + 16.6i
```
## GRPA 2

![image](https://user-images.githubusercontent.com/82328858/180589113-2b246cc1-fd8d-41f5-aa01-513c27bb1beb.png)
```
import java.util.*;
class ArrayExample <T>{
  T[] a;
  
// Define constructor(s) as needed
    
    
  // Define method display() that print the elements of array a 
  
    
  // Define method elementCount(T x) that 
  
  public int elementCount(T x){
      
  }
  // counts the no. of times x is present in the array a
}
public class ArrayObject{
  public static void main(String[] args){
    Scanner sc = new Scanner(System.in);
    int len = sc.nextInt(); //Taking input for length of the array
    Integer[] x = new Integer[len];
    for(int i = 0; i < len; i++){
          x[i] = sc.nextInt(); //Taking input for Integer array
    }
    
    //Write the code here to create an object obj for Integer array
    @SuppressWarnings("unchecked")
    
    int s1 = sc.nextInt(); //Taking input for the value to be counted
    String[] y = new String[len];
    for(int i = 0; i < len; i++){
          y[i] = sc.next(); //Taking input for String array
    }
    
    //Write the code here to create an object obj1 for String array
    @SuppressWarnings("unchecked")
    

    String s2 = sc.next(); //Taking input for the value to be counted
    obj.display();
    System.out.println(obj.elementCount(s1));
    obj1.display();
    System.out.println(obj1.elementCount(s2));
  }
}
```
Test Case 1
```
2 
1 
1 
1 
car 
car 
car 
```
Expected Output
```
1 1 
2
car car 
2 
```

Test Case 2
```
3 
4 
5
6
4 
java 
nest 
play
play
```
Expected Output
```
4 5 6 
1
java nest play 
1
```
