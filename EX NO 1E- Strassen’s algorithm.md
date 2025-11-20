
# EX 1E Integer Multiplication using Divide and Conquer Approach(Strassen’s algorithm).
## DATE: 18.09.2025
## AIM:
To write a Java program to for given constraints.
You are given two square matrices A and B of size n × n (where n is a power of 2). Your task is to compute their matrix product using Strassen’s Matrix Multiplication algorithm and return the resulting matrix.

Unlike traditional matrix multiplication which takes O(n3)O(n^3)O(n3) time, Strassen’s algorithm improves this by reducing the number of recursive multiplications from 8 to 7, achieving approximately O(n2.81)O(n^{2.81})O(n2.81) complexity.
## Algorithm
1. Read two large integer inputs as strings.
2. Remove leading zeros and pad the inputs if required.
3. Split each number into two halves: high and low parts.
4. Recursively compute:

   * z0 = low × low
   * z2 = high × high
   * z1 = (high + low) × (high + low) − z0 − z2
5. Combine the results using powers of 10 and return the final product.
6. Print the resulting multiplied value.  

## Program:
```
/*
Program to implement Reverse a String
Developed by: LEKASRI G
Register Number: 212223100025 
*/
import java.util.Scanner;

public class StrassenMatrix {

    static int[][] add(int[][] A, int[][] B) {
        int n = A.length;
        int[][] C = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                C[i][j] = A[i][j] + B[i][j];
        return C;
    }

    static int[][] subtract(int[][] A, int[][] B) {
        int n = A.length;
        int[][] C = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                C[i][j] = A[i][j] - B[i][j];
        return C;
    }

    static int[][] strassen(int[][] A, int[][] B) {
        //Type code here...
        
        int n = A.length;
        int[][] C = new int[n][n];
        if (n == 1) {
            C[0][0] = A[0][0] * B[0][0];
        } else {
            int newSize = n / 2;
            int[][] A11 = new int[newSize][newSize];
            int[][] A12 = new int[newSize][newSize];
            int[][] A21 = new int[newSize][newSize];
            int[][] A22 = new int[newSize][newSize];
            int[][] B11 = new int[newSize][newSize];
            int[][] B12 = new int[newSize][newSize];
            int[][] B21 = new int[newSize][newSize];
            int[][] B22 = new int[newSize][newSize];

            for (int i = 0; i < newSize; i++) {
                for (int j = 0; j < newSize; j++) {
                    A11[i][j] = A[i][j];
                    A12[i][j] = A[i][j + newSize];
                    A21[i][j] = A[i + newSize][j];
                    A22[i][j] = A[i + newSize][j + newSize];
                    B11[i][j] = B[i][j];
                    B12[i][j] = B[i][j + newSize];
                    B21[i][j] = B[i + newSize][j];
                    B22[i][j] = B[i + newSize][j + newSize];
                }
            }
            int[][] M1 = strassen(add(A11, A22), add(B11, B22));
            int[][] M2 = strassen(add(A21, A22), B11);
            int[][] M3 = strassen(A11, subtract(B12, B22));
            int[][] M4 = strassen(A22, subtract(B21, B11));
            int[][] M5 = strassen(add(A11, A12), B22);
            int[][] M6 = strassen(subtract(A21, A11), add(B11, B12));
            int[][] M7 = strassen(subtract(A12, A22), add(B21, B22));

            int[][] C11 = add(subtract(add(M1, M4), M5), M7);
            int[][] C12 = add(M3, M5);
            int[][] C21 = add(M2, M4);
            int[][] C22 = add(subtract(add(M1, M3), M2), M6);

            for (int i = 0; i < newSize; i++) {
                for (int j = 0; j < newSize; j++) {
                    C[i][j] = C11[i][j];
                    C[i][j + newSize] = C12[i][j];
                    C[i + newSize][j] = C21[i][j];
                    C[i + newSize][j + newSize] = C22[i][j];
                }
            }
        }
        return C;


    }

    static void printMatrix(int[][] matrix) {
        for (int[] row : matrix) {
            for (int val : row)
                System.out.print(val + " ");
            System.out.println();
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        
        int n = sc.nextInt();

        int[][] A = new int[n][n];
        int[][] B = new int[n][n];

        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                A[i][j] = sc.nextInt();

        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                B[i][j] = sc.nextInt();

        int[][] result = strassen(A, B);

        System.out.println("Result of Strassen Matrix Multiplication:");
        printMatrix(result);
    }
}

```

## Output:
<img width="1309" height="821" alt="Screenshot 2025-11-20 161203" src="https://github.com/user-attachments/assets/267a9637-68bb-4fc2-bd01-6ed333b9ba8a" />

## Result:
The program successfully implemented and the expected output is verified.
