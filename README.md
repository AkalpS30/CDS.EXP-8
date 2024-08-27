# CDS.EXP-8

## Aim:
**To study and implement C++ 2D Array - Matrices..**

## Software:
`Microsoft VSCode`

## Theory:
A data structure that is used to store colection of the itmas of same data type is known as an Array.
An array can be multidimensional also.
A multidimensional array is an array with more than one dimension. It is the homogeneous collection of items where each element is accessed using multiple indices.

A two-dimensional array in C++ is a collection of elements organized in rows and columns.
It can be visualised as a matrix, table or grid. Its each element can be accessed using two indices: one for the rows and the other for the columns.

Like a one-dimensional array, two-dimensional array indices also range from 0 to n-1 for both rows and columns.


## Code: 8A
```
#include<iostream> 
using namespace std; 

int main() 
{
    int a[4][4], i, j, k, l;
    for (i=0; i<4; i++) {
        for (j=0; j<4; j++) {
            cout<<"Enter elements: ("<<i<<j<<"):";
            cin>>a[i][j];
        }
    }
    for (k=0; k<4; k++) {
        for (l=0; l<4; l++) {
            cout<<a[k][l];
            cout<<" ";
        }
        cout<<"\n";
    }
}

```
## Output:
 ![Output8A](https://github.com/user-attachments/assets/6b45743e-03f1-421d-aa02-9879a8e0444d)
## Code: 8B 
```
#include <iostream>
using namespace std;

int main() {
    // Define matrix dimensions
    int r1 = 3, c1 = 3;
    int r2 = 3, c2 = 3;

    int m1[r1][c1], m2[r2][c2], sum[r1][c1];

    cout << "Enter elements of the first matrix:" << endl;
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m1[i][j];
        }
    }
    cout << "Enter elements of the second matrix:" << endl;
    for (int i = 0; i < r2; ++i) {
        for (int j = 0; j < c2; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m2[i][j];
        }
    }

    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            sum[i][j] = m1[i][j] + m2[i][j];
        }
    }
 

    cout << endl << "Sum of matrices:" << endl;
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            cout << sum[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

## Output:
![Output8B](https://github.com/user-attachments/assets/4d04609b-901b-4bc5-9e56-7c4e98bc4de0)

## Code: 8C 
```
#include <iostream>
using namespace std;

int main() {
    // Define matrix dimensions
    int r1 = 2, c1 = 2;
    int r2 = 2, c2 = 2;

    int m1[r1][c1], m2[r2][c2], sub[r1][c1];

    cout << "Enter elements of the first matrix:" << endl;
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m1[i][j];
        }
    }
    cout << "Enter elements of the second matrix:" << endl;
    for (int i = 0; i < r2; ++i) {
        for (int j = 0; j < c2; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m2[i][j];
        }
    }

    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            sub[i][j] = m1[i][j] -  m2[i][j];
        }
    }
 

    cout << endl << "Difference of the matrices is: " << endl;
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            cout << sub[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}

```
## Output:
![Output8C](https://github.com/user-attachments/assets/6dbb527f-ce17-4aba-9674-72d44c2a504a)
## Code: 8D 
```
#include <iostream>
using namespace std;


const int MAX = 100;

void printDiagonalSums(int mat[][MAX], int n) 
{ 
    int principal = 0;
    
    for (int i = 0; i < n; i++)  
    { 
        // Condition for principal diagonal 
        principal += mat[i][i]; 
    } 
  
    cout << "Sum of the diagonal elements is: " << principal << endl; 
} 

int main() 
{ 
    int a[][MAX] = {{1, 2, 3, 4},  
                    {8, 7, 6, 5},  
                    {2, 1, 4, 3},  
                    {5, 6, 7, 8}}; 
    printDiagonalSums(a, 4); 
    return 0; 
}

```
## Output:
![Output8D](https://github.com/user-attachments/assets/3abf38ca-7ca3-4e15-b00f-912084377792)

## Code 8E
```
// Multiplication of two matrices. 

#include<iostream> 
using namespace std; 

int main() 
{
      int r1, c1, r2, c2;
    
    // Input dimensions of the first matrix
    cout << "Enter rows and columns for the first matrix: ";
    cin >> r1 >> c1;

    // Input dimensions of the second matrix
    cout << "Enter rows and columns for the second matrix: ";
    cin >> r2 >> c2;

    // Check if matrix multiplication is possible
    if (c1 != r2) {
        cout << "Matrix multiplication not possible!" << endl;
        return 0;
    }

    // Define the matrices
    int m1[r1][c1], m2[r2][c2], result[r1][c2];

    // Input elements of the first and second matrix
    cout << "Enter elements of the first matrix:" << endl;
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m1[i][j];
        }
    }
    cout << "Enter elements of the second matrix:" << endl;
    for (int i = 0; i < r2; ++i) {
        for (int j = 0; j < c2; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m2[i][j];
        }
    } 
    // Initialize the result matrix with zeros
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            result[i][j] = 0;
        }
    }

    // Matrix multiplication
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            for (int k = 0; k < c1; k++) {
                result[i][j] += m1[i][k] * m2[k][j];
            }
        }
    }

    // Display the result
    cout << "Resultant matrix:\n";
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            cout << result[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
} 
```
## Output:
![Output8E](https://github.com/user-attachments/assets/e1ee2b0a-e00b-4866-894c-f271ea1f7fee)
## Code 8F.
```
// To find the transpose of a matrix. 

#include<iostream> 
using namespace std;      

int main() 
{
    int r, c ;

    // Getting the size of the matrix
    cout << "Enter the number of rows and columns of the matrix: ";
    cin >> r  >> c ;

    int m[r][c], transpose[c][r];

    // Getting elements of the matrix
    cout << "Enter elements of the first matrix:" << endl;
    for (int i = 0; i < r; ++i) {
        for (int j = 0; j < c; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m[i][j];
        }
    }

    // Transposing the matrix
    for(int i = 0; i < r; ++i) {
        for(int j = 0; j < c; ++j) {
            transpose[j][i] = m[i][j];
        }
    }

    // Displaying the transpose of the matrix
    cout << "\nTranspose of the matrix:" << endl;
    for(int i = 0; i < c; ++i) {
        for(int j = 0; j < r; ++j) {
            cout << transpose[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
} 
```
## Output:
![Output8F](https://github.com/user-attachments/assets/ddad458e-6869-4f8c-820d-a180042c9a46)

## Conclusion:
I learnt about the various operations performed on matrices and how we can do the same in C++ using two-dimensional arrays.
