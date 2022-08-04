归并排序是建立在归并操作上的一种有效的排序算法。该算法是采用分治法（Divide and Conquer）的一个非常典型的应用。将已有序的子序列合并，得到完全有序的序列；即先使每个子序列有序，再使子序列段间有序。若将两个有序表合并成一个有序表，称为2-路归并。 

O(n long2 n)

```C++

void mergesort(int* a,int low,int high){
    int mid = (low + high) / 2;
    if (low < right) {
        insert_mergesort(a, low, mid);
        insert_mergesort(a, mid + 1, high);
        merge(a, low, mid, high);
    }
}
void merge(int *a,int low ,int mid,int high ) {
    int i, j, k=low;
    int b[50] = { 0 };  //假设对50个元素非递减排序
    i = low;
    j = mid + 1;
    while (i <= mid && j <= high) {
        if (a[i] <= a[j]) {
            b[k] = a[i++];
        }
        else b[k] = a[j++];
        k++;
    }
    if (i > mid) {
        for (int t = j; t <= high; t++)
            b[k++] = a[t];
    }
    else
        for (int t = i; t <= mid; t++)
            b[k++] = a[t];
    for (k = low; k <= high; k++)
        a[k] = b[k];
}

```