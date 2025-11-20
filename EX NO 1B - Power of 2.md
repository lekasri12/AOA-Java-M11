
# EX 1B Power of 2
## DATE: 18.09.2025
## AIM:
To write a Java program to for given constraints.Given an integer n, return true if it is a power of two. Otherwise, return false.
An integer n is a power of two, if there exists an integer x such that n == 2x.

## Algorithm
1. Start the program.
2. Read the integer value n from the user.
3. If n ≤ 0, return false (because powers of 2 are always positive).
4. Use a loop to check whether n becomes 1 when repeatedly divided by 2.
5.If n becomes 1, display true; otherwise display false.   

## Program:
```
/*
Program to implement Reverse a String
Developed by: LEKASRI G
Register Number: 212223100025 
*/
import java.util.*;
public class fact{
    public static void main(String [] args){
        Scanner s=new Scanner(System.in);
        int n;
        n=s.nextInt();
        if(n<0)
        {
            System.out.print("Invalid input.");
        }
        long fact=1;
        for(int i=1;i<=n;i++)
        {
            fact*=i;
        }
        System.out.println(fact);
    }
    
}
```

## Output:
<img width="916" height="327" alt="image" src="https://github.com/user-attachments/assets/7ecbeda6-5a9f-49f2-aad5-09c7a4086fbf" />



## Result:
The program successfully implemented and the expected output is verified.
