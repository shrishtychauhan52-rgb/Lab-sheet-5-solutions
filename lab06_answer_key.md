# BCA111P Lab Sheet-06 - Answer Key

## p01_input_display_1d.cpp
```cpp
// Program 1: Input and display elements of a 1D array
#include <iostream>
using namespace std;
int main() {
    int arraySize, numbers[100];
    cout << "Enter number of elements: ";
    cin >> arraySize;
    for (int index = 0; index < arraySize; index++) {
        cout << "Enter element " << index + 1 << ": ";
        cin >> numbers[index];
    }
    cout << "Array elements: ";
    for (int index = 0; index < arraySize; index++)
        cout << numbers[index] << " ";
    cout << endl;
    return 0;
}
```

## p02_sum_1d.cpp
```cpp
// Program 2: Sum of all elements in a 1D array
#include <iostream>
using namespace std;
int main() {
    int arraySize, numbers[100], totalSum = 0;
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " elements: ";
    for (int index = 0; index < arraySize; index++) {
        cin >> numbers[index];
        totalSum += numbers[index];   // accumulate running total
    }
    cout << "Sum = " << totalSum << endl;
    return 0;
}
```

## p03_max_min.cpp
```cpp
// Program 3: Maximum and minimum element in a 1D array
#include <iostream>
using namespace std;
int main() {
    int arraySize, numbers[100];
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " elements: ";
    for (int index = 0; index < arraySize; index++) cin >> numbers[index];

    int maximumValue = numbers[0], minimumValue = numbers[0];
    for (int index = 1; index < arraySize; index++) {
        if (numbers[index] > maximumValue) maximumValue = numbers[index];
        if (numbers[index] < minimumValue) minimumValue = numbers[index];
    }
    cout << "Maximum = " << maximumValue << endl;
    cout << "Minimum = " << minimumValue << endl;
    return 0;
}
```

## p04_reverse.cpp
```cpp
// Program 4: Reverse a 1D array (in place)
#include <iostream>
using namespace std;
int main() {
    int arraySize, numbers[100];
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " elements: ";
    for (int index = 0; index < arraySize; index++) cin >> numbers[index];

    // swap first with last, second with second-last, ...
    for (int left = 0, right = arraySize - 1; left < right; left++, right--) {
        int temporary = numbers[left];
        numbers[left] = numbers[right];
        numbers[right] = temporary;
    }
    cout << "Reversed array: ";
    for (int index = 0; index < arraySize; index++) cout << numbers[index] << " ";
    cout << endl;
    return 0;
}
```

## p05_even_odd_count.cpp
```cpp
// Program 5: Input 10 numbers and count even and odd
#include <iostream>
using namespace std;
int main() {
    const int ARRAY_SIZE = 10;
    int numbers[ARRAY_SIZE], evenCount = 0, oddCount = 0;
    cout << "Enter 10 numbers: ";
    for (int index = 0; index < ARRAY_SIZE; index++) {
        cin >> numbers[index];
        if (numbers[index] % 2 == 0) evenCount++;
        else oddCount++;
    }
    cout << "Even numbers: " << evenCount << endl;
    cout << "Odd numbers: " << oddCount << endl;
    return 0;
}
```

## p06_search_no_function.cpp
```cpp
// Program 6: Search an element in a 1D array (without functions)
#include <iostream>
using namespace std;
int main() {
    int arraySize, numbers[100], searchKey, foundPosition = -1;
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " elements: ";
    for (int index = 0; index < arraySize; index++) cin >> numbers[index];
    cout << "Enter element to search: ";
    cin >> searchKey;

    for (int index = 0; index < arraySize; index++) {
        if (numbers[index] == searchKey) { foundPosition = index; break; }
    }
    if (foundPosition != -1)
        cout << "Element found at position " << foundPosition + 1 << endl;
    else
        cout << "Element not found" << endl;
    return 0;
}
```

