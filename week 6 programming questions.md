# PPA 1

![image](https://user-images.githubusercontent.com/82328858/180444343-3142fad4-2a0c-4165-8367-22a198cb21f1.png)

```
import java.util.*;
class RemoveStudent{
	    public boolean property(Double value) {
		        if(value<65)
			            return true;
	        return false;				
	    }
	    public void detained(Map<String, Double> obj) {
        // Define the detained() method
        
}
	    public void display(Map<String, Double> obj) {
		        System.out.println(obj);
	    }
}
public class Test {
	    public static void main(String[] args) {
		        Map<String,Double> map=new TreeMap<String,Double>();
		        Scanner scanner=new Scanner(System.in); 
		        for (int i=0; i<6; i++) {
			            map.put(scanner.next(),scanner.nextDouble());
		        }
		        RemoveStudent obj=new RemoveStudent();
		        obj.detained(map);
	    }
}
```
###### Test Case 1
```
virat
23.0
johny
78.9
suchith
56.9
juhee
45.00
karthik
90.0
shannu
67.0
```

###### Expected Output

{johny=78.9, karthik=90.0, shannu=67.0}

###### Test Case 2
```
Nani
34.0
Bala
89.0
Chiru
70.0
Venky
56.0
Nag
97.0
Raj
52.0
```
###### Expected Output

{Bala=89.0, Chiru=70.0, Nag=97.0}
