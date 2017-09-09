

# Arithmetic Operation, Type Conversion

- Arithmetic operator

	- 加（+）、減（-）、乘（*）、除（/）、餘除運算子（%）或稱模數（Modulus）運算子

- Operator precedence 運算子優先順序

	- **()** => **^** => ***, /** => **+, -**

		(detailed information : https://msdn.microsoft.com/zh-tw/library/fatf1t6a(v=vs.90).aspx )

	- usage of %

		- eg:
                
            ```c	
            counter = (counter + 1) % 10    // 0 to 9 circulation
            ```
        
- rand() 與 srand()

	```cpp
    #include <stdlib.h> // library for C
    #include <cstdlib>  // library for C++

    /* rand() 產生正整數亂數，取 100 的餘數可以產生範圍為 0 to 99 的亂數 */
    cout << rand() % 100;
    ```

    - 把上面的程式重複執行數次之後，會發現所得到的亂數是一樣的，這是因為它由上一個數值產生出下一個亂數，而一開始系統都是 0，所以每次產生出來的亂數才會一樣<br>
	=> 用 srand() 函數改變一開始的亂數值

	- srand() 需要一個參數做為種子，以產生一個新的亂數數列，而這個參數我們通常以目前的時間傳入，也就是使用 time() 函數，而 time() 是定義在 time.h 中

        ```c
			srand(time(0));
			for(int i = 0; i < 5; i++){
				printf("%d\n", rand() % 100);
			}
        ```

- Explicit type conversion:

	- eg:

        ```cpp
        // change true from bool into integer, which is 1 here
		static_cast<int>(true)


	> you can also use the syntax such as ```(int)true```, which was used in C

- Implicit type conversion:

    - 在一個指定的動作中，左邊的數值會成為目標型態，當右邊的數值型態比左邊的數值型態長度小時，右邊的數值會自動提升為目標型態

        ```c
        int num = 10;
        double number = num;
        ```

	- 在一個型態混雜的算式中，長度較長的資料型態會成為目標型態，較小的型態會自動提升為目標型態，又稱算術轉換（Arithmetic conversion）

        ```c
		double number = 10.0;
		cout << number / 3;

# Relational Operation, Conditional Operation

- Comparison operator

	- 大於（>）、不小於（>=）、小於（<）、不大於（<=）、等於 （==）以及不等於（!=）

    - 程式的執行會顯示 0 或 1，分別表示真（成立）或假（不成立）

    > 在 C 中，所有非零的數值在作為條件式時都被視為真

- Conditional operator

	- **條件式 ? 成立傳回值 : 失敗傳回值**

# Logical operation, Bitwise operation

- Logical Operator

	- 「且」（&&）、「或」（||）及「反相」（!）

- Bitwise Operator

	- AND(&), OR(|), NOT(!), XOR(^), ~(Complement)

- 左移（<<）與右移（>>）運算子

    - 左移運算子會將所有的位元往左移指定的位數，左邊被擠出去的位元會被丟棄，而右邊會補上 0；右移運算則是相反，右邊被擠出去的位元會被丟棄，至於左邊位元補 0 或補 1 則不一定，視系統而定

# Increment, Decrement, Assignment Operation

- Increment Operator

	- i++, ++i

- Decrement Operator

	- i--, --i

- 將遞增（遞減）運算子撰寫在變數前時，表示先將變數的值加（減）1，然後再傳 回變數的值，將遞增（遞減）運算子撰寫在變數之後，表示先傳回變數值，然後再對變數加（減）1

    ```c
	num = i++;	// i = i + 1; num = i;
	num = ++i;	/ /num = i; i = i + 1;
    ```

- Assignment Operator

			a += b;  // a = a + b;
			a -= b;  // a = a - b;
			...
			a <<= b; // a = a << b;
