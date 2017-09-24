# Data type 資料型態

- Integer :
	- short, int, long
- Float :
	- float, double, long double
- Character :
	- char
- Bool
	- true, false

> 以上的資料型態在記憶體中佔有的大小依編譯器而有所差異，想知道這些資料型態在使用的平台上，佔有的記憶體空間有多少，可以使用 sizeof() 運算子

> 在新的 C11 標準中，建議包括 stdint.h 程式庫，使用 int8_t、int16_t、int32_t、int64_t uint8_t、uint16_t、uint32_t、uint64_t 等作為整數型態的宣告，以避免平台相依性的問題

# Literal constant 字元常量

- 1、1.0、3.14159 這樣的數值
- 程式中若寫下一個整數值，例如 1 這個數值的話，預設是個 int 型態，若在程式中寫下 1.0，3.14 等，預設會是 double 型態的數值

## Carry for integer
	
    11010	// binary
	26 	// Decimal
	032	// Octal
	0x1A	// Hexadecimal

- use "cout" to output an interger, the number will be displayed automatically in "Decimal"

- if using "printf", assign format of the value is essential
  
	eg:	
	```
	printf("%d\n", 26);
	printf("%d\n", 032);
	printf("%d\n", 0x1A)
	```

	=> the output will all be 26 in decimal (%d)

- 可以在整數值之後加上

	- **l** or **L** to make it in "long" type
	- **U** or **u** as "unsigned"
	- **F** or **f** as "float"
	- (UL can be assigned at the same time)
	- 20000 can be presented as 2e

## Escape sequences

| 轉義序列 | 說明 |
| ------ | ----- |
|	\n	|	newline			|
|	\t	|	horizontal tab	|
|	\v	|	vertical tab	|
|	\b	|	backspace			|
|	\r	|	(carriage return)	|
|	\f	|	換頁（formfeed)	|
|	\a	|	alert bell	|
|	\\	|	backslash		|
|	\'	| 	單引號 (')		|
|	\"	| 	雙引號 (")		|
| \ddd	|	八進位ASCII碼	|
| \xdd	|	十六進位ASCII	|
	
> 可以使用 endl 來取代 "\n"

# Variable 變數

- 提供具名稱的記憶體儲存空間，一個變數關聯一個資料型態、儲存的值與儲存空間的位址值

- naming 命名

	```
	int ageForStudent;
	int age_for_student;
	```

- Scope

	- Local variables

		- can only be accessed within the functions in which they are created

	- Global variables

		- can be accessed by any functions in the program

- Initialize

	```cpp
	int ageForStudent = 0;
	int ageForStudent(0);
	int ageForStudent = int();
	```

	> Use "const" before the data type if you don't want the value to be changed
	
	> 宣告無號的整數變數 => unsigned int

# Magic numbers

- C provides a preprocessor directive (also called a macro) for creating symbolic constants

	**#define NAME REPLACEMENT**

	eg.
	```c
	#define PI 3.14159265
	```

- at the time your program is compiled, #define goes through your code and replaces NAME with REPLACEMENT

# Input / Output

- In C++ provided by the standard library "iostream library", that's why you always add

	```cpp
	#include <iostream>
	```

	In C

	```c
	#include <stdio.h>
	```

	at the beginning of the code

- Format specifier

| 格式指定碼 | 			說明					|
| ------ | -------------------------------- |
| %c	 |	以字元方式輸出					   |
| %d	 |	10 進位整數輸出					|	
| %o	 |	以 8 進位整數方式輸出			 |
| %u	 |	無號整數輸出						|
| %x, %X |	將整數以 16 進位方式輸出			 |
| %f	 |	浮點數輸出 (double: %lf)			|
| %e, %E |	使用科學記號顯示浮點數				|		
| %g, %G |	浮點數輸出，取%f或%e，看哪個表示精簡 |
| %% 	 |	顯示 %						 |
| %s	 |	字串輸出						 |
| %lu	 | 	long unsigned 型態的整數			|
| %p	 | 	指標型態						|

- 在輸出浮點數時指定精度

	- eg:

		```c
		%.2f	// 小數點後取兩位
		%6f	// 至少要預留的字元寬度
		%-6f	// 表示靠左對齊，沒有指定則靠右對齊
		```

- 若事先無法決定字元寬度：

	```c
	printf("%*d\n", 2, 1);	// 2 為預留字元寬度，1 為輸出字元
	```

- Standard output

	1. C++
		```cpp
		cout << "Hello! World!" << endl;
		```
	2. C 
		```c
		printf("Hello! World!\n");	// 執行過後會傳回所輸出的字元數
		```

	- eg:

		```c
		int count = printf("This is a test!\n");
    	printf("%d\n", count);
		```

	-  Compile the program and output the result to the assigned file in the terminal

		```
		$ g++ main.cpp -o main
		$ ./main >> result.txt )
		```

		cerr << "Sorry! World!" << endl;

		> different from cout, the result will directly output to the terminal, and won't output to the file

- Standard Input

	```cpp
	int number = int();
	```
	
	1. 
	```cpp
	cin >> number;
	```
	2. 
	```c
	scanf("%d\n", &number)	// 取得輸入的字串傳至變數的位置
	```

	> Using %s in a scanf string tells scanf to read the next word from input – NOT a line of input

	- 指定可接受的字元集合:

	```c
	scanf("%[1-5]", str);	// 1 到 5
	/* 連續讀入符合集合的字元並放到字元陣列中，直到讀到不符合的字元為止，剩下的字元仍會存在輸入緩衝區中 */
	```
	
	> 因為在讀入數值或字串時，會自動添加一個換行符號在其後，第二個之後的 scanf 會讀取到上一次讀取時留下的換行符號而導致失效<br><br>
	=> 若有連續兩個以上的 scanf 讀入數值或字串，可於第二個之後的 scanf 裡的 % 符號前添加一空白字元，或使用
	
	```c
	fflush(stdin); // 清除輸入緩衝區
	```

- putchar()、getchar()、puts()、gets()

	- eg : 只想取得並輸出一個字元

	```c
	char c;
	printf("請輸入一個字元：");
	c = getchar();
	putchar(c);
	putchar('\n');
	```

	-  輸入了兩個以上的字元，則 getchar() 會取得第一個字元，並將第二個字元留在緩衝區中，直到使用 getchar() 或 scanf() 再次嘗試取得輸入

	- 使用 gets()，它會取得使用者的整行輸入字串，不包括按下 Enter 的換行字元碼
	
	- 想要輸出整行字串，也可以直接使用 puts()，它在輸出字串後，會直接進行換行

	> 因為 gets() 函式無法知道字元陣列的大小，而是依賴換行符號或 EOF 才會結束輸入，因此有可能引發緩衝區溢位的安全問題<br>
	-> 使用 fgets() 來取代 gets()

- fgets()

	- e.g.

		```c
		char str[20];
		printf("Type in your name\n");
		fgets(str, sizeof(str), stdin);
		```