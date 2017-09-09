# if conditional formula

- Syntax

    ```c
	if(condition1){
		statement1;
		...
	}
	else if(condition2){
		statement2;
		...
	}
	...
	else{
		statementN;
		...
	}
    ```

# switch conditional formula

- Syntax

	```c
	switch (variable name or operation){
		case match_number / character:
			statement1;
			break;
		case ...
		...
		default:
			statementN;
	}
	```

- 如果比對的是字元，則記得加上單引號（''）, e.g. case 'A'

- 如果比對的是一個數值範圍，在 gcc 編譯器的擴充還允許使用 ... 來設定一個範圍的數值, e.g. case 1...30

# for loop

- Syntax

	```c	
	for (initial variable; discriminant; Increment /Decrement or any statement){
		statement1;
		...
	}
	```

- 在一個陳述區塊中若想寫兩個以上的陳述句，則使用逗號（,）作區隔

# while loop

- Syntax

	```c
	while (conditional expression){
		statement1;
		...
	}
	```

> infinite loop : while(true), while(1))

- 先執行迴圈本體，然後再進行條件判斷

	```c
	do{
		statement1;
		...
	}while(conditional expression);
	```

# break, continue, goto

-  break 用於中斷目前的迴圈執行

- continue 只會結束接下來區塊中的陳述句，並 跳回迴圈區塊的開頭繼續下一個迴圈

- goto (not recommended, 濫用它的話會破壞程式的架構、使得程式的邏輯難以理解)

	```c
	Name:
	...
	...
	goto Name;
	```