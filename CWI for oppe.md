# question 1
```
/* Complete the given Java program that takes as input a list of strings, removes the strings that contain , (comma) and/or . (dot) and prints the remaining strings.
    Class CollectRes has/should have the following members:
        - Main method that takes input and invokes method collectData to filter the input based on the given conditions.
        - Method public static Collection<String> collectData(ArrayList<String>) that filters the given list using methods in class Stream, to obtain the specified output. */
        
import java.util.*;
import java.util.stream.*;
public class CollectRes{
    public static Collection<String> collectData(ArrayList<String> l){
        Collection<String> obj;
        // Write your code here
        obj = l.stream().filter(s -> s.contains(",")!=true).filter( s -> s.contains(".")!=true).toList();
        obj = new TreeSet<String>(obj);
        return obj;
    }
    
public static void main (String [] args){
    var list = new ArrayList<String>();
    Scanner sc = new Scanner(System.in);
    int len = sc.nextInt();
    for (int i = 0; i<len;i++){
        list.add(sc.next());
    }
    System.out.println(CollectRes.collectData(list));
}
}


//Input
//4
//India
//India,
//India
//Asia
```