## p07_input_display_2d.cpp
```cpp
// Program 7: Input and display a 2D array (matrix)
#include <iostream>
using namespace std;
int main() {
    int rowCount, columnCount, matrix[10][10];
    cout << "Enter rows and columns: ";
    cin >> rowCount >> columnCount;
    cout << "Enter matrix elements:" << endl;
    for (int row = 0; row < rowCount; row++)
        for (int column = 0; column < columnCount; column++)
            cin >> matrix[row][column];

    cout << "Matrix:" << endl;
    for (int row = 0; row < rowCount; row++) {
        for (int column = 0; column < columnCount; column++)
            cout << matrix[row][column] << "\t";
        cout << endl;
    }
    return 0;
}
```

## p08_add_matrices.cpp
```cpp
// Program 08: Add two matrices
#include <iostream>
using namespace std;
int main() {
    int rowCount, columnCount, matrixA[10][10], matrixB[10][10], resultMatrix[10][10];
    cout << "Enter rows and columns: ";
    cin >> rowCount >> columnCount;
    cout << "Enter elements of first matrix:" << endl;
    for (int row = 0; row < rowCount; row++)
        for (int column = 0; column < columnCount; column++) cin >> matrixA[row][column];
    cout << "Enter elements of second matrix:" << endl;
    for (int row = 0; row < rowCount; row++)
        for (int column = 0; column < columnCount; column++) cin >> matrixB[row][column];

    // element-wise operation
    for (int row = 0; row < rowCount; row++)
        for (int column = 0; column < columnCount; column++)
            resultMatrix[row][column] = matrixA[row][column] + matrixB[row][column];

    cout << "Resultant matrix (sum):" << endl;
    for (int row = 0; row < rowCount; row++) {
        for (int column = 0; column < columnCount; column++)
            cout << resultMatrix[row][column] << "\t";
        cout << endl;
    }
    return 0;
}
```

## p09_subtract_matrices.cpp
```cpp
// Program 09: Subtract two matrices
#include <iostream>
using namespace std;
int main() {
    int rowCount, columnCount, matrixA[10][10], matrixB[10][10], resultMatrix[10][10];
    cout << "Enter rows and columns: ";
    cin >> rowCount >> columnCount;
    cout << "Enter elements of first matrix:" << endl;
    for (int row = 0; row < rowCount; row++)
        for (int column = 0; column < columnCount; column++) cin >> matrixA[row][column];
    cout << "Enter elements of second matrix:" << endl;
    for (int row = 0; row < rowCount; row++)
        for (int column = 0; column < columnCount; column++) cin >> matrixB[row][column];

    // element-wise operation
    for (int row = 0; row < rowCount; row++)
        for (int column = 0; column < columnCount; column++)
            resultMatrix[row][column] = matrixA[row][column] - matrixB[row][column];

    cout << "Resultant matrix (difference):" << endl;
    for (int row = 0; row < rowCount; row++) {
        for (int column = 0; column < columnCount; column++)
            cout << resultMatrix[row][column] << "\t";
        cout << endl;
    }
    return 0;
}
```

## p10_multiply_matrices.cpp
```cpp
// Program 10: Multiply two matrices
#include <iostream>
using namespace std;
int main() {
    int rowsA, columnsA, rowsB, columnsB;
    int matrixA[10][10], matrixB[10][10], productMatrix[10][10];
    cout << "Enter rows and columns of first matrix: ";
    cin >> rowsA >> columnsA;
    cout << "Enter rows and columns of second matrix: ";
    cin >> rowsB >> columnsB;

    // multiplication needs columns of A == rows of B
    if (columnsA != rowsB) {
        cout << "Multiplication not possible" << endl;
        return 0;
    }
    cout << "Enter elements of first matrix:" << endl;
    for (int row = 0; row < rowsA; row++)
        for (int column = 0; column < columnsA; column++) cin >> matrixA[row][column];
    cout << "Enter elements of second matrix:" << endl;
    for (int row = 0; row < rowsB; row++)
        for (int column = 0; column < columnsB; column++) cin >> matrixB[row][column];

    for (int row = 0; row < rowsA; row++)
        for (int column = 0; column < columnsB; column++) {
            productMatrix[row][column] = 0;
            for (int k = 0; k < columnsA; k++)
                productMatrix[row][column] += matrixA[row][k] * matrixB[k][column];
        }

    cout << "Product matrix:" << endl;
    for (int row = 0; row < rowsA; row++) {
        for (int column = 0; column < columnsB; column++)
            cout << productMatrix[row][column] << "\t";
        cout << endl;
    }
    return 0;
}
```

