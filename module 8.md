EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

```
#include <stdio.h>

int main() {
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    switch(n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 7:
            printf("seventy three\n");
            break;
        case 8:
            printf("seventy four\n");
            break;
        case 9:
            printf("seventy five\n");
            break;
        case 10:
            printf("seventy six\n");
            break;
        case 11:
            printf("seventy seven\n");
            break;
        case 12:
            printf("seventy eight\n");
            break;
        case 13:
            printf("seventy nine\n");
            break;
        default:
            printf("greater than 13\n");
            break;
    }

    return 0;
}
```




Output:


<img width="676" height="309" alt="Screenshot 2025-09-17 094159" src="https://github.com/user-attachments/assets/47494aea-d379-44ba-896e-7661150b0f49" />







Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
```
#include <stdio.h>
#include <string.h>

int main() {
    char a[50];
    int count[10] = {0};  
    int i;

    
    printf("Enter a string containing digits: ");
    scanf("%s", a);

    
    for(i = 0; i < strlen(a); i++) {
        if(a[i] >= '0' && a[i] <= '9') {
            count[a[i] - '0']++;
        }
    }

    
    for(i = 0; i < 10; i++) {
        printf("%d ", count[i]);
    }
    printf("\n");

    return 0;
}
```




Output:


<img width="812" height="250" alt="Screenshot 2025-09-17 094656" src="https://github.com/user-attachments/assets/f35af678-2285-47f4-b350-209e789a1265" />







Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <stdbool.h>

void swap(char *a, char *b) {
    char temp = *a;
    *a = *b;
    *b = temp;
}

void reverse(char str[], int start, int end) {
    while (start < end) {
        swap(&str[start], &str[end]);
        start++;
        end--;
    }
}

bool next_permutation(char str[], int n) {
    int i = n - 2;

    while (i >= 0 && str[i] >= str[i + 1]) {
        i--;
    }

    if (i < 0) return false; 

    int j = n - 1;
    while (str[j] <= str[i]) {
        j--;
    }

    swap(&str[i], &str[j]);

    reverse(str, i + 1, n - 1);

    return true;
}

int main() {
    char s[50];
    int n;

    printf("Enter a string: ");
    scanf("%s", s);

    n = strlen(s);

    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (s[i] > s[j]) {
                swap(&s[i], &s[j]);
            }
        }
    }

    do {
        printf("%s\n", s);
    } while (next_permutation(s, n));

    return 0;
}
```



Output:


<img width="581" height="573" alt="Screenshot 2025-09-17 095040" src="https://github.com/user-attachments/assets/3e896e64-2104-464a-85f7-3ae9eb9ca36f" />







Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

```
// EXP NO:9
// C program to print a pattern of numbers from 1 to n

#include <stdio.h>

int main() {
    int n, i, j, len, min;

    printf("Enter n: ");
    scanf("%d", &n);

    len = 2 * n - 1;

    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
           
            int top = i;
            int left = j;
            int bottom = len - 1 - i;
            int right = len - 1 - j;

            min = top;
            if (left < min) min = left;
            if (bottom < min) min = bottom;
            if (right < min) min = right;

            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```




Output:


<img width="493" height="266" alt="Screenshot 2025-09-17 101457" src="https://github.com/user-attachments/assets/e2af770e-e820-42c6-b50c-2173fc777972" />







Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

```
#include <stdio.h>

// Function definition
int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;  // return the square
}

int main() {
    int result;

    // Function call
    result = square();

    // Display the result
    printf("Square = %d\n", result);

    return 0;
}
```




Output:


<img width="299" height="94" alt="Screenshot 2025-09-17 101649" src="https://github.com/user-attachments/assets/1492f512-7a48-4680-a251-242f4a56a70b" />







Result:
Thus, the program is verified successfully



























