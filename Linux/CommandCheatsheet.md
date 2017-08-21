- [指令結構、快捷鍵](#instruc)
- [線上求助及檔案搜尋](#help_search)
- [檔案、目錄基本操作](#basic)
- [系統及檔案權限](#permission)

<a name="instruc"></a>
# 指令結構、快捷鍵

| command | options | parameter1 | parameter2 | ... |
| -- | -- | --| -- | -- |
| 指令 | 選項 | 參數(1) | 參數(2) |

## 說明：

0. 一行指令中第一個輸入的部分絕對是『指令(command)』或『可執行檔案』
1. 選項前會帶 - 號，例如 -h；有時候會使用選項的完整全名，則選項前帶有 -- 符號，例如 --help， (某些特殊情況下， 選項或參數前面也會帶有正號『+』的情況)
2. 指令, 選項, 參數等以空格來區分，不論空幾格 shell 都視為一格；
3. 指令太長的時候，可以使用反斜線 (\\) 來跳脫 [Enter] 符號，使指令連續到下一行
> 注意！反斜線後就立刻接特殊字符，才能跳脫！

## 其他：

* 在 Linux 系統中，英文大小寫字母是不一樣的
* Linux 預設的情況下會提供六個 Terminal 來讓使用者登入， 切換的方式為使用：[Ctrl] + [Alt] + [F1]~[F6]
	* [Ctrl] + [Alt] + [F2] ~ [F6] ：文字介面登入 tty2 ~ tty6 終端機；
	* [Ctrl] + [Alt] + [F1] ：CentOS 圖形介面預設位置 (Ubuntu: F7)
	* 快捷鍵：
		* [Ctrl]-C	中斷目前程式
		* [Ctrl]-D	鍵盤輸入結束 (End Of File, EOF 或 End Of Input) ($ exit)
		* [Ctrl]-Z 	將『目前』的工作丟到背景中『暫停』
		* [Ctrl]-L	清除畫面 ($ clear)
		* [Shift] + [Page Up] | [Page Down]	往前翻頁 或 往後翻頁
	* 可用分號 (;) 分隔各指令，將多行命令打在同一行
	* 邏輯運算元：
		```
		$ cmd1 || cmd2	// 執行cmd1，如果 cmd1 失敗才會執行 cmd2
		$ cmd1 && cmd2	// 執行cmd1，如果 cmd1 成功才會執行 cmd2
		$ cmd1 ; cmd2	// 執行cmd1，然後接著執行 cmd2
		$ cmd1 | cmd2	// 執行cmd1，利用 cmd1 的結果執行 cmd2
		```
	* [Tab] 接在一串指令的第一個字的後面，為『命令補全』<br>
	   [Tab] 接在一串指令的第二個字以後時，則為『檔案補齊』<br>
	   若安裝 bash-completion 軟體，則在某些指令後面使用 [Tab] 按鍵時，可以進行『選項/參數的補齊』功能

<a name="help_search"></a>
# 線上求助及檔案搜尋

	$ 指令 --help	// 通常用在協助你查詢『你曾經用過的指令所具備的選項與參數』
	$ man 指令或資料	// manual，查詢從來沒有用過的指令，或者是檔案的『格式』
	
	選項：
		-k	// 只要說明檔有包含以上的關鍵字皆會列出
		-f	// 只列出與關鍵字完全相同的資料或指令
	
|man page 常用按鍵|進行工作|
|--|--|
|/欲搜尋的字串|向『下』搜尋|
|?欲搜尋的字串|向『上』搜尋|
n, N|搜尋字串時，用 n 來繼續下一個搜尋、 N 來進行『反向』搜尋|
|[space]|往下翻頁|
|[Home]|去到第一頁|
|[End]|去到最後一頁|
|q|結束這次的 man page|
	
	$ whatis 指令或資料 	<== 相當於 man -f 指令或者是資料
	$ apropos 指令或資料 	<== 相當於 man -k 指令或者是資料
	以上兩個指令須先以 root 身份建立 whatis 資料庫：
	# mandb
	
範例：
	
	$ man date
	訊息的第一行可以看到：『DATE(1)』

|重要代號|代表內容|
|--|--|
|1|使用者在 shell 環境中可以操作的指令或可執行檔|
|5|設定檔或者是某些檔案的格式|
|8|系統管理員可用的管理指令|
(使用 man man 來取得更詳細的說明)

	註：
		若搜尋結果同時有如(1)(7)...超過一個代號如使用 man -f man 搜尋時，
		可使用 ($man 編號 man) 指定要看的文件編號，
		若未指定，顯示先搜尋到的文件 (通常是數字最小那個)

	$ info 指令或資料 	// 類似 man，但有獨立頁面及超連結
|info page 常用按鍵|進行工作|
|--|--|
|n|到下一個節點 (node)|
|p|到上一個節點|
|u|到上一層節點|
|[Tab]|將游標在畫面中的 node 間移動|
|h|提供一些基本按鍵功能的介紹|

	$ find 一 二 三
	ㄧ、 要搜尋的目錄位置(必打，可為相對路徑) eg. /home
	二、 要搜尋的檔案種類、名稱規則...(必打)
		-type	f 	// file
			d 	// directory
			l 	// link
		-name	檔案名稱
			或 "檔名.*"	// 包含此檔名的所有檔案
			或 "*.c"	// 包含副檔名.c的所有檔案
			"*.[och]"	// 包含.o, .c, .h三種副檔名的所有檔案
	三、 參數
		-print		// 結果印在螢幕上(不需打)
		-exec 指令 {} \;	// 找到後要執行的指令
		-ok 指令		// 同 exec，但是每找到一個檔案都停下詢問是否處理

<a name="basic"></a>
# 檔案、目錄基本操作

	$ cd	相對路徑或絕對路徑	// 進入此路徑下的目錄
		/	 	// 根目錄
		~		// 家目錄(同等於/home/使用者名稱)
		.		// 當前目錄
		..		// 上一層目錄
		../..		// 上上層目錄

	$ exit	// 結束並離開程式 ([Ctrl]-D)

	$ cp 	// 複製
		cp 來源檔案 目標位置	// 使用參數 -r (recursive) 以複製資料夾
		cp 來源檔案 目標檔案	// 複製檔案內容覆蓋目標檔案原本的內容

	$ mv  	// 移動
		mv 來源檔案 目標位置
		mv 來源檔案 目標檔名	// 更改檔名

	$ mkdir 	// 創建資料夾
		-p 	// 若已存在，不建立也不顯示錯誤訊息

	$ touch 	// 修改檔案時間或建置新檔
		三個主要的變動時間：
		1. modification time (mtime)：
			當該檔案的『內容資料』變更時
		2. status time (ctime)：
			當該檔案的『狀態 (status)』改變時，如權限與屬性
		3. access time (atime)：
			當『該檔案的內容被取用』時，如使用 cat 去讀取檔案時

	$ ls	// (list) 顯示檔案的檔名與相關屬性
		-a	// 列出所有包括隱藏檔(ex: .vimrc)
		-l	// 顯示完整的格式如下：
			   1. 檔案類型
			   	-(file) d(directory) l(link)
				b(可隨機存取裝置) c(一次性讀取裝置)
			   2. (user, group, others)各自的權限r w x
			   3. 連結數
			   4. 擁有者
			   5. 所屬群組
			   6. 檔案容量 (bytes)
			   7. 最後被修改的時間
			   8. 檔名 \ 目錄名
		--full-time	// 顯示出完整的時間格式

		eg.
			drwxr-xr-x. 2 erebuszz erebuszz 6 Aug  1 13:59 Desktop

<a name="permission"></a>
# 系統及檔案權限
	
	$ su -   	// 輸入 root 的密碼讓你的身份變成 root

	$ chgrp		// 改變檔案所屬群駔

	$ chown		// 改變檔案擁有者
		-R : (recursive) 連同次目錄下的所有檔案都變更

		$ chown	帳號名稱 檔案或目錄
		$ chown	帳號名稱:群組名稱 檔案或目錄	// 同時改變所屬擁有者及群組
		   	帳號名稱.群組名稱 檔案或目錄
		eg.
			chown 0.0 date.sh
			= chown root.root date.sh

	$ chmod 	// 改變檔案、目錄權限
		-R : (recursive) 連同次目錄下的所有檔案都會變更
		
		
		1. 累加每種身份 (owner/group/others) 各自的三個權限 (r/w/x) 分數
		-> 其中權重分別為：
			r(read):4	w(write):2	x(execute):1

		eg.
		chmod 777	// 開啟 user, group, others 的所有權限

		2.
|chmod|u(user)<br>g(group)<br>o(others)<br>a(all)|+(加入)<br>-(除去)<br>=(設定)|r<br>w<br>x|檔案或目錄|
|:--:|:--:|:--:|:--:|:--:|

		eg.
		chmod  u=rwx,go=rx  .bashrc
		# 注意！ㄒu=rwx,go=rx 是連在一起的

		註：
		1. 目錄需要執行權限才可進入
		2. 檔案不希望他人看到，可拿掉讀取權限
		3. 檔案寫入的權限不含刪除該檔案
		4. 目錄的寫入權限可刪除期內已經存在的檔案與目錄 (不論該檔案的權限為何！)

	$ umask	檔案權限預設遮罩
		022 -> 轉為二進位 000010010 -> rwx r-x r-x

	$ init		// 切換執行等級
		init 0：關機
		init 3：純文字模式
		init 5：含有圖形介面模式
		init 6：重新開機

- 更改主機名的兩種方法
	1. $ sudo hostname 欲更改的名字	// 此方法僅於此次開機暫時改變
	2. $ sudo vim /etc/hostname	// 更改目前所使用的主機名
	   $ sudo vim /etc/hosts 	// 更改所有主機代稱及其對應ip => 之後下指令可用代稱代替完整ip位址

# 開關機與系統狀態

	$ startx	以純文字啟動時，開啟 X window (圖形介面 - GUI)
註：不一定開啟於tty1，重點是並沒有其他的 X window 在其他終端被啟用

	$ locale		// 顯示目前所支援的語系
	$ LANG=en_US.utf8	// 修改為英文語系(僅限輸出訊息)
	$ export LC_ALL=en_US.utf8	(將語系所有相關資料同步修改)
	$ who		// 目前有誰在線上
	$ netstat	// 網路的連線狀態
		-a	// 列出所有連接埠，包含 listening 與 non listening
	$ ps	// 查閱系統上面正在運作當中的程序
		常用組合：
		ps -l 	// 僅觀察自己的 bash 相關程序
		ps -aux	// 可以查閱所有系統運作的程序
|參數|功能|
|--|--|
|-a|不與 terminal 有關的所有 process|
|-u|有效使用者 (effective user) 相關的 process|
-x|通常與 a 這個參數一起使用，可列出較完整資訊|
|-l|較長、較詳細的將該 PID 的的資訊列出|

|印出的資訊|說明|
|--|--|
|F|程序旗標 (process flags)，說明這個程序的總結權限，常見號碼有：
||4 	// 此程序的權限為 root|
||1 	// 此子程序僅進行複製(fork)而沒有實際執行(exec)|
|S|程序的狀態 (STAT)|
|R| (Running)：該程式正在運作中|
|S| (Sleep)：該程式目前正在睡眠狀態(idle)，但可以被喚醒(signal)|
|D|不可被喚醒的睡眠狀態，通常這支程式可能在等待 I/O 的情況 (ex：列印)|
|T|停止狀態(stop)，可能是在工作控制(背景暫停)或除錯 (traced) 狀態|
|Z| (Zombie)：僵屍狀態，程序已經終止但卻無法被移除至記憶體外|
			
			UID/PID/PPID：
				代表『此程序被該 UID 所擁有/程序的 PID 號碼/此程序的父程序 PID 號碼』
			...待續
	註：
		UID:
			使用者 ID (User ID)
		GID:
			群組 ID (Group ID)
		=> 每一個檔案都會有所謂的擁有者 ID 與擁有群組 ID，當我們有要顯示檔案屬性的需求時，系統會依據 /etc/passwd 與 /etc/group 的內容， 找到 UID / GID 對應的帳號與群組名稱再顯示出來
		PID:
			觸發任何一個事件時，系統都會將他定義成為一個程序，並且給予這個程序一個 ID ，同時依據觸發這個程序的使用者與相關屬性關係，給予這個 PID 一組有效的權限設定


	$ jobs	// 目前的背景工作狀態
		-l 	// 同時列出 PID 的號碼
		註：
			印出的資訊中
			+ 代表最近一個被丟進背景且預設會被取用的工作
			- 代表最近倒數第二個被放置到背景中的工作號碼
			ex:
				目前我有兩個工作在背景當中，兩個工作都是暫停的， 而如果我僅輸入 fg 時，那麼那個有標注 + 的會被拿到前景當中來處理

	$ fg 	// (foreground)將背景工作拿到前景來處理
		%工作號碼 	// 直接規定取出的那個工作號碼(適用於 bg)

	$ bg 	// 讓工作在背景下的狀態變成『運作中』 / 等同使用 => 指令 &
			// 注意：[Ctrl]-Z 為『暫停』

	$ kill 	// 管理背景當中的工作
		kill -l 	// 列出目前 kill 能夠使用的訊號 (signal) 有哪些
		kill signal %工作號碼

			signal 	// 用 man 7 signal 可知：

				-1 	// 重新讀取一次參數的設定檔 (類似 reload)
				-2 	// 等同由鍵盤輸入 [ctrl]-c
				-9 	// 立刻強制刪除一個工作
				-15	// 以正常的程序方式終止一項工作。與 -9 是不一樣的

	$ sync	// 資料同步寫入磁碟(使用 sudo sync, 或先用 su- 進入 root)
		使用原因：
			Linux系統中，為了加快資料的讀取速度，所以在預設的情況中， 某些已經載入記憶體中的資料將不會直接被寫回硬碟，而是先暫存在記憶體當中
		註：
			1. 也可以被一般帳號使用！只不過一般帳號使用者所更新的硬碟資料就僅有自己的資料，不像 root 可以更新整個系統中的資料了
			2. 目前的 shutdown/reboot/halt 等等指令均已經在關機前進行了 sync 這個工具的呼叫，不過還是建議關機前多做幾次

	$ shutdown 	// 慣用的關機指令
		/sbin/shutdown [-krhc] [時間] [警告訊息]
		-k 	// 不要真的關機，只是發送警告訊息出去！
		-r 	// 在將系統的服務停掉之後就重新開機
		-h 	// 將系統的服務停掉後，立即關機
		-c 	// 取消已經在進行的 shutdown 指令內容。
		eg.
			sbin/shutdown -h 10 'I will shutdown after 10 mins'
		註：
			1. CentOS 7 下如果你什麼參數都沒有加，系統預設會在 1 分鐘後關機
			2. 使用遠端管理工具，那關機就只有 root 有權力而已
			3. 不管是 shutdown, reboot, ..., 全部的動作都是去呼叫 systemctl 這個管理命令

	$ reboot 	// 重新開機
	$ poweroff	// 關機
	$ halt 		// 系統停止～螢幕可能會保留系統已經停止的訊息
	$ pm-hibernate 	// 休眠(儲存電腦狀態並關機)

	$ systemctl
		halt
		poweroff
		reboot
		suspend 	// 睡眠(電腦及周遭設備進入低耗能模式)

# 小工具

$ date	顯示日期與時間
$ cal	顯示日曆
$ bc	計算機
	scale=小數點位數	// 設定接下來的計算所需用到的小數點位數

- 常見文書編輯器
	$ nano
	$ gedit
	$ vim


--------------------------
$ echo 	// 變數的取用
	-n 	// 顯示變數或字串後不跳行
	${變數名稱} 	// 讀出變數內容，{}可有可無
	設定規則：
		$ 變數名稱=變數內容
			注意：
				1. 等號兩邊不能直接接空白字元
				2. 變數名稱只能是英文字母與數字，且開頭字元不能是數字
				3. 變數內容若有空白字元可使用雙引號『"』或單引號『'』將變數內容結合起來，但
					(1) 雙引號內的特殊字元如 $ 等，可以保有原本的特性，如下所示：
					『var="lang is $LANG"』則『echo $var』可得『lang is zh_TW.UTF-8』
					(2) 單引號內的特殊字元則僅為一般字元 (純文字)，如下所示：
					『var='lang is $LANG'』則『echo $var』可得『lang is $LANG』
				4. 可用跳脫字元『 \ 』將特殊符號(如 [Enter], $, \, 空白字元, '等)變成一般字元
		$ unset 變數名稱 	// 取消變數

系統預設變數：(通常大寫字元為系統預設變數)
	(Note: 在變數前加上 $ 來取用變數內容，ex: echo $PATH)
	PATH	// 顯示環境變數位置
	PS1 	// 提示字元的設定

$ export 	// 自訂變數轉成環境變數
	PATH=路徑名稱:$PATH	// 添加路徑至原先的環境變數

$ cat 	// (concatenate)直接檢視檔案內容
	-b 	// 列印出行號
	-n 	// 連同空白行也會有行號

$ tac 	// 由最後一行到第一行反向在螢幕上顯示出來

$ more, $ less 	// 一頁一頁翻動
	註：
		man這個指令就是呼叫 less 來顯示說明文件的內容的

. file
	or
./file

$ source 設定檔檔名 	// 讀入環境設定檔
	由於 /etc/profile 與 ~/.bash_profile 都是在取得 login shell 的時候才會讀取的設定檔，所以若不使用上述指令，通常都是得登出再登入後，該設定才會生效

$ rm 	// 移除檔案
	rmdir	// 移除資料夾 -f (force)不會詢問是否確定刪除
	rm -fr	// 移除內含檔案的資料夾

$ which 	// 顯示特定檔案的位置
		grep
		ls

$ alias	// 顯示命令的別名
	alias 別名="執行命令及其參數"	// 設定執行命令的別名


$ scp 檔案路徑名稱 帳號@ip位址:	// 上傳檔案至伺服器
$ scp 帳號@ip位址:欲下載之檔案路徑名稱 欲放置之檔案路徑名稱	// 從伺服器下載檔案

$ tar 	// 打包指令
	檔案格式對應參數 -z => .gz / -j => .bjz .bz2 / -J => .xz
	(
	Note:
		1. -z, -j, -J 不可以同時出現在一串指令列中
		2. 壓縮比率： .xz > .bz2 > .gz
		3. 注意： tar 並非壓縮指令而是將多個目錄或檔案打包成一個大檔案，同時透過 gzip / bzip2 / xz 的支援，將檔案進行壓縮
	)
	ex:
		壓　縮：tar -jcv -f 檔名.tar.bz2 要被壓縮的檔案或目錄名稱
		查　詢：tar -jtv -f 檔名.tar.bz2
		解壓縮：tar -jxv -f 檔名.tar.bz2 -C 欲解壓縮的目錄
	(Note: 『 -f 檔名 』是緊接在一起的)
 	-x 	// 解打包或解壓縮
 	-c 	// 建立打包檔案
	-v 	// 在壓縮/解壓縮的過程中，將正在處理的檔名及權限等顯示出來
	-f 	// 後面打指定檔名
	-C 	// 解壓縮至指定目錄
	-t  // 察看打包檔案的內容含有哪些檔名
	-p 	// 保留備份資料的原本權限與屬性，常用於備份(-c)重要的設定檔

# encrypt file.txt to file.enc using 256-bit AES in CBC mode
openssl enc -aes-256-cbc -salt -in file.txt -out file.enc

# the same, only the output is base64 encoded for, e.g., e-mail
openssl enc -aes-256-cbc -a -salt -in file.txt -out file.enc

# decrypt binary file.enc
openssl enc -d -aes-256-cbc -in file.enc -out file.txt

# decrypt base64-encoded version
openssl enc -d -aes-256-cbc -a -in file.enc -out file.txt

壓縮並加密：
	$ tar -czf - 欲加密之檔名 | openssl enc -e -aes256 -out 輸出檔名.tar.gz
	$ openssl enc -d -aes256 -in 欲解密之檔名.tar.gz | tar xz -C 指定目錄

$ unrar e 解壓縮rar
	e 	//不用指定檔案路徑

$ readelf -d 執行檔	// 查看此執行檔所需要的函式庫

$ wc	// 計算行數、字數、字元數
	-l  ：僅列出行；
	-w  ：僅列出多少字(英文單字)；
	-m  ：多少字元；

$	命令 > 檔案 		// 將命令執行結果輸出至指定檔案

		(命令1; echo; 命令3) > 檔案 	// 將命令1及命令3執行後的結果共同放置至檔案，中間以空白行隔開

	命令 2> 檔案 		// 將命令執行顯示的錯誤訊息輸出至指定檔案
	命令 2>&1 檔案 	// 將命令執行顯示的錯誤訊息及其正常執行結果輸出至指定檔案 (同等於 1>&2)
	命令 >> 檔案 		// 將命令執行結果接續(append)到檔案的內容之後
	命令 < 檔案 		// 將檔案內容作為命令的輸入資訊
	命令1 | 命令2 | ...	// pipe: 將命令1執行後的輸出交給命令2做為輸入來執行
	(命令)			// 在小括號內執行的命令執行完後會跳回原先的目錄
		ex: 假設妳現在位於家目錄內(~)，試試執行 $ (cd /bin);pwd

補充： ? vs * vs [] vs !
	[a-z]
	[0-9][a-z]
	[a-zA-z0-9]	註：中間不可有空白
	.[!o]


history 欲顯示的歷史紀錄數量 	// 顯示前幾個（包括現在打的history 數字）歷史紀錄
!第幾個歷史紀錄 	// 再次執行此命令

$ ping -c 次數 ip 	// 檢查與此ip的連線並設定要ping幾次
----------------------------------------
/dev/null
/dev/tty
/dev/pts
----------------------------------------
補充：不同系統按下 Enter 的換行控制不同

	DOS, Windows   0D 0A   (\r\n)
	UNIX           0A      (\n)
	Machintosh     0D      (\r)

	ex:

	將於 windows 上編輯的執行檔去掉其中的 0D 使其能於Unix系統上執行：
		$ tr -d "\r" < 輸入來源檔 > 輸出的檔名

----------------------------------------
- /bin, /sbin, /usr/sbin, /usr/bin

	功能：
		/bin 放置系統的必備執行檔如：ls, chmod
		/sbin 放置系統管理的必備程式如：shutdown, reboot
		/usr/bin 放置一些後來才安裝的應用程式的執行檔如：gcc
		/usr/sbin 放置使用者安裝的系統管理程式如：netconfig
	權限：
		/bin 一般用戶即可執行
		/sbin 通常需要管理員的權限
	執行時間：
		/bin, /sbin都能在系統載入其他檔案系統前執行
	放置位置：
		/bin, /sbin必須與根目錄位在同一分割區
		/usr/bin, usr/sbin則不用

13.1
13.2
13.3 4 7 8 9 12 13 17 18

exit 0		// 沒問題
	 1 2	// 警告

last 	// 查看之前所有登錄過的紀錄
sudo lastb 	// 登錄失敗的紀錄
/var/log/btmp 	// 記錄錯誤登錄的日誌檔
- shell script
	read 變數名稱

	- if
		if command
			then
				commands
		fi

		if command; then
			commands
		fi
	- case
		case expression in
			pattern1)
				commands
				;;
			pattern2)
				commands
				;;
			...
		esac

	x=5
	y=7
	test $x -eq $y	// test指令在後面正確時回傳0, 錯誤回傳1

	-z
	-n

	p370
	[-f file]	// 檔案是否存在
	 -r 		// 檔案是否存在且可讀
	 -w
	 -x
	 -d
	 -s 		// ; 且長度 > 0

	$ 指令 參數1 參數2
		$0 	// 指令
		$1, $2, ... 	// 參數1, 參數2, ...
		$# 	// 參數總數
		$?	// 回傳前個命令執行結束後的return value，正常時為0
-------------------------------------

允許的ip連線管理

sudo iptables-save > ip.txt 	// 重新開機前
sudo iptables-restore < ip.txt
sudo iptables -nL --line-numbers | more 	// 以清單檢視被封鎖的 ip 並顯示行號
	-L ：列出目前的 table 的規則
	-n ：不進行 IP 與 HOSTNAME 的反查，顯示訊息的速度會快很多！
sudo iptables -D INPUT 行號 	// 解除第幾行的ip封鎖
sudo iptables -A INPUT -s ip位址 -i eth0 wlan0 -j DROP 	// 封鎖特定的ip
	-A ：新增加一條規則
	-s 來源 IP/網域
	-i ：封包所進入的那個網路介面
	-j ：後面接動作，主要的動作有接受(ACCEPT)、丟棄(DROP)、拒絕(REJECT)及記錄(LOG)

網路設定
	a.
		＄ ifconfig interface options
			interface：網路卡介面代號，包括 eth0, eth1, ppp0 等等
			options  ：可以接的參數，包括如下：
    			up, down ：啟動 (up) 或關閉 (down) 該網路介面(不涉及任何參數)
    			mtu      ：可以設定不同的 MTU 數值，例如 mtu 1500 (單位為 byte)
    			netmask  ：子遮罩網路
    			broadcast：廣播位址
    		ex:
    			$ifconfig eth0 192.168.100.100 //如果不加任何其他參數，則系統會依照該 IP 所在的 class 範圍，自動的計算出
    			$ifconfig eth0 mtu 9000 //僅修改該介面的 MTU 數值，其他的保持不動！
    			$ifconfig eth0:0 192.168.50.50 //在該實體網卡上，再模擬一個網路介面， 亦即是在一張網路卡上面設定多個 IP 的意思
    			$ifconfig eth0:0 down //關掉 eth0:0 這個介面。那如果想用預設值啟動 eth1：『ifconfig eth1 up』即可達成
    			$/etc/init.d/network restart //剛剛設定的資料全部失效，會以 ifcfg-ethX 的設定為主！
    b.
    	＄ip [option] [動作] [指令]
    		option ：設定的參數，主要有-s 顯示出該裝置的統計數據(statistics)，例如總接受封包數等
    		動作：亦即是可以針對哪些網路參數進行動作，包括有：
    			link  ：關於裝置 (device) 的相關設定，包括 MTU, MAC 位址等
    			addr/address ：關於額外的 IP 協定，例如多 IP 的達成等
    			route ：與路由有關的相關設定
    		ex:
    			＄ip link show //顯示出所有的介面資訊
    			＄ip -s link show  //show僅顯示出這個裝置的相關內容，如果加上 -s 會顯示更多統計數據；
    	＄ip link set [device] [動作與參數]
    		選項與參數：
				set ：可以開始設定項目
				device 指的是 eth0, eth1 等等介面代號；
			動作與參數：包括有底下的這些動作：
   				up|down  ：啟動 (up) 或關閉 (down) 某個介面，其他參數使用預設的乙太網路；
   				address  ：如果這個裝置可以更改 MAC 的話，用這個參數修改
   				name     ：給予這個裝置一個特殊的名字
   				mtu      ：就是最大傳輸單元
   			ex:
   				＄ip link set eth0 up //啟動 eth0 這個裝置介面
   				＄ip link set eth0 down //關閉 eth0 這個裝置介面
   				＄ip link set eth0 mtu 1000 //更改 MTU 的值，達到 1000 bytes，單位就是 bytes

   		更新網路卡的 MTU 使用 ifconfig 也可以達成啊。不過，如果是要更改『網路卡代號、 MAC 位址的資訊』的話，那可就得使用 ip 。不過，設定前可能得要先關閉該網路卡，否則會不成功
   			ex:
   				$ip link set eth0 down       //關閉介面
				$ip link set eth0 name vbird //重新設定
				$ip link show                //觀察一下
			網路卡代號都可以改變，不過，玩玩後記得改回來啊！因為我們的 ifcfg-eth0 還是使用原本的裝置代號！避免有問題，要改回來
		改回來網路卡
			ex:
				ip link set vbird name eth0  //介面改回來

		＄ip address [add/del] [IP參數] [dev 裝置名] [相關參數]
			add/del ：進行相關參數的增加 (add) 或刪除 (del) 設定
    		IP 參數 ：主要就是網域的設定，例如 192.168.100.100/24 之類的設定
    		dev    ：這個 IP 參數所要設定的介面，例如 eth0, eth1 等等；
    		相關參數：主要有底下這些：
        		broadcast：設定廣播位址，如果設定值是 + 表示『讓系統自動計算』
        		label    ：亦即是這個裝置的別名，例如 eth0:0 就是了！
        		scope    ：這個介面的領域，通常是這幾個大類：
                global   ：允許來自所有來源的連線；
                site     ：僅支援 IPv6 ，僅允許本主機的連線；
                link     ：僅允許本裝置自我連線；
                host     ：僅允許本主機內部的連線；
                所以當然是使用 global 囉！預設也是 global 啦！
            ex:
            	$ip address show //顯示出所有的介面之 IP 參數

            	$ip address add 192.168.50.50/24 broadcast + dev eth0 label eth0:vbird //新增一個介面，名稱假設為 eth0:vbird 
            	$ip address show eth0 //會顯示更改結果為 inet 192.168.50.50/24 brd 192.168.50.255 scope global eth0:vbird
            	$ip address del 192.168.50.50/24 dev eth0 //將剛剛的介面刪除

        $ip route [add/del] [IP或網域] [via gateway] [dev 裝置]
        	add/del ：增加 (add) 或刪除 (del) 路由的意思。
   			IP或網域：可使用 192.168.50.0/24 之類的網域或者是單純的 IP
    		via     ：從那個 gateway 出去，不一定需要
   			dev     ：由那個裝置連出去，這就需要了
    		mtu     ：可以額外的設定 MTU 的數值喔！

    		ex:
    			$ip route show //顯示出目前的路由資料
    			$ip route add 192.168.5.0/24 dev eth0 //針對本機直接溝通的網域設定好路由，不需要透過外部的路由器
    			$ip route add 192.168.10.0/24 via 192.168.5.100 dev eth0 //增加可以通往外部的路由，需透過 router 喔
    			$ip route add default via 192.168.1.254 dev eth0 //增加預設路由
    			$ip route del 192.168.10.0/24 //刪除路由



gsettings set org.gnome.desktop.interface enable-animations false 這個動作會將 GNOME 預設的畫面切換的動畫功能關閉