## p11_bubble_sort_ascending.cpp
```cpp
// Program 11: Bubble Sort in ascending order
#include <iostream>
using namespace std;
int main() {
    int arraySize, numbers[100];
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " elements: ";
    for (int index = 0; index < arraySize; index++) cin >> numbers[index];

    for (int pass = 0; pass < arraySize - 1; pass++) {
        bool swapped = false;
        for (int index = 0; index < arraySize - pass - 1; index++) {
            if (numbers[index] > numbers[index + 1]) {
                int temporary = numbers[index];
                numbers[index] = numbers[index + 1];
                numbers[index + 1] = temporary;
                swapped = true;
            }
        }
        if (!swapped) break;   // already sorted
    }
    cout << "Sorted array (ascending): ";
    for (int index = 0; index < arraySize; index++) cout << numbers[index] << " ";
    cout << endl;
    return 0;
}
```

## p12_bubble_sort_descending.cpp
```cpp
// Program 12: Bubble Sort in descending order
#include <iostream>
using namespace std;
int main() {
    int arraySize, numbers[100];
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " elements: ";
    for (int index = 0; index < arraySize; index++) cin >> numbers[index];

    for (int pass = 0; pass < arraySize - 1; pass++) {
        bool swapped = false;
        for (int index = 0; index < arraySize - pass - 1; index++) {
            if (numbers[index] < numbers[index + 1]) {
                int temporary = numbers[index];
                numbers[index] = numbers[index + 1];
                numbers[index + 1] = temporary;
                swapped = true;
            }
        }
        if (!swapped) break;   // already sorted
    }
    cout << "Sorted array (descending): ";
    for (int index = 0; index < arraySize; index++) cout << numbers[index] << " ";
    cout << endl;
    return 0;
}
```

## p13_sort_names_bubble.cpp
```cpp
// Program 13: Sort names of students using Bubble Sort
#include <iostream>
#include <string>
using namespace std;
int main() {
    int studentCount;
    string studentNames[100];
    cout << "Enter number of students: ";
    cin >> studentCount;
    cout << "Enter names (one word each): " << endl;
    for (int index = 0; index < studentCount; index++) cin >> studentNames[index];

    for (int pass = 0; pass < studentCount - 1; pass++)
        for (int index = 0; index < studentCount - pass - 1; index++)
            if (studentNames[index] > studentNames[index + 1]) {   // alphabetical compare
                string temporary = studentNames[index];
                studentNames[index] = studentNames[index + 1];
                studentNames[index + 1] = temporary;
            }

    cout << "Sorted names:" << endl;
    for (int index = 0; index < studentCount; index++) cout << studentNames[index] << endl;
    return 0;
}
```

## p14_linear_search.cpp
```cpp
// Program 14: Linear Search in a 1D array
#include <iostream>
using namespace std;
int linearSearch(int numbers[], int arraySize, int searchKey) {
    for (int index = 0; index < arraySize; index++)
        if (numbers[index] == searchKey) return index;
    return -1;
}
int main() {
    int arraySize, numbers[100], searchKey;
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " elements: ";
    for (int index = 0; index < arraySize; index++) cin >> numbers[index];
    cout << "Enter element to search: ";
    cin >> searchKey;
    int position = linearSearch(numbers, arraySize, searchKey);
    if (position != -1) cout << "Found at position " << position + 1 << endl;
    else cout << "Not found" << endl;
    return 0;
}
```

## p15_binary_search.cpp
```cpp
// Program 15: Binary Search in a 1D array (array must be sorted ascending)
#include <iostream>
using namespace std;
int main() {
    int arraySize, numbers[100], searchKey;
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " elements in ascending order: ";
    for (int index = 0; index < arraySize; index++) cin >> numbers[index];
    cout << "Enter element to search: ";
    cin >> searchKey;

    int low = 0, high = arraySize - 1, foundPosition = -1;
    while (low <= high) {
        int middle = low + (high - low) / 2;
        if (numbers[middle] == searchKey) { foundPosition = middle; break; }
        else if (numbers[middle] < searchKey) low = middle + 1;   // search right half
        else high = middle - 1;                                   // search left half
    }
    if (foundPosition != -1) cout << "Found at position " << foundPosition + 1 << endl;
    else cout << "Not found" << endl;
    return 0;
}
```

## p16_count_occurrences.cpp
```cpp
// Program 16: Count occurrences of an element (Linear Search)
#include <iostream>
using namespace std;
int main() {
    int arraySize, numbers[100], searchKey, occurrenceCount = 0;
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " elements: ";
    for (int index = 0; index < arraySize; index++) cin >> numbers[index];
    cout << "Enter element to count: ";
    cin >> searchKey;
    for (int index = 0; index < arraySize; index++)
        if (numbers[index] == searchKey) occurrenceCount++;
    cout << searchKey << " occurs " << occurrenceCount << " time(s)" << endl;
    return 0;
}
```

## p17_check_present.cpp
```cpp
// Program 17: Check whether a number is present in the array (Linear Search)
#include <iostream>
using namespace std;
int main() {
    int arraySize, numbers[100], searchKey;
    bool isPresent = false;
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " elements: ";
    for (int index = 0; index < arraySize; index++) cin >> numbers[index];
    cout << "Enter number to check: ";
    cin >> searchKey;
    for (int index = 0; index < arraySize; index++)
        if (numbers[index] == searchKey) { isPresent = true; break; }
    cout << searchKey << (isPresent ? " is present" : " is not present") << " in the array" << endl;
    return 0;
}
```

## p18_binary_search_int.cpp
```cpp
// Program 18: Binary Search for an array of integers (function version)
#include <iostream>
using namespace std;
int binarySearch(int numbers[], int arraySize, int searchKey) {
    int low = 0, high = arraySize - 1;
    while (low <= high) {
        int middle = low + (high - low) / 2;
        if (numbers[middle] == searchKey) return middle;
        if (numbers[middle] < searchKey) low = middle + 1;
        else high = middle - 1;
    }
    return -1;
}
int main() {
    int arraySize, numbers[100], searchKey;
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " integers in ascending order: ";
    for (int index = 0; index < arraySize; index++) cin >> numbers[index];
    cout << "Enter integer to search: ";
    cin >> searchKey;
    int position = binarySearch(numbers, arraySize, searchKey);
    if (position != -1) cout << "Found at position " << position + 1 << endl;
    else cout << "Not found" << endl;
    return 0;
}
```

## p19_binary_search_float.cpp
```cpp
// Program 19: Binary Search for an array of floating-point numbers
#include <iostream>
using namespace std;
int binarySearch(float values[], int arraySize, float searchKey) {
    int low = 0, high = arraySize - 1;
    while (low <= high) {
        int middle = low + (high - low) / 2;
        if (values[middle] == searchKey) return middle;   // exact match (see note below)
        if (values[middle] < searchKey) low = middle + 1;
        else high = middle - 1;
    }
    return -1;
}
int main() {
    int arraySize;
    float values[100], searchKey;
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " floating-point numbers in ascending order: ";
    for (int index = 0; index < arraySize; index++) cin >> values[index];
    cout << "Enter number to search: ";
    cin >> searchKey;
    int position = binarySearch(values, arraySize, searchKey);
    if (position != -1) cout << "Found at position " << position + 1 << endl;
    else cout << "Not found" << endl;
    return 0;
}
```

## p20_largest_binary_search.cpp
```cpp
// Program 20: Find the largest element in a sorted (ascending) array using Binary Search
#include <iostream>
using namespace std;
int main() {
    int arraySize, numbers[100];
    cout << "Enter number of elements: ";
    cin >> arraySize;
    cout << "Enter " << arraySize << " elements in ascending order: ";
    for (int index = 0; index < arraySize; index++) cin >> numbers[index];

    int low = 0, high = arraySize - 1;
    // keep discarding the left half while a bigger-or-equal neighbour exists on the right
    while (low < high) {
        int middle = low + (high - low) / 2;
        if (numbers[middle] <= numbers[middle + 1]) low = middle + 1;
        else high = middle;
    }
    cout << "Largest element = " << numbers[low] << " at position " << low + 1 << endl;
    return 0;
}
```
