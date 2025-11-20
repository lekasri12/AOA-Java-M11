
# EX 1A Print All Numbers 
## DATE: 18.09.2025
## AIM:
To write a Java program that finds the median of two sorted arrays nums1 and nums2 of sizes m and n respectively. The overall time complexity should be O(log(m + n)).
## Algorithm
1. Start the program.
2. Read the sizes of the two arrays and their elements.
3. Use two pointers to pick the smallest element from both arrays step-by-step.
4. Traverse until reaching the median index (middle of combined sorted list).
5. If the total number of elements is odd, return the middle element; otherwise return the average of the two middle elements.
## Program:
```
/*
Program to implement Reverse a String
Developed by: LEKASRI G 
Register Number: 212223100025 
*/
import java.util.*;
public class demo{
    public static void main(String[] args){
        Scanner s=new Scanner(System.in);
        int N,i;
        N=s.nextInt();
        if(N<=0)
        {
            System.out.print("Invalid input. N must be greater than 0.");
        }
        else{
            for(i=1;i<=N;i++){
                System.out.print(i+" ");
            }
        }
    }
}
```

## Output:
<img width="1036" height="342" alt="image" src="https://github.com/user-attachments/assets/edb68e24-18ec-4d9b-86ee-da4a622b0229" />

## Result:
The program successfully print all the numbers from 1 to N. 
