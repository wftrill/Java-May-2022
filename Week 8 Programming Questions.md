### Practice Prgramming Assignment 1
![image](https://user-images.githubusercontent.com/90960384/179887586-0e73df33-efd5-47ae-aed9-8e4cf6e338bb.png)
![image](https://user-images.githubusercontent.com/90960384/179887601-cda89c6f-599a-4c61-9730-08cbdfdd0593.png)
```java
import java.util.*;
//define class Address

//define class Department

//define class Person

//define class Employee



public class FClass{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        String n = sc.next(); //read name
        String a1 = sc.next(); //read address
        String d1 = sc.next(); //read department
        String a2 = sc.next(); //read new address
        String d2 = sc.next(); //read new department
        try {
            Employee e1 = new Employee(n, new Address(a1), new Department(d1));
            Employee e2 = e1.clone(); 
            e1.updateEmp(a2, d2);
            System.out.println(e1 + ", " + e2);
        }
        catch(CloneNotSupportedException e) {
            System.out.println("clone() not supported");
        }
    }
}

```

###### Sample Input 1
    Vinay Kota HR
    Mumbai Finance
###### Expected Output 1
    Vinay : Mumbai : Finance, Vinay : Kota : HR
###### Sample Input 2
    Brinda Chennai Finance
    Kolkata IT
###### Expected Output 2
    Brinda : Kolkata : IT, Brinda : Chennai : Finance

### Practice Programming Assignment 2
![image](https://user-images.githubusercontent.com/90960384/179886617-870e5bc6-fea8-466a-8fb5-36a9d6876c92.png)
![image](https://user-images.githubusercontent.com/90960384/179886652-8f01a3fa-433b-4821-be38-62b5c23aec53.png)
```java
import java.util.stream.Stream;
import java.util.*;
import java.text.*;

class Student{
    private int roll_num;
    private Date dose_one = new Date(); 
    private Date dose_two = new Date();	
    
    public int getRollNo() {
        return roll_num;
    }	
    public Student(int roll_num, String dd_str) {
        SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy");
        this.roll_num = roll_num;
        try {			
            dose_one = sdf.parse(dd_str);		
            dose_two = sdf.parse("30/03/2022");
        }
        catch(ParseException e){
            System.out.println("Incorrect Date Format");
        }
    }	
    public boolean isEligible() {
        //Complete the method definition
        
    }
}
//Define class StudentList here.
//Inside class StudentList, define method getEligibleList(List<Student>)
//that uses the method isEligible() in class Student to return the 
//stream of eligible students.

//Define method isEmpty(Stream<Student>) 
//that helps customizing output message
public class SecondDose{
    public static void main(String[] args) {		
        Scanner sc = new Scanner(System.in);
        int roll_num;		
        String dose_one_str;
        List<Student> full_list = new ArrayList<Student>();
        
        int num = sc.nextInt(); //Number of students
        for (int i=0; i<num; i++) {
            roll_num = sc.nextInt(); //Roll Number
            dose_one_str = sc.next(); //Date of Dose One			
            Student st = new Student(roll_num, dose_one_str);
            full_list.add(st); // Add the student to an ArrayList
        }
        
        StudentList list = new StudentList();		
        Stream<Student> eligible_list = list.getEligibleList(full_list);
        if (!list.isEmpty(eligible_list)) {
            System.out.println("The list of eligible students are: ");
            eligible_list = list.getEligibleList(full_list);
            eligible_list.forEach(s -> System.out.println(s.getRollNo()));
        }
        else {
            System.out.println("There are no eligible students.");
        }
        sc.close();
    }
}
```
![image](https://user-images.githubusercontent.com/90960384/179886765-5a2f42fc-ec61-41ef-b237-a05e2b989569.png)
![image](https://user-images.githubusercontent.com/90960384/179886794-f090352f-8df2-4820-9873-d884bc6444a5.png)
![image](https://user-images.githubusercontent.com/90960384/179886815-4e527dfb-e349-445c-989b-5c96e947e396.png)
![image](https://user-images.githubusercontent.com/90960384/179886860-1fce3e47-bd6b-4016-87b6-907df4957c25.png)


### Graded Programming Assignment 1
![image](https://user-images.githubusercontent.com/90960384/179887081-fc38a3d1-2e98-4628-a096-d78da948c358.png)
```java
import java.util.*;
import java.util.stream.*;
//define class Employee


class FClass{
    //define method query

    
 public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        var eList = new ArrayList<Employee>();
        eList.add(new Employee("Jack", "HR", 30000));
        eList.add(new Employee("Aria", "HR", 40000));
        eList.add(new Employee("Nora", "IT", 50000));
        eList.add(new Employee("Bella", "IT", 60000));
        eList.add(new Employee("Jacob", "IT", 70000));
        eList.add(new Employee("James", "HR", 80000));
        String d = sc.next();       //read department
        double s = sc.nextInt();    //read salary
		
        var st = query(eList, d, s);
        st.forEach(n -> System.out.println(n + " "));
    }
}
```
![image](https://user-images.githubusercontent.com/90960384/179887137-a9ecd16d-6bfc-4280-afe5-4af65daabd88.png)


### Graded Programming Assignment 2
![image](https://user-images.githubusercontent.com/90960384/179887276-34fb243d-76b9-4c3b-9333-f7c82da5f226.png)
![image](https://user-images.githubusercontent.com/90960384/179887330-2c9f5777-afec-4f93-a7c9-913c53187da0.png)
```java
import java.util.*;
//Define classes Items, Customer


public class Order {
  public static void main(String[] args) throws CloneNotSupportedException{
    Scanner sc = new Scanner(System.in);
    int n = sc.nextInt(); // number of items
    String[] itm = new String[n];
    for(int i = 0; i < n; i++){
      itm[i] = sc.next(); // list of items
    } 
    var c1 = new Customer("naresh", new Items(itm));
    Customer c2 = c1.clone();   
    c2.getItems().item[0] = sc.next();   //Update first item of c2
    c2.setName("suresh"); //Update name of c2
    System.out.println(c1);
    System.out.println(c2);
  }
}   
```
![image](https://user-images.githubusercontent.com/90960384/179887406-f14ebdf5-5692-4ca1-8b09-93b21b50d366.png)
