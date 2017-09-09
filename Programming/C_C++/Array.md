# One-dimensional array

- initialize

    ```c
	int irr[10] = {0};
	char carr[10] = {'\0'}; // with \0, C indicates the end of the string.
	...

- 可變長度的陣列型態

    ```c
    int len = 0;
    scanf("%d", &len);
    int arr[len];
    ```

- 只初始索引 0 與索引 1 的兩個元素，其他未初始的元素，整數的話會自動初始為 0，浮點數的話會自動初始為 0.0，字元的話會自動初始為空字元 

    ```c
	double darr[5] = {0.0, 0.1};
    ```

- 宣告陣列時未定義陣列大小，C 編譯器將自動根據元素個數決定陣列大小

    ```c
	int iarr[] = {1, 2, 3, 4, 5};
    ```
- 可以使用 sizeof() 運算子得知陣列的長度

    ```c
    int numbers[] = {1, 2, 3, 4, 5, 6};
    printf("陣列長度：%d\n", sizeof(numbers) / sizeof(numbers[0]));
    ```

> 不可以將陣列直接指定給另一個陣列，或是直接比較兩個陣列是否相同

- 只能循序一個一個元素進行複製

    ```c
    for(int i = 0; i < 5; i++) {
    arr1[i] = arr2[i];
    }
    ```

# Two-dimensional array

- Syntax

    ```c
	int iarr[row_number][column_number];
	int iarr[2][3] = {
        {1, 2, 3}, 
        {4, 5, 6}
    };
    ```
>多維以上的陣列在 C 中也是可行的，但並不建議使用，使用多維陣列會讓元素的指定更加困難，此時適當的將資料加以分割，或是使用其它的資料結構來解決，會比直接宣告多維陣列來得實在