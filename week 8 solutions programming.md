# ppa 1 
```
// Write a program to clone an object e1 of class  Employee by implementing the interface Cloneable
//. After cloning, update the department and the address of  e1. Complete the program as detailed below to achieve this functionality.   

// Define classes Address and Department that implement the interface Cloneable, and have the following members: 
// In both classes, add an instance variable of String type (to store the address and the department respectively) 
// Implement the required constructor(s) and accessors. 
// Override the method clone.

// Define a class Person that implements the interface Cloneable, and has the following members:
// Instance variables name of type String and addr of type Address	
// Implement the required constructor(s) and accessors
// Override the method clone
// Define a class Employee that implements the interface Cloneable, extends the class Person, and has the following members:
// Instance variable dept of type Department	
// Implement the required constructor(s) and accessors.
// Override the method clone.
// Define a method updateEmp to update the dept and addr of an Employee object
import java.util.*;
//define class Address
class Address implements Cloneable{
    String addr;
    public Address(String ad){
        this.addr=ad;
    }
    public Address clone() throws CloneNotSupportedException{
        Address a=(Address) super.clone();
        return a;
    }
 
}


//define class Department
class Department implements Cloneable{
    String dep;
    public Department(String ad){
        this.dep=ad;
    }
    public Department clone() throws CloneNotSupportedException{
        Department a=(Department) super.clone();
        return a;
    }
}

//define class Person
class Person implements Cloneable{
    String name;
    Address add;
    public Person(String n,Address a1){
        this.name=n;
        this.add=a1;
    }
    public Person clone() throws CloneNotSupportedException{
        Person p=(Person) super.clone();
        p.add=add.clone();
        return p;
    }
}

//define class Employee
class Employee extends Person implements Cloneable{

    Department dept;
    public Employee(String n,Address a1,Department d1){
        super(n,a1);
        this.dept=d1;
    }
    
    public Employee clone() throws CloneNotSupportedException{
        Employee e=(Employee) super.clone();
        e.dept=dept.clone();
        return e;
    }
    public void updateEmp(String a2,String d2){
        this.dept=new Department(d2);
        this.add=new Address(a2);
    }
    //Vinay : Mumbai : Finance, Vinay : Kota : HR
    public String toString(){
        return name +" : "+add.addr+" : "+ dept.dep ;
    }
    
}



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

## ppa 2
```
// A school is planning for a second Covid-19 vaccination drive on 30/03/2022, for students who have already taken the first dose. 
//A student is eligible for the second dose if 28 days have passed since the first dose. Write a Java program to find the list of students who are eligible 
//for the second dose of vaccination, based on the date of their first dose. Note that you must use the Stream class.
// Your program takes as input a positive integer, which is the total number of students, followed by the roll number and the date of first dose of vaccination in “dd/MM/yyyy” 
//format for each student.
//  Your program should print the roll numbers of all students who are eligible for the second dose on 30/03/2022
// The roll number, the date of first dose of vaccination and the planned date of second dose are available as instance variables in class Student.

// Things to be done:

// Define method isEligible() inside class Student that returns true if the student is eligible for the second dose.

// Define class StudentList inside which you have to define two methods - getEligibleList(List<Student>) and isEmpty(Stream<Student>).

// The method getEligibleList(List<Student>) returns a stream of eligible students using method isEligible() inside class Student

// The method isEmpty(Stream<Student>) checks if the stream is empty, in order to customize the output message. If the stream is empty, it should print the message: 
//There are no eligible students. If the stream is not empty, then it prints the message: The list of eligible students are: followed by the roll numbers of eligible students.



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
        return ((dose_two.getTime()-dose_one.getTime())/(24*60*60*1000))>28;
        
    }
}
//Define class StudentList here.
class StudentList {
    public Stream<Student> getEligibleList(List<Student> full){
        return full.stream().filter(i->i.isEligible());
    }
    
    public boolean isEmpty(Stream<Student> s1){
        return s1.count()==0;
        
    }
}
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
# grpa 1
```
// The program stores a list of Employee objects, each of which has name, department and salary as instance variables.
//A user can query the list to find the Employees who belong to a specific department and have salary greater than or equal to the input salary. Complete the program as specified.
// Define a class Employee as follows:
// Add the instance variables to represent name, department and salary
// Implement the required constructor(s) and accessors.
// Override the method toString() so that the format of the output is in accordance with those in the test cases. 

// Define a function query that takes a list of employees, a department and a salary as input. 
//returns a stream comprising the Employee objects that have the same department and have salary greater and equal to the given salary.	


import java.util.*;
import java.util.stream.*;
//define class Employee
class Employee{
    String name;
    String dept;
    int sal;
    public Employee(String n,String de,int i){
        name=n;
        dept=de;
        sal=i;
    }
    public String toString(){
        return name+ " : "+ dept+ " : " + sal;
    }
}


// Nora : IT : 50000 
// Bella : IT : 60000 
// Jacob : IT : 70000 
public class FClass{
    //define method query
    public static Stream<Employee> query(ArrayList<Employee> lis,String d,double s){
        return lis.stream().filter(i->i.dept.equals(d) && i.sal>=s);
    }

    
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
# grpa 2
```
// Naresh (aka Customer c1) buys a set of items from a shop. Suresh (aka Customer c2)
// also buys all items bought by Naresh except the first item, in place of which Suresh
// buys another item. Write a program that defines two classes Items and Customer, and
// clones the object of class Customer to model the scenario given above. Classes Items
// and Customer should be cloneable, and must have the functionality to clone (deep copy)
// c2 from c1. You are given as input the number of items bought by Naresh, the names
// of the items, and the new item that Suresh will be buying. The code to change the first
// item and the name in the second customer object after the cloning, has been provided
// in the given code. You should complete the program as specified below.

// Define a class Items that implements interface Cloneable, and has the following
// members.
// – A public instance variable item of type String[] to store the item names
// – Constructor(s) and accessors to, respectively, initialize and access the instance
// variable
// – Override the method clone
// – Override the method toString so that the format of the output is in accordance
// with those in the test cases

// Define a class Customer that implements interface Cloneable, and has the following
// members.
// – Instance variable name of type String to store the name of the customer
// – Instance variable of type Items to store the items purchased by the customer
// – Implement the constructor(s), the accessor getItems() to return the object
// of Items, and the mutator setName(String s) to update the name of the
// customer.
// – Override the method clone
// – Override the method toString so that the format of the output is in accordance
// with those in the test cases.


// naresh milk bread 
// suresh maggi bread 


import java.util.*;
//Define classes Items, Customer
class Items implements Cloneable{
    public String[] item;
    public Items(String[] itm){
        this.item=itm;
    }
    public Items clone() throws CloneNotSupportedException{
         Items it=(Items) super.clone();
         it.item=item.clone();
         return it;
    }
    public String toString(){
        String st="";
        for(String s:item){
            st=st+s+" ";
        }
        return st;
    }
}

class Customer implements Cloneable{
    String name;
    Items iteam;
    public Customer(String n,Items i){
        name=n;
        iteam=i;
    }
    public Items getItems(){
        return iteam;
    }
    public Customer clone() throws CloneNotSupportedException{
         Customer it=(Customer) super.clone();
         it.iteam=iteam.clone();
         return it;
    }
    public String toString(){
        return name+" "+ iteam;
    }
    public void setName(String s){
        name=s;
    }
}


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
