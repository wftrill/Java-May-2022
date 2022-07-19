### Practice Programming Assignment 1
![image](https://user-images.githubusercontent.com/82328858/179658307-91410d19-7262-485f-abae-fc4e6a7b00bc.png)
![image](https://user-images.githubusercontent.com/82328858/179658328-56363c16-a43a-4cde-81a4-2d9efc5b7455.png)



```java
import java.util.*;

//Define class WrongDestinationException


//Define class ImproperHeadCountException


class CarRental{
    int passenger_count;
    String chosen_destination;
    HashMap<String,Double> available_destinations;  
	
    public CarRental(int pc, String dest) {
        passenger_count = pc;
        chosen_destination = dest;
        //preassigned destinations and total car fare
        //Leave the code below as it is
        available_destinations = new HashMap<String,Double>();
        available_destinations.put("Marina Beach", 2000.0);
        available_destinations.put("Elliot's Beach", 5000.0);
        available_destinations.put("Film City", 8000.0);
    }
    public void carBooker() throws NullPointerException{
        
        //define this method according to the problem description
    }

}
public class Test4{
    public static void main(String args[]) {
        Scanner s = new Scanner(System.in);
        
        int num = s.nextInt(); //input the number of car rental requests
        try {
            for(int i=1;i<=num;i++) {
                int heads = s.nextInt(); //enter head count
                s.nextLine();  //enter destination
                String dest = s.nextLine();     
                CarRental obj = new CarRental(heads,dest);
                obj.carBooker();
            }
        }catch(Exception e) {
            System.out.println(e.getCause());
        }
    }
}
```
![image](https://user-images.githubusercontent.com/82328858/179658429-185cc35a-86eb-4692-bc8d-e577e30eeed1.png)

###SAMPLE OUTPUT 1

```
ImproperHeadCountException: Head count should be positive non zero value
Destination: Elliot's Beach, Head cost: 1250.0
WrongDestinationException: Invalid destination
```

###SAMPLE OUTPUT 2

```
ImproperHeadCountException: Head count should be positive non zero value
Destination: Film City, Head cost: 1142.857142857143
```

### Practice Programming Assignment 2
```java
import java.util.*;
class FClass{
   
 //implement function replace()
 
	 public static void main(String[] args) {
			Scanner sc = new Scanner(System.in);
			String s1 = sc.next();
			int i = sc.nextInt();
			char c = sc.next().charAt(0);
			try {
				String s2 = new String(replace(s1.toCharArray(), i, c));
				System.out.println(s2);
			} 
			catch(Exception e) {
				System.out.println(e.getMessage());
			}
	}
}
```

### Graded Programming Assignment 1
```java
import java.util.*;
//Define DivisionException class here


public class Test {
 
    //Define divide(int a, int b) here
    

    public static void main(String[] args) {
       Scanner sc = new Scanner(System.in);
       int x = sc.nextInt();
       int y = sc.nextInt();
       
       //call divide method here


   }
} 
```

### Graded Programming Assignment 2
```java
import java.util.*;
//define user defined exception InvalidInputEx



//define the class IntList with 
 class IntList{
     //instance variable of int[]
    int[] arr = new int[5];
    
    //and methods set_value, getArray()
}


class FClass{
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        IntList ilist = new IntList();
        try {
            for(int i = 0; i < 5; i++) {			
                int n = sc.nextInt();
                int m = sc.nextInt();
                ilist.set_value(n, m);
            }
        }
        catch(InvalidInputEx e) {
            System.out.println(e.getMessage());
            Throwable ori = e.getCause();
            System.out.println(ori.getMessage());
        }	
        int[] i_arr = ilist.getArray();
        for(int i = 0; i < i_arr.length; i++)
            System.out.print(i_arr[i] + " ");
    }
}
```
