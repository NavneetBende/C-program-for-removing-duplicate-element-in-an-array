Removing Duplicate element in an Array
Here, in this page we will discuss the program for Removing Duplicate Element in an array in C programming language. We will discuss two ways for solving this problem. We are given with an array and need to print the array after removing the duplicate elements.

While loop in C
Here, we will discuss the following two methods, for removing the duplicate elements from the given array.

Method 1 : Using Auxiliary space.
Method 2 : Without using extra space
Now, let’s discuss the above two methods in brief,

Method 1 :
Declare an array say temp[], as an auxiliary array.
Traverse input array and one by one copy unique elements of arr[] to temp[]. Also keep track of count of unique elements. Let this count be j
Copy j elements from temp[] to arr[] and return j.
Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(n)
Related Pages
Finding  Repeating elements in an Array

Finding Non Repeating elements in an Array

Finding Minimum scalar product of two vectors

Finding Maximum scalar product of two vectors in an array 

Counting the number of even and odd elements in an array 

Method 1 : Code in C
Run
#include <stdio.h>

int duplicates(int arr[], int n)
{
   if (n==0 || n==1)
     return n;

   int temp[n];

   int j = 0;
   for (int i=0; i<n-1; i++)
      if (arr[i] != arr[i+1])
         temp[j++] = arr[i];

   temp[j++] = arr[n-1];

   for (int i=0; i<j; i++)
     arr[i] = temp[i];

   return j;
}

// Driver code
int main()
{
   int arr[] = {10, 20, 20, 30, 40, 40, 40, 50, 50};
   int n = sizeof(arr) / sizeof(arr[0]);

   n = duplicates(arr, n);

   for (int i=0; i<n; i++)
      printf("%d ", arr[i]);

   return 0;
}
Output
10 20 30 40 50
Method 2 (Efficient Approach) :
In this method we will maintain a separate index for same array as maintained for different array in Method 1

Method 2 : Code in C
Run
#include <stdio.h>

int duplicates(int arr[], int n)
{
    if (n==0 || n==1)
    return n;

    int j = 0;

    for (int i=0; i<n-1; i++)
       if (arr[i] != arr[i+1])
           arr[j++] = arr[i];

    arr[j++] = arr[n-1];

    return j;
}

// Driver code
int main()
{
     int arr[] = {10, 20, 20, 30, 40, 40, 40, 50, 50};
     int n = sizeof(arr) / sizeof(arr[0]);

     n = duplicates(arr, n);

     for (int i=0; i<n; i++)
       printf("%d ", arr[i]);

     return 0;
}
Output
10 20 30 40 50
