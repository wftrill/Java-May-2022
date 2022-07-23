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
## Test Case 1
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

## Expected Output

{johny=78.9, karthik=90.0, shannu=67.0}

## Test Case 2
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
## Expected Output

{Bala=89.0, Chiru=70.0, Nag=97.0}

# PPA2
![image](https://user-images.githubusercontent.com/82328858/180589588-1c6c5b9b-7a1a-4948-b76a-911684ef431f.png)

```
import java.util.*;
abstract class Account implements Comparable<Account>{
    String acc_no;
    double balance;	
    public Account(String no,double bal){
        acc_no = no; 
        balance = bal;
    }	
//Override "compareTo" method here
    
// Override "equals" method here
    
// Override "hashCode" method here
    
}
class SavingsAccount extends Account{
    public SavingsAccount(String acc_no, double bal) {
        // Complete the definition
        
    }
    // Override the toString() method
    
}


class CurrentAccount extends Account{
    double overdraft_limit;
    public CurrentAccount(String acc_no, double bal, double odl) {
        // Complete the constructor definition}}
        
    }

    // Override the toString() method}}
    
}

public class Test4 {
     // Define the `accountProcessor' method here
     public static void accountProcessor(ArrayList<Account> obj){
         
     }

 public static void main(String args[]) {
        Scanner s = new Scanner(System.in);
        ArrayList<Account> acc = new ArrayList<Account>();
        
        //reading the number of savings accounts
        int s_acc_count = s.nextInt();
        for(int i=1;i<=s_acc_count;i++) {
            //reading acc no
            String no = s.next();
            //reading balance
            double bal = s.nextDouble();
            acc.add(new SavingsAccount(no,bal));
        }
        
        //reading the number of current accounts
        int c_acc_count = s.nextInt();
        for(int i=1;i<=c_acc_count;i++) {
            //reading acc no
            String no = s.next();
            //reading balance
            double bal = s.nextDouble();
            //reading overdraft limit
            double lim = s.nextDouble();
            acc.add(new CurrentAccount(no,bal,lim));
        }
        
        accountProcessor(acc);
        }
}
```
Test Case 1
```
3
111 2000
222 1000
111 5000
2
444 1200 50000
111 6000 50000
```

Expected Output
```
Savings Account:111 , Balance:2000.0
Current Account:444 , Balance:1200.0
Savings Account:222 , Balance:1000.0
```
Test Case 2
```
4
111 800
222 5000
888 100
555 6000
2
222 1200 500000
111 6500 500000
```

Expected Output
```
Savings Account:555 , Balance:6000.0
Savings Account:222 , Balance:5000.0
Savings Account:111 , Balance:800.0
Savings Account:888 , Balance:100.0
```

# GRPA 1
Given as input a set of four objects of class CricketPlayer complete the Java code to segregate the players represented by these objects into batsmen and bowlers.
Create an ArrayList object to store the four objects of CricketPlayer. Segregate them as batsmen and bowlers based on the following criteria: 
A player is termed as a batsman if his/her average runs per match are greater than 25.
A player is termed as a bowler if his/her average wickets per match are greater than 1.
Create ArrayList bt to store the batsmen and ArrayList bw to store the bowlers. Observe that the same player could belong to both the lists. 
Print the list of bowlers in a line, followed by the list of batsmen in the next line, using the displayPlayers(ArrayList<CricketPlayer> bw, ArrayList<CricketPlayer> bt) method.
```
import java.util.*;
class CricketPlayer{
  private String name;
  private int wickets;
  private int runs;
  private int matches;
  public CricketPlayer(String s, int w, int r, int m){
    this.name = s;
    this.wickets = w;
    this.runs = r;
    this.matches = m;
  }
  public String getName(){
    return name;
  }
  public int getWickets(){
    return wickets;
  }
  public int getRuns(){
    return runs;
  }
  public double avgRuns(){
    return runs/matches;
  }
  public double avgWickets(){
    return wickets/matches;
  }
} 
public class Main {
// Define displayPlayers() method here
    
 public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    CricketPlayer p1 = new CricketPlayer(sc.next(), sc.nextInt(), 
                                sc.nextInt(), sc.nextInt());
    CricketPlayer p2 = new CricketPlayer(sc.next(), sc.nextInt(), 
                                sc.nextInt(), sc.nextInt());
    CricketPlayer p3 = new CricketPlayer(sc.next(), sc.nextInt(), 
                                sc.nextInt(), sc.nextInt());
    CricketPlayer p4 = new CricketPlayer(sc.next(), sc.nextInt(), 
                                sc.nextInt(), sc.nextInt());

    // Define ArrayList objects here
    displayPlayers(bw, bt);
  }
}
```
Test Case 1
```
Dhoni
11
11000
347
Kohli
10
12285
257
Ashwin
181
1000
90
Bumrah
130 
50
60
```

Expected Output
```
Ashwin Bumrah 
Dhoni Kohli 
```
Test Case 2
```
KapilDev
434
12867
131
Tendulkar
46
15921
200
AnilKumble
619
18355
132
Dravid
32
13265
163
```

Expected Output
```
KapilDev AnilKumble 
KapilDev Tendulkar AnilKumble Dravid 
```
Test Case 3
```
Muralitharan
800
18180
133
Marshall
376
7876
81
Sehwag
13
8503
103
Laxman
20 
8781
134
```

Expected Output
```
Muralitharan Marshall 
Muralitharan Marshall Sehwag Laxman 
```

# GRPA 2
Write a program that checks for balanced parentheses in an expression i.e. whether the pairs and the order of  "{ ",  " } ”, " ( ", " ) ”, " [ ", " ] ” are correct in the given input.
The program should keep taking expressions as input one after the other, until the user enters the word `done' (not case-sensitive). After all the expressions are input, for each input, the program should print whether the given expression is balanced or not (the order of the output should match the order of the input). If an input expression is balanced, print Balanced else print Not Balanced
```
import java.util.*;

public class Test3{
    public static boolean balanceCheck(String sequence) {
//Write your code here
        
}
   
    public static void main(String args[]) {
        Scanner s = new Scanner(System.in);
        
        ArrayList<String> expr_arr= new ArrayList<String>();
        String inp=null;
        
        do {
            inp = s.nextLine();
            if(!inp.equalsIgnoreCase("Done"))
                expr_arr.add(inp);
        }while(!inp.equalsIgnoreCase("Done"));

        for(String expr : expr_arr) {
            if(balanceCheck(expr)) {
                System.out.println("Balanced");
            }
            else {
                System.out.println("Not Balanced");
            }
        }
    }
}
```
Test Case 1
```
class a{ public static void main(String args[]){System.out.println();}
class a{ public static void main(String args[]){System.out.println();}}
}}{{
()()[(){()}]
void fun(int x, double y){ x = x*y; return x;}
done
```

Expected Output
```
Not Balanced
Balanced
Not Balanced
Balanced
Balanced
```
Test Case 2
```
{)}
public void fun(Integer[] arr){ if(arr.length > 7){ print("ok");}
({[]})[][()]
Done
```

Expected Output
```
Not Balanced
Not Balanced
Balanced
```
