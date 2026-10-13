# DAY-9-C




## 1. Write a C program to check whether a given number is a strong number or not.

Program:

c
```
#include <stdio.h>

int main()
{
    int n, temp, digit, i, fact, sum = 0;

    printf("Enter a number: ");
    scanf("%d", &n);

    temp = n;

    while (temp > 0)
    {
        digit = temp % 10;
        fact = 1;

        for (i = 1; i <= digit; i++)
        {
            fact = fact * i;
        }

        sum = sum + fact;
        temp = temp / 10;
    }

    if (sum == n)
        printf("%d is a Strong Number", n);
    else
        printf("%d is not a Strong Number", n);

    return 0;
}
```

Output:

text
```
Enter a number: 145
145 is a Strong Number
```

## 2. Write a C program to find the second-largest element in an array without sorting the array.

Program:

c
```
#include <stdio.h>
#include <limits.h>

int main()
{
    int a[100], n, i;
    int largest = INT_MIN;
    int second = INT_MIN;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    printf("Enter array elements: ");
    for (i = 0; i < n; i++)
    {
        scanf("%d", &a[i]);

        if (a[i] > largest)
        {
            second = largest;
            largest = a[i];
        }
        else if (a[i] > second && a[i] < largest)
        {
            second = a[i];
        }
    }

    if (second == INT_MIN)
        printf("Second largest element does not exist");
    else
        printf("Second largest element = %d", second);

    return 0;
}
```

Output:

text
```
Enter the number of elements: 5
Enter array elements: 10 25 8 40 30
Second largest element = 30
```

## 3. Write a C program to check whether a given number is a palindrome number and print the reverse of the number using loops.

Program:

c
```
#include <stdio.h>

int main()
{
    int n, temp, digit, reverse = 0;

    printf("Enter a number: ");
    scanf("%d", &n);

    temp = n;

    while (temp > 0)
    {
        digit = temp % 10;
        reverse = reverse * 10 + digit;
        temp = temp / 10;
    }

    printf("Reverse of the number = %d\n", reverse);

    if (n == reverse)
        printf("%d is a Palindrome Number", n);
    else
        printf("%d is not a Palindrome Number", n);

    return 0;
}
```

Output:

text
```
Enter a number: 121
Reverse of the number = 121
121 is a Palindrome Number
```
