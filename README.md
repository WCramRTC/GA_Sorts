
# Comprehensive Tutorial on Sorting Algorithms with Complete C# Code Examples

## Introduction

This tutorial provides an in-depth look at four key sorting algorithms - Selection Sort, Bubble Sort, Insertion Sort, and Merge Sort - complete with C# code examples and explanations.

---

### 1. Selection Sort
**Description:** Repeatedly finds the smallest element and moves it to the sorted portion.

**C# Code Example:**
```csharp
public void SelectionSort(int[] arr)
{
    for (int i = 0; i < arr.Length - 1; i++)
    {
        int minIndex = i;
        for (int j = i + 1; j < arr.Length; j++)
            if (arr[j] < arr[minIndex])
                minIndex = j;

        int temp = arr[minIndex];
        arr[minIndex] = arr[i];
        arr[i] = temp;
    }
}
```

---

### 2. Bubble Sort
**Description:** Repeatedly steps through the list and swaps adjacent elements if they are in the wrong order.

**C# Code Example:**
```csharp
public void BubbleSort(int[] arr)
{
    for (int i = 0; i < arr.Length - 1; i++)
        for (int j = 0; j < arr.Length - i - 1; j++)
            if (arr[j] > arr[j + 1])
            {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
}
```

---

### 3. Insertion Sort
**Description:** Builds the final sorted array one item at a time.

**C# Code Example:**
```csharp
public void InsertionSort(int[] arr)
{
    for (int i = 1; i < arr.Length; i++)
    {
        int key = arr[i];
        int j = i - 1;

        while (j >= 0 && arr[j] > key)
        {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}
```

---

### 4. Merge Sort
**Description:** Divides the array into two halves, sorts each half, and then merges them.

**C# Code Example:**
```csharp
public void MergeSort(int[] arr, int left, int right)
{
    if (left < right)
    {
        int middle = left + (right - left) / 2;

        MergeSort(arr, left, middle);
        MergeSort(arr, middle + 1, right);

        Merge(arr, left, middle, right);
    }
}

private void Merge(int[] arr, int left, int middle, int right)
{
    int n1 = middle - left + 1;
    int n2 = right - middle;

    int[] L = new int[n1];
    int[] R = new int[n2];
    int i, j;

    for (i = 0; i < n1; ++i)
        L[i] = arr[left + i];
    for (j = 0; j < n2; ++j)
        R[j] = arr[middle + 1 + j];

    i = 0;
    j = 0;
    int k = left;

    while (i < n1 && j < n2)
    {
        if (L[i] <= R[j])
        {
            arr[k] = L[i];
            i++;
        }
        else
        {
            arr[k] = R[j];
            j++;
        }
        k++;
    }

    while (i < n1)
    {
        arr[k] = L[i];
        i++;
        k++;
    }

    while (j < n2)
    {
        arr[k] = R[j];
        j++;
        k++;
    }
}
```

---

### Conclusion

Each sorting algorithm has its own unique characteristics. Understanding these algorithms and their implementations in C# is crucial for effective data manipulation and algorithm choice based on the application's requirements.

### Further Learning
- Test these algorithms with different data sets.
- Explore more advanced sorting algorithms like Quick Sort and Heap Sort.
- Analyze the real-world applications of each sorting algorithm.
