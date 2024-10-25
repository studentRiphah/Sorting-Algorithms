# Sorting-Algorithms
Sorting Alogirithms

//bubble Sort//

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

//Selection Sort//

void swap( int &lhs, int &rhs );

void selectionSort( int a[], int n) { for (int i = 0; i < n-1; i++) {
int min = i;
for (int j = i+1; j < n; j++){ if (a[j] < a[min]) min = j;
}
swap(a[i], a[min]);
}
}

//Merge Sort//








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



//Quick Sort Partition Function//


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

//Quick Sort//


void quicksort(int theArray[], int first, int last) {
int pivotIndex;
if (first < last) {
 S1, pivot, S2 partition(theArray, first, last, pivotIndex);
 quicksort(theArray, first, pivotIndex-1); quicksort(theArray, pivotIndex+1, last);
}
}

