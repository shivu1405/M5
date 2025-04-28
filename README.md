EX-21-POINTERS
# AIM:
Write a C program to convert a 23.65 into 25 using pointer

## ALGORITHM:
1.	Declare a double variable to hold the floating-point number (23.65).
2.	Declare a pointer to double to point to the address of the variable.
3.	Use the pointer to modify the value to 25.0.
4.	Print the modified value.

## PROGRAM:
```
#include <stdio.h>

int main() {
    float number = 23.65;
    float *ptr = &number;  // Pointer to the number

    // Print the original value
    printf("Original number: %.2f\n", *ptr);

    // Modify the value using the pointer to make it 25
    *ptr = 25;

    // Print the modified value
    printf("Modified number: %.2f\n", *ptr);

    return 0;
}

```
## OUTPUT:
 	
![image](https://github.com/user-attachments/assets/f49d9fb5-adc9-4e58-8341-06ca69aae33c)

## RESULT:
Thus the program to convert a 23.65 into 25 using pointer has been executed successfully.
 
 


# EX-22-FUNCTIONS AND STORAGE CLASS

## AIM:

Write a C program to calculate the Product of first 12 natural numbers using Recursion

## ALGORITHM:

1.	Define a recursive function calculateProduct that takes an integer parameter n.
2.	Return n multiplied by the result of the calculateProduct function called with n - 1.
3.	Declare an integer variable n and an unsigned long long variable product.
4.	Initialize n with the value 12 (for the first 12 natural numbers).
5.	Call the calculateProduct function with n and store the result in the product variable.
6.	Print the result, indicating it is the product of the first 12 natural numbers.

## PROGRAM:
```
#include <stdio.h>

// Function to calculate the product of the first n natural numbers
long long product(int n) {
    // Base case: when n is 1, the product is 1
    if (n == 1)
        return 1;
    else
        return n * product(n - 1);  // Recursive call
}

int main() {
    int n = 12;
    long long result;

    // Call the product function and calculate the product of the first 12 natural numbers
    result = product(n);

    // Print the result
    printf("The product of the first %d natural numbers is: %lld\n", n, result);

    return 0;
}

```
## OUTPUT:
  ![image](https://github.com/user-attachments/assets/ca676660-cec1-44a6-8796-55d193e5228f)
       		
## RESULT:

Thus the program has been executed successfully.
 
 


# EX-23-ARRAYS AND ITS OPERATIONS

## AIM:

Write C Program to find Sum of each row of a Matrix

## ALGORITHM:

1.	Declare and initialize the matrix with the desired values.
2.	Create a loop to iterate through each row of the matrix.
3.	Inside the loop, calculate the sum of the elements in each row.
4.	Print the sum for each row.

## PROGRAM:
```
#include <stdio.h>

int main() {
    int rows, cols;

    // Input number of rows and columns
    printf("Enter the number of rows: ");
    scanf("%d", &rows);
    
    printf("Enter the number of columns: ");
    scanf("%d", &cols);

    // Declare the matrix
    int matrix[rows][cols];

    // Input elements of the matrix
    printf("Enter the elements of the matrix:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            printf("Element at [%d][%d]: ", i + 1, j + 1);
            scanf("%d", &matrix[i][j]);
        }
    }

    // Calculate the sum of each row
    printf("\nSum of each row:\n");
    for (int i = 0; i < rows; i++) {
        int rowSum = 0;  // Initialize row sum
        for (int j = 0; j < cols; j++) {
            rowSum += matrix[i][j];  // Add each element in the row
        }
        printf("Sum of row %d: %d\n", i + 1, rowSum);  // Print the sum of the row
    }

    return 0;
}

```


## OUTPUT

![image](https://github.com/user-attachments/assets/bfcab53f-5a09-4585-9d01-bfdcb331aa5c)


 ## RESULT
 Thus C Program is executed successfully 


# EX-24-STRINGS

## AIM:

Write C program for the below pyramid string pattern. Enter a string: PROGRAM Enter number of rows: 5 P R O G R A M P R O G R A M P R O G R A M

## ALGORITHM:

1.	Input the number of rows for the pyramid (e.g., num_rows).
2.	Initialize variables:i for the row count (starting from 1),j for the character count (starting from 1)
3.	Start a loop for i from 1 to num_rows (for each row of the pyramid).
4.	Calculate the midpoint position as midpoint = (2 * num_rows - 1) / 2.
5.	End the program.

## PROGRAM:
```
#include <stdio.h>
#include <string.h>

int main() {
    char str[100];
    int rows;

    // Input the string and the number of rows
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';  // Remove the newline character from fgets input

    printf("Enter number of rows: ");
    scanf("%d", &rows);

    int len = strlen(str);  // Length of the string

    // Loop through each row
    for (int i = 1; i <= rows; i++) {
        // Print the characters in each row
        for (int j = 0; j < i; j++) {
            // Print the characters of the string in a cyclic manner
            printf("%c ", str[(j) % len]);
        }
        printf("\n");
    }

    return 0;
}

```

 ## OUTPUT
![image](https://github.com/user-attachments/assets/8b680e1d-c078-4e55-8687-72469ffd023e)

 

## RESULT

Thus the C program to String process executed successfully
 

 
.



# EX -25 –DISPLAYING ARRAYS USING POINTERS
## AIM

Write a c program to read and display an array of any 6 integer elements using pointer

## ALGORITHM
Step 1: Start the program.
Step 2: Declare the following:
•	Integer variable i for iteration.
•	Integer variable n to store the number of elements.
•	Integer array arr[10] to hold up to 10 elements.
•	Integer pointer parr and initialize it to point to the array arr.
Step 3: Read the value of n (number of elements) from the user.
Step 4: Loop from i = 0 to i < n:
•	Read an integer value and store it in the address parr + i using pointer arithmetic.
Step 5: Loop from i = 0 to i < n:
•	Print the element at *(parr + i) using pointer dereferencing.
Step 6: End the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    int arr[6];         // Array of 6 integers
    int *ptr = arr;     // Pointer to the first element of the array

    // Input the elements of the array
    printf("Enter 6 integer elements:\n");
    for (int i = 0; i < 6; i++) {
        printf("Element %d: ", i + 1);
        scanf("%d", (ptr + i));  // Using pointer arithmetic to store the value
    }

    // Display the elements of the array
    printf("\nThe elements of the array are:\n");
    for (int i = 0; i < 6; i++) {
        printf("Element %d: %d\n", i + 1, *(ptr + i));  // Using pointer arithmetic to access the value
    }

    return 0;
}

```
## OUTPUT
![image](https://github.com/user-attachments/assets/a213e699-5d4b-42f7-9560-23a34c8bb55d)


## RESULT

Thus the C program to read and display an array of any 6 integer elements using pointer has been executed


