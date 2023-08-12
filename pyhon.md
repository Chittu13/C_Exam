# CS 103 Re-exam Practice Question 


### 1) Write a C program to add three decimal numbers taking the numbers as input from the user. 

``` c
#include <stdio.h>

int main() {
    int num1, num2, num3, sum;

    printf("Enter three decimal numbers:\n");
    scanf("%d %d  %d", &num1, &num2, &num3);

    sum = num1 + num2 + num3;

    printf("Sum = %d\n", sum);

    return 0;
}
```

### 2) Write a C program to print "POSITIVE" if a given number taken as input from the user is greater than 0, print NEGATIVE if number is less than 0 ,and print ZERO if number is equal to 0 


``` c
#include <stdio.h>

int main() {
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if (number > 0) {
        printf("POSITIVE\n");
    } else if (number < 0) {
        printf("NEGATIVE\n");
    } else {
        printf("ZERO\n");
    }

    return 0;
}

```

### 3) Write a program to find a sum of odd numbers starting from 1 to a given positive integer taken as input (inclusive of both numbers) Eg. input = 10, program should output 1+3+5+7+9 = 25......OUTPUT is 25 



``` c

#include <stdio.h>

int main() {
    int number, sum = 0;

    printf("Enter a positive integer: ");
    scanf("%d", &number);
    int total=0;

    for (int i = 1; i <= number; i++) {
        if(i%2==1){
            total=total+i;
        }
        }
    

    printf("Sum of odd numbers:  %d", total);

    return 0;
}
```
### 4) Write a program to count the number of digits in a given integer number taken as input from the user. Eg. input = 256; Output = 3; input = 98754, output = 5 (program should be generic to take any number of digits) 



``` c
#include <stdio.h>
#include <string.h>

int main() {
    char str[100];
    
    printf("Enter a number: ");
    scanf("%s", str);

    int length = strlen(str);

    printf("Length is: %d\n", length);

    return 0;
}

```

### 5) Write a program to add given two matrices A and B where both A and B are 2x2 matrix. Program should take matrices as input from user and print the resultant matrix C 


``` c
#include <stdio.h>

int main() {
    int matrixA[2][2], matrixB[2][2], matrixC[2][2];

    printf("Enter the elements of matrix A:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            scanf("%d", &matrixA[i][j]);
        }
    }

    printf("Enter the elements of matrix B:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            scanf("%d", &matrixB[i][j]);
        }
    }

    
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            matrixC[i][j] = matrixA[i][j] + matrixB[i][j];
        }
    }

    printf("Resultant matrix C after addition:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            printf("%d ", matrixC[i][j]);
        }
        printf("\n");
    }

    return 0;
}

```

### 6) Write a program to print "YES" if a number given as input is a multiple of 5 and print "NO" if number is not a multiple of 5. 



``` c
#include <stdio.h>

int main() {
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if (number % 5 == 0) {
        printf("YES\n");
    } else {
        printf("NO\n");
    }

    return 0;
}

```


### 7) Write a program to convert a given decimal number taken as input from the user to binary form. 



``` c
#include <stdio.h>

int main() {
    int decimal, binary[32], i = 0;

    printf("Enter a decimal number: ");
    scanf("%d", &decimal);

    while (decimal > 0) {
        binary[i] = decimal % 2;
        decimal /= 2;
        i++;
    }

    printf("Binary representation: ");
    
    if (i == 0) {
        printf("0");
    } else {
        for (int j = i - 1; j >= 0; j--) {
            printf("%d", binary[j]);
        }
    }

    printf("\n");

    return 0;
}

```


### 8) Write a program to create a structure with name (str 25), ID(int), marks (decimal)). Take input details of 3 students and print the average of the marks


``` c
#include <stdio.h>

struct Student {
    char name[25];
    int ID;
    float marks;
};

int main() {
    struct Student students[3];
    float totalMarks = 0.0;

    printf("Enter details of 3 students:\n");

    
    for (int i = 0; i < 3; i++) {
        printf("Student %d:\n", i + 1);
        printf("Name: ");
        scanf("%s", students[i].name);
        printf("ID: ");
        scanf("%d", &students[i].ID);
        printf("Marks: ");
        scanf("%f", &students[i].marks);

        totalMarks += students[i].marks;
    }

    
    float averageMarks = totalMarks / 3;

    printf("\nAverage marks: %.2f\n", averageMarks);

    return 0;
}

```
