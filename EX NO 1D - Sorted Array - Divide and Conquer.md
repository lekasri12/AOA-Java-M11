
# EX 1D Sorted Array using Divide and Conquer Approach.
## DATE: 18.09.2025
## AIM:
To write a Java program to for given constraints.
Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.
The overall run time complexity should be O(log (m+n)).

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
import java.util.Scanner;

public class Solution {
    private int p1 = 0, p2 = 0;
    private int getMin(int[] nums1, int[] nums2) {
        if (p1 < nums1.length && p2 < nums2.length) {
            return nums1[p1] < nums2[p2] ? nums1[p1++] : nums2[p2++];
        } else if (p1 < nums1.length) {
            return nums1[p1++];
        } else if (p2 < nums2.length) {
            return nums2[p2++];
        }
        return -1;
    }

    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
       //Type code here...
       
       
       int m=nums1.length,n=nums2.length;
       int total=m+n;
       if(total%2==0){
           for(int i=0;i<total/2-1;++i){
               getMin(nums1,nums2);
           }
           return (double)(getMin(nums1,nums2)+getMin(nums1,nums2))/2;
       }
       else{
           for(int i=0;i<total/2;++i){
               getMin(nums1,nums2);
           }
           return getMin(nums1,nums2);
       }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        int m = sc.nextInt();
        int[] nums1 = new int[m];
        for (int i = 0; i < m; i++) {
            nums1[i] = sc.nextInt();
        }

        int n = sc.nextInt();
        int[] nums2 = new int[n];
        for (int i = 0; i < n; i++) {
            nums2[i] = sc.nextInt();
        }

        double median = sol.findMedianSortedArrays(nums1, nums2);
        System.out.println("Median of the two sorted arrays = " + median);
        
        sc.close();
    }
}

```

## Output:
<img width="1282" height="364" alt="Screenshot 2025-11-20 160641" src="https://github.com/user-attachments/assets/6a49c3ac-ae78-4840-af9f-c1c6ac3fa562" />

## Result:
The program successfully implemented and the expected output is verified.
