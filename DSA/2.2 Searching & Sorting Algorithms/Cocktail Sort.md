# **COCKTAIL SORT**
Cocktail Sort is a Bubble Sort variant. The Bubble sort algorithm always begs from the left and transfers the largest element to its proper location in the first iteration, then the second largest in the second, and so on. Cocktail Sort alternates between traversing an array in both ways.

## Algorithm

#### *The algorithm is divided into two steps for each iteration*:

Step 1 : It is similar to the Bubble Sort, cycles across the array from left to right. During the loop, neighboring items are compared, and values are exchanged if the value on the left is larger than the value on the right. The greatest number will be at the last of the array at the conclusion of the first iteration.

Step 2 : It cycles over the array in the reverse direction, beginning with the item immediately preceding the most recently sorted item and returning to the beginning. Similarly, neighboring items are compared and, if necessary, switched.


![download](https://www.linkpicture.com/q/ezgif.com-gif-maker_25.jpg)


## Code :-
```
#include <stdio.h>
void sort_cocktail(int l[], int n)  
{   
    // argument passed is the list of the array to be sorted and the length of the array

    // first is used to represent the starting index of the array
    int first = 0;
    int temp = 0;
    // last is used to represent the last index of the array
    int last = n - 1;
    // p is the variable used to check if the array contains sorted elements after sorting process
    int p = 1;
    while ( p != 0)
    {
        // while loop checks the status of the array
        p = 0;
        for (int i = first; i < last; ++i)
        {
        // for loop is used to do the forward sorting on the array
            if (l[i] > l[i + 1])
            {
                // larger element is exchanged with smaller one
                temp = l[i];
                l[i] = l[i+1];
                l[i+1] = temp;
                p = 1;
            }
            // after every sorting, largest element is at the last index and value of p is set to 1
        }
        if (! p)
        // if value is not 1, it means the array is sorted already , so the control is sent out of while loop
            break;
        else
        {
        // value of last is decreased by 1 as largest element need not to be sorted
            p = 0;
            last--;
        }
        for (int i = last; i >= first; --i)
        {
        // for loop is used to do backward sort on the array
            if (l[i] > l[i + 1])
            {
                temp = l[i];
                l[i] = l[i+1];
                l[i+1] = temp;
                p = 1;
            }
        }
        // the smallest element is placed at the front of the array, so the value of first variable is increased by 1
        first++;
    }
    for (int i = 0; i < n; ++i)
    // for loop is used to display the sorted array elements
        printf("%d ", l[i]);
    printf("\n");
}
 
int main()
{
    int n;
    printf("Enter the size of the array: ");
    scanf("%d",&n);
    int A[n];
    printf("\nEnter the elements of array: ");
    for(int i=0;i<n;i++)       
	  {
		    scanf("%d",&A[i]);
	  }
    sort_cocktail(A, n);
    return 0;
}
```
## Output :-
```
Enter the size of the array :10
Enter the array elements:1 3 2 8 5 1 5 1 2 7
1 1 1 2 2 3 5 5 7 8
```
## Time Complexity :-
- Best Case	- O(n)
- Average Case  -	O(n*n)
- Worst Case  -  O(n*n)

## Space Complexity :-
- Space Complexity - O(1)

## References :-
- http://will.thimbleby.net/algorithms/doku.php?id=cocktail_sort
- https://en.wikipedia.org/wiki/Cocktail_shaker_sort
- https://www.tutorialspoint.com/cplusplus-program-for-cocktail-sort
