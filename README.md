# Sorting-Algorithms
Sorting Alogirithms

//////bubble Sort//////

void swap( int &lhs, int &rhs );

void bubleSort(int a[], int n) { bool sorted = false;
int last = n-1;
for (int i = 0; (i < last) && !sorted; i++){
sorted = true;
for (int j=last; j > i; j--) if (a[j-1] > a[j]{
swap(a[j],a[j-1]);
sorted = false; 
}
}
}

void swap( int &lhs, int &rhs ){ int tmp = lhs;
lhs = rhs; rhs = tmp;
}
/////Bubble Sort Tick Function////////
int calculateTicks(int arr[], int n) 
{ int ticks = 0;  for (int i = 0; i < n - 1; i++) 
{ bool swapped = false;
for (int j = 0; j < n - i - 1; j++) 
{ ticks++; 
 if (arr[j] > arr[j + 1]) 
{ swap(arr[j], arr[j + 1]); ticks++; 
 swapped = true; }
} 
if (!swapped) break; 
 } 
return ticks; } 
int main() 
{ int originalArray[] = {23, 78, 45, 8, 32, 56}; 
int n = sizeof(originalArray) / sizeof(originalArray[0]); 
int arr[n]; 
Tick Function

// Worst Case:
  copy(begin(originalArray), end(originalArray), arr); 
 sort(arr, arr + n, greater<int>()); 
 cout << "Ticks (Worst Case): " << calculateTicks(arr, n) << endl; 
// Best Case:
 copy(begin(originalArray), end(originalArray), arr); 
 sort(arr, arr + n); 

/cout << "Ticks (Best Case): " << calculateTicks(arr, n) << endl; 
// Average Case:
copy(begin(originalArray), end(originalArray), arr); 
 cout << "Ticks (Average Case): " << calculateTicks(arr, n) << endl; 

////////Bubble sort Time Calculation Function for all cases///////////


best_case = [1, 2, 3, 4, 5]
average_case = [3, 1, 4, 5, 2]
worst_case = [5, 4, 3, 2, 1]

print(f"Best-case time: {measure_time(best_case[:]):.6f} seconds")
print(f"Average-case time: {measure_time(average_case[:]):.6f} seconds")
print(f"Worst-case time: {measure_time(worst_case[:]):.6f} seconds")



////////////Selection Sort////////

void swap( int &lhs, int &rhs );

void selectionSort( int a[], int n) { for (int i = 0; i < n-1; i++) {
int min = i;
for (int j = i+1; j < n; j++){ if (a[j] < a[min]) min = j;
}
swap(a[i], a[min]);
}
}


//////////////Selection Sort Tick Function///////

def selection_sort(arr):
    ticks = 0
    n = len(arr)
    for i in range(n):
        min_idx = i
        ticks += 1
        for j in range(i+1, n):
            ticks += 1
            if arr[j] < arr[min_idx]:
                min_idx = j
                ticks += 1
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
        ticks += 1
    return ticks

arr = [64, 25, 12, 22, 11]

ticks = selection_sort(arr)
print(arr)
print(ticks)

//////////////////Time calculation for all cases(Best, Worst, Average)////////////////////////

import time

def selection_sort(arr):
    for i in range(len(arr)):
        min_idx = i
        for j in range(i+1, len(arr)):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]

def time_sort(arr):
    start = time.time()
    selection_sort(arr[:])
    return time.time() - start

arr_best = [1, 2, 3, 4, 5]
arr_average = [64, 25, 12, 22, 11]
arr_worst = [5, 4, 3, 2, 1]

print(f"Best case: {time_sort(arr_best):.6f} seconds")
print(f"Average case: {time_sort(arr_average):.6f} seconds")
print(f"Worst case: {time_sort(arr_worst):.6f} seconds")



///////////Merge Sort///////////////








void merge(int theArray[], int first, int mid, int last) { int tempArray[last+1]; 
int first1 = first;	
int first2 = mid + 1;		
int index = first1;  for ( ; (first1 <= last1) && (first2 <= last2); ++index) {
if (theArray[first1] < theArray[first2]) { tempArray[index] = theArray[first1];
++first1;
}
else {
tempArray[index] = theArray[first2];
++first2;
}
}



for (; first1 <= last1; ++first1, ++index) tempArray[index] = theArray[first1];


tempArray[index] = theArray[first2];



theArray[index] = tempArray[index];
}








void mergesort(int theArray[], int first, int last) {
if (first < last) {
int mid = (first + last)/2; 

 mergesort(theArray, first, mid); mergesort(theArray, mid+1, last);


 merge(theArray, first, mid, last);
}
}
//////////////Merge Sort Tick Function/////////////////

def merge_sort(arr):
    ticks = 0
    if len(arr) <= 1:
        return arr, ticks

    mid = len(arr) // 2
    left_sorted, left_ticks = merge_sort(arr[:mid])
    right_sorted, right_ticks = merge_sort(arr[mid:])
    ticks += left_ticks + right_ticks

    sorted_arr, merge_ticks = merge(left_sorted, right_sorted)
    ticks += merge_ticks
    return sorted_arr, ticks

def merge(left, right):
    result = []
    i = j = ticks = 0

    while i < len(left) and j < len(right):
        ticks += 2
        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
       else:
            result.append(right[j])
            j += 1

    result.extend(left[i:])
    result.extend(right[j:])
    ticks += len(left[i:]) + len(right[j:])
    return result, ticks

arr = [64, 25, 12, 22, 11]
sorted_arr, ticks = merge_sort(arr)
print("Sorted array:", sorted_arr)
print("Total ticks (operations):", ticks)


Merge Sort Time Calculation for (BEST,AVERAGE,WORST) 
Cases

import time
import random

def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        L = arr[:mid]
        R = arr[mid:]
        merge_sort(L)
        merge_sort(R)
        i = j = k = 0
        while i < len(L) and j < len(R):
            if L[i] < R[j]:
                arr[k] = L[i]
                i += 1
            else:
                arr[k] = R[j]
                j += 1
            k += 1
        while i < len(L):
            arr[k] = L[i]
                        i += 1
            k += 1
        while j < len(R):
            arr[k] = R[j]
            j += 1
            k += 1
def time_merge_sort(arr):
    start_time = time.time()
    merge_sort(arr)
    return time.time() - start_time

def generate_sorted_array(size):
    return list(range(size))

def generate_reverse_sorted_array(size):
    return list(range(size, 0, -1))

def generate_random_array(size):
    return [random.randint(0, 10000) for _ in range(size)]
if __name__ == "__main__":
    array_size = 1000
   best_case_time = time_merge_sort(generate_sorted_array(array_size))
    print(f"Best case (sorted): {best_case_time:.6f} seconds")

  worst_case_time = time_merge_sort(generate_reverse_sorted_array(array_size))
    print(f"Worst case (reverse sorted): {worst_case_time:.6f} seconds")



    average_case_time = time_merge_sort(generate_random_array(array_size))
    print(f"Average case (random): {average_case_time:.6f} seconds")


////////////////////Quick Sort Partition Function/////////////////


void swap( int &lhs, int &rhs );

void partition(int theArray[], int first, int last, int &pivotIndex) {

// Choose and place pivot in theArray[first]
choosePivot(theArray, first, last);

// Initialize
int pivot = theArray[first];
int lastS1 = first;
int firstUnknown = first + 1;

// Move one item at a time until unknown region is empty
for (; firstUnknown <= last; ++firstUnknown) {
if (theArray[firstUnknown] < pivot) { // Belongs to S1
++lastS1; // Expands S1 by incrementing lastS1
// Swap firstUnknown with lastS1
swap(theArray[firstUnknown], theArray[lastS1]);
}
// else belongs to S2, ++firstUnknown in the loop
// places it to S2
}
// Place pivot in proper position and mark its location swap(theArray[first], theArray[lastS1]);
pivotIndex = lastS1;
}

///////////////Quick Sort/////////////////


void quicksort(int theArray[], int first, int last) {
int pivotIndex;
if (first < last) {
 S1, pivot, S2 partition(theArray, first, last, pivotIndex);
 quicksort(theArray, first, pivotIndex-1); quicksort(theArray, pivotIndex+1, last);
}
}
for j in range(low, high):
        ticks += 1
        if arr[j] < pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]
           
   ticks += 1

    arr[i + 1], arr[high] = arr[high], arr[i + 1]
    ticks += 1
    return i + 1, ticks

  
   arr = [64, 25, 12, 22, 11]
  ticks = quick_sort(arr, 0, len(arr) - 1)
  print("Sorted array:", arr)
  print("Total ticks (operations):", ticks)
 Quick Sort Time Calculation for (BEST,AVERAGE,WORST) 
Cases
import time
import random

def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quick_sort(left) + middle + quick_sort(right)
def time_quick_sort(arr):
    start_time = time.time()
    quick_sort(arr)
    return time.time() - start_time

def generate_sorted_array(size):
    return list(range(size))

def generate_reverse_sorted_array(size):
    return list(range(size, 0, -1))

def generate_random_array(size):
    return [random.randint(0, 10000) for _ in range(size)]

if __name__ == "__main__":
    array_size = 1000

    best_case_time = time_quick_sort(generate_sorted_array(array_size))
    print(f"Best case (sorted): {best_case_time:.6f} seconds")

    worst_case_time = time_quick_sort(generate_reverse_sorted_array(array_size))
    print(f"Worst case (reverse sorted): {worst_case_time:.6f} seconds")


