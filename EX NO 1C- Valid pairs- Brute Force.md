
# EX 1C Valid Pairs using Brute Force Approach
## DATE: 18.09.2025
## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.

## Algorithm
1. Start the program.
2. Read the value of **n** and then read **n** elements into the array.
3. Read the value of integer **k**.
4. Use two nested loops to compare every pair (i, j) where **i < j**.
5. Count the pair if the absolute difference equals **k**, then print the result.   

## Program:
```
/*
Program to implement Reverse a String
Developed by: LEKASRI G
Register Number: 212223100025  
*/
import java.util.Scanner;
public class CountPairsWithDifference {
    public static int countKDifference(int[] nums, int k) {
        //Type your code here
        int count=0;
        for(int i=0;i<nums.length;i++){
            for(int j=i+1;j<nums.length;j++){
                if(Math.abs(nums[i]-nums[j])==k){
                    count++;
                }
            }
        }
        return count;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }
        int k = sc.nextInt();
        int result = countKDifference(nums, k);
        System.out.println(result);
        sc.close();
    }
}

```

## Output:
<img width="1121" height="390" alt="Screenshot 2025-11-20 155849" src="https://github.com/user-attachments/assets/531583ef-a4c1-4202-a952-7384f8b64f15" />

## Result:
The program successfully implemented and the expected output is verified.
