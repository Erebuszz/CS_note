# C-type string

- Initialize

    ```c
    // 字串是一個字元陣列，最後一個字元以空字元 '\0' 作結尾
	char str[] = {'h', 'e', 'l', 'l', 'o', '\0'};
	char str[] = "hello";   // same as above
    ```
- 讀取字串

    ```c
    char str[80];
    scanf("%s", str);
    /* 變數前不用再加上 &，因為實際上，字串（字元陣列）變數名稱本身，即表示記憶體位址資訊 */
    ```

# 字串相關處理函式

- 函式定義於

    ```cpp
    #include <string.h> // in C
    #include <cstring>  // in C++
    ```

- 字串長度

    ```c
	(sizeof(str) / sizeof(str[0]));
    // The length of the char including end character
    
    strlen(str);
    // not including end character
    ```

- 字串複製

    ```c
	strcpy(str1, str2); // str2 copied to str1
    strncpy(str1, str2, 要複製的字元長度);
    ```

- 字串串接

    ```c
	strcat(str1, str2); // str2 concatenated to str1
    strncat(str1, str2, 要串接的字元長度);
    ```

- 字串比較

    ```c
	strcmp(str1, str2); // compare the size of str1 and str2
	/* 比較字串 str1 與 str2 的大小，若相同就傳回 0，str1 大於 str2 則傳回大於 0 的值，小於則傳回小於 0 的值，比較的標準是依字典順序 */
    ```

- 比較兩個字串，找出兩個字串中開始不匹配的地方

    ```c
    size_t loc = strspn(str1, str2);
    /* 傳回兩個字串開始不匹配的第一個字元索引位置，完全不同則傳回 0 */
    ```

    - strpbrk() 函式則與 strcspn() 類似，只不過完全不匹配的話，則傳回 NULL

- 字串搜尋

    ```c
    char *loc = strstr(source, search);
    /* 第一個參數是被搜尋字串，第二個參數是想要搜尋的子字串，如果沒找到子字串則傳回 NULL，如果搜尋到第一個符合的子字串，則傳回符合位置的指標 */
    ```

    - 想要得知子字串是在哪一個索引位置，則可以利用該指標減去字串（字元陣列）開頭的指標，得到的位移量即為符合的索引位置

        ```c
        if(loc == NULL) {
            printf("找不到符合的子字串\n");
        }
        else {
            printf("在索引位置 %lu 處找到子字串\n", loc - source);
        }
        ```

# 字串轉換、字元測試

- 將字串轉換為數字

    ```c
    #include <stdlib.h>

    atoi(str);  // string to int
    atol(str);  // string to long
    atof(str);  // string to float
    /* 搜尋字串中可以轉換的部份，直到遇到無法轉換的字元，字串開頭可以使用正負號 */
    ```

- 測試字元為數字、字母、大寫、小寫等等

    ```c
    #include <ctype.h>

    isalnum(int c)：是否為字母或數字
    isalpha(int c)：是否為字母
    iscntrl(int c)：是否為控制字元
    isdigit(int c)：是否為數字
    islower(int c)：是否為小寫字母
    isprint(int c)：是否為列印字元
    ispunct(int c)：是否為標點符號
    isspace(int c)：是否為空白
    isupper(int c)：是否為大寫字母
    isxdigit(int c)：是否為16進位數字
    ...
    /* ctype.h 中也包括了像是可以進行字母大小寫轉換的 tolower()、toupper() 等函式 */
    ```

# String Type (C++)

- Initialize

    ```cpp
	string str1;  // 建立一個string物件，內容為空字串
    string str2("caterpillar");  // 以字串常量建立字串
    string str3(str2); // 以string實例建立字串
    ```

- 字串長度

    ```cpp
	str1.size();
    str1.length();  // the same
    ```

- 是否為空

	```cpp
    str1.empty();
    ```
		
- 是否相同

    ```cpp
    str1 == str2;
    ```

- 字串複製

    ```cpp
    str = str2;
    ```

    - 這個指定會將 str 1原本的字串記憶體空間釋放，並重新配置足夠容納 str2 的記憶體空間
    - 可以將一個 C- Style 的字串指定給 string，但反過來不行

- 字串串接
	
    ```cpp
    str1 += str2;
    ```

- 指定字串

    ```cpp
	str2 = str1.assign(string, start, num);
    ```

    - 從 str1 的第 start 個字元取出 num 個字元來指定給 str2

- 附加字串

	```cpp
    str2 = str1.append(string, start, num);
    ```

- 尋找字串

    ```cpp
	str1.find(string, 0);
    ```

    - 從引發 find 的字串物件第 0 個字元尋找是否有符合 string 的子字串

- 插入字串

    ```cpp
	str1.insert(start, string);

    - 將 string 插入引發 insert 的字串物件第 start 個字元之後