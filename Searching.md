# Searching Algorithms

## Linear Search

```c
// Linear search function
int linearSearch(int arr[], int n, int target) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == target) {
            return i; // Return the index of the target if found
        }
    }
    return -1; // Return -1 if target is not found
}
```

## Binary Search

```c
// Binary search function (recursive)
int binarySearch(int arr[], int low, int high, int target) {
    if (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == target) {
            return mid; // Element found at index mid
        } else if (arr[mid] < target) {
            return binarySearch(arr, mid + 1, high, target); // Search right half
        } else {
            return binarySearch(arr, low, mid - 1, target); // Search left half
        }
    }
    return -1; // Return -1 if target is not found
}
```