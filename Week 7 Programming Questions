### Practice Programming Assignment 1
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
