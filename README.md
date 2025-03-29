# include  <iostream>
#include <vector>

using namespace std;

void bubbleSort(vector<int> arr) {
    for (int i = 0; i < arr.size() - 1; i++)
        for (int j = 0; j < arr.size() - i - 1; j++)
            if (arr[j] > arr[j + 1])
                swap(arr[j], arr[j + 1]);
    for (int num : arr) cout << num << " ";
    cout << endl;
}

void insertionSort(vector<int> arr) {
    for (int i = 1; i < arr.size(); i++) {
        int key = arr[i], j = i - 1;
        while (j >= 0 && arr[j] > key) arr[j + 1] = arr[j--];
        arr[j + 1] = key;
    }
    for (int num : arr) cout << num << " ";
    cout << endl;
}

void selectionSort(vector<int> arr) {
    for (int i = 0; i < arr.size() - 1; i++) {
        int minIdx = i;
        for (int j = i + 1; j < arr.size(); j++)
            if (arr[j] < arr[minIdx]) minIdx = j;
        swap(arr[i], arr[minIdx]);
    }
    for (int num : arr) cout << num << " ";
    cout << endl;
}

void simpleSort(vector<int> arr) {
    for (int i = 0; i < arr.size(); i++)
        for (int j = i + 1; j < arr.size(); j++)
            if (arr[i] > arr[j]) swap(arr[i], arr[j]);
    for (int num : arr) cout << num << " ";
    cout << endl;
}

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    vector<int> arr(n);
    cout << "Enter elements: ";
    for (int& num : arr) cin >> num;

    cout << "Bubble Sort: ";    bubbleSort(arr);
    cout << "Insertion Sort: "; insertionSort(arr);
    cout << "Selection Sort: "; selectionSort(arr);
    cout << "Simple Sort: ";    simpleSort(arr);

    return 0;
}

