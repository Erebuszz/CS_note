# Pointer and memory location

- 取址運算子（Address-of operator）: &

    ```c
    printf("變數 var 的值：%d\n", var);
    printf("變數 var 的記憶體位址：%p\n", &var);
    ```

- declare a pointer

    ```c
	type* ptr;
    type *ptr;  // preference
    /* type 是指標的型態如 int, float, char, etc. */
    ```

- 使用 & 運算子取出變數的位址值並指定給指標

    ```c
	int var = 10;
	int *ptr = &var;
    ```

- 使用提取 （Dereference）運算子 * 來提取指標指向位址的資料

    ```c
    printf("取出 ptr 指向的記憶體位置之值：%d\n", *ptr);
    ```

- 將某個值指定給 *ptr 時，該記憶體位置的值也會跟著改變，相當於告訴程式，將值放到 ptr 指向的記憶體位址

    ```c
    *ptr = 20;
    printf("var = %d\n", var);
    ```
    ```> var = 20```

> 如果宣告指標但不指定初值，則指標指向的位址是未知的，存取未知位址的記憶體內容是危險的
>> 如果指標一開始不指向任何的位址，則可設定初值為 0，表示不指向任何位置

```c
int *iptr = 0;
```

- 只希望儲存記憶體的位址，然後將之與另一個記憶體位址作比較，這時並不需要關心型態的問題，可以使用 void* 來宣告指標

- 由於 void 型態的指標沒有任何的型態資訊，所以只用來持有位址資訊，不可以使用 * 運算子對 void 型態指標提取值，而必須作轉型動作至對應的型態

    ```c
    void *vptr = &var ;
    int *iptr = (int*) vptr;
    ```

- 被 const 宣告的變數一但被指定值，就不能再改變變數的值， 但是以下這樣是可以改變變數值的：

    ```c
    const int var = 10;
    int *vptr = &var; // 在 Ubuntu 16.04 的 gcc 會產生警訊
    *vptr = 20;
    ```

- 如果不想要該**記憶體位置的值**被改變，則可以用 const 宣告指標

    ```c
    const int *vptr = &var;
    *vptr = 20; // error, assignment of read-only location
    ```

- 指標常數，也就是一旦指定給指標值，就不能指定新的**記憶體位址**給它

    ```c
    int* const vptr = &x;
    vptr = &y;  // error,  assignment of read-only variable 'vptr'
    ```

# Pointer Arithmetic

- 除了指定運算子 =、取址運算子 & 與取值運算子 * 之外，還有 +、-、++、--、+= 與 -= 等運算子可以使用在指標上

- 在指標運算上加 1 ，是表示前進一個資料型態的記憶體長度

# Pointer and Array

- 在宣告一個陣列之後，陣列名稱用來參考至陣列的第一個元素的記憶體位址

    ```c
    arr == &arr[0]
    ```

# malloc()、free()、calloc() 與 realloc()

- 配置 1000 個 int 型態大小的記憶體

    ```c
    int *arr = malloc(1000 * sizeof(int));
    ```

- 使用 malloc() 函式動態配置的空間，在整個程式結束前並不會自動歸還給記憶體，必須使用 free() 函式將空間還給記憶體

    ```c
    free(ptr);
    ```

- 配置後的空間資料是未知的，可以使用 calloc() 來宣告空間配置 (將所有的空間值初始為 0)

    ```c
    int *arr = calloc(1000, sizeof(int));
    ```

- 使用指標來模擬二維陣列

    ```c
    int *ptr = malloc(m * n * sizeof(int));

    for(int i = 0; i < m; i++) {
        for(int j = 0; j < n; j++) {
            *(ptr + n*i + j) = i + j;
        }
    }
    ```

- 改變先前配置的記憶體大小，則可以使用 realloc()

    ```c
    int *arr1 = malloc(size * sizeof(int));
    int *arr2 = realloc(arr1, sizeof(int) * size * 2);
    ```

> arr1 與 arr2 的位址相同並不保證，realloc() 會需要複製資料來改變記憶體的大小，若原位址有足夠的空間，則使用原位址調整記憶體的大小，若空間不足，則重新尋找足夠的空間來進行配置，在這個情況下，realloc() 前舊位址的空間會被釋放掉，因此，必須使用 realloc() 傳回的新位址，而不該使用舊位址，若 realloc() 失敗，則傳回空指標（null）

>> 進行檢查：

```c
int *arr2 = realloc(arr1, sizeof(int) * size * 2);
if(!arr2) {
    arr1 = arr2;
}
....
free(arr1);
```

# Double Pointer

- 指標可以用來儲存（某變數的）記憶體位址，所以指標本身就是一個變數，也要佔有記憶體空間才能儲存資訊

    ```c
    int p = 10;
    int *ptr = &p;

    printf("*ptr 參照的值:%d\n", *ptr);
    printf("ptr 儲存的位址值:%p\n", ptr);
    printf("ptr 的記憶體位置:%p\n", &ptr);
    ```

    ```
    *ptr 參照的值:10
    ptr 儲存的位址值:0x7ffc77005e5c
    ptr 的記憶體位置:0x7ffc77005e60
    ```

- 為了要儲存指標的記憶體位址
    - 若指標是個 int* 型態變數，如同 int 變數必須宣告 int* 指標，所以 int* 型態變數就必須宣告 int** 型態的指標

    ```c
    int p = 10;
    int *ptr1 = &p;
    int **ptr2 = &ptr1;

    printf("p 的值：%d\n", p);
    printf("p 的記憶體位置:%p\n\n", &p);

    printf("*ptr1 = %d\n", *ptr1);
    printf("ptr1 = %p\n", ptr1);
    printf("ptr1 的記憶體位置:%p\n\n", &ptr1);

    printf("**ptr2 = %d\n", **ptr2);
    printf("*ptr2 = %p\n", *ptr2);
    printf("ptr2 = %p\n\n", ptr2);
    ```

    ```
    p 的值：10
    p 的記憶體位置:0x7ffdbbf22864

    *ptr1 = 10
    ptr1 = 0x7ffdbbf22864
    ptr1 的記憶體位置:0x7ffdbbf22868

    **ptr2 = 10
    *ptr2 = 0x7ffdbbf22864
    ptr2 = 0x7ffdbbf22868
    ```

# Pointer and String

- Syntax

    ```c
    char *str = "hello";
    ```

- 使用字元指標的好處是，您可以直接使用指定運算子將一個字串常數指定給字元指標

    ```c
    str = "world";
    ```

> 上面的程式 str 前後指向的記憶體位址並不相同

- 使用陣列的方式宣告字串，則不可以直接使用 = 指定運算子另外指定字串

    ```c
    char str[] = "hello";
    str = "world";  // error, incompatible types in assignment
    ```

- 在字元指標中使用指標陣列，可以更方便地處理字串陣列

    ```c
    char *str[] = {"professor", "teacher", "student", "etc."};
    ```

- 二維以上的字串陣列

    ```c
    char *str[][2] = {
        "professor", "Justin",
        "teacher", "Momor", 
        "student", "Caterpillar"
    };
    ```