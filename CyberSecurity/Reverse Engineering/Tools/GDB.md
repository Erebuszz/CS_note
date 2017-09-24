The GNU Project Debugger

- http://www.study-area.org/goldencat/debug.htm

# Basic command

- `run` - 執行
- `disas <function name>` - 反組譯某個 function
- `break *<address>` - 設中斷點
- `info breakpoint` - 查看已設定哪些中斷點
- `info register` - 查看所有 register 狀態
- `x/wx <address>` - 查看 address 中的內容
    - w 可換成 b / h / g，分別是 1 / 2 / 8 byte
    - / 後可接數字，表示一次列出幾個
    - 第二個 x 可換成 u / d / s / i 以不同方式表示
        - u : unsigned int
        - d : decimal
        - s : string
        - i : instruction
- `backtrace`, `bt` - 顯示上層所有 stack frame 資訊
- `set *<address> = value`
    - 將 address 中的值設成 value，一次 4 bytes
    - 可將 * 換成 {char/short/long}，分別設定 1 / 2 / 8 byte(s)
    - e.g.
        - `set *0x602040=0xdeadbeef`
        - `set {int}0x602040=1337`

# 在有 debug symbol 下 (gcc 的 -g 參數)
  
- `[l]ist`：列出source code
- `[b]reak <line no.>` - 設斷點
- `[i]nfo local` - 列出區域變數
- `[p]rint <var>` - 印出變數 var 的值
    - `p <var> = <val>` - 改變變數值為 val
- `display <var>`
- `attach <pid>` - attach 一個正在運行的 process
    - 可以配合 ncat 進行 exploit 的 debug
        - `ncat -ve ./a.out -kl 8888`
    - `echo 0 > /proc/sys/kernel/yama/ptrace_scope`

## GDB - PEDA

- Python Exploit Development Assistance for GDB
    - https://github.com/longld/peda
    - https://github.com/scwuaptx/peda
- Some useful feature
    - `checksec` :
        - 查看 binary 中有哪些保護機制
        - CANARY/FORTIFY/NX/PIE/RELRO
    - `elfsymbol` : show elf .plt section
        - 查看 function .plt 時做 ROP 非常需要
    - `vmmap` : show memory mapping
        - 查看 process mapping
            - 可觀察到每個 address 中的權限
    - `readelf` : Get headers information from an ELF file
        - 查看 section 位置
            - 有些攻擊手法會需要
            - e.g. `ret2dl_resolve`
    - `find` (alias searchmem) : Search for a pattern in memory
        - search memory 中 的pattern
            - 通常拿來找字串
            - e.g. /bin/sh
    - `record` : record every instruction at runtime
        - 記錄每個 instruction，讓 gdb 可回溯前面的指令，在 PC 被改變後，可利用該功能，追回原本發生問題的地方
# pwntools

- Exploit development library
- python

## GDB cheatsheet

| 指令        | 說明                                  | 範例            |
| --------- | ----------------------------------- | ------------- |
| [b]reak func | 在 func 下中斷點                          | b main        |
| b *0xADDR | 在 ADDR 下斷點                          | b *0x08048000 |
| [c]ontinue | 繼續執行                                |               |
| r[un]         | 開始執行 / 重新執行                         |               |
| si        | step into（進到 call 的子函式）                 |               |
| ni        | next instruction（不跟進去 call）         |               |
| x         | 印 pointer 指向的資料（`help x` 看詳細用法）      | x/16xw $esp   |
| p         | 直接印出資料                              | p/d 0x5566    |
| i b       | 列出所有 breakpoints (info braekpoints) |               |
| i file    | 列出檔案資訊                              |               |
| d $NUM    | 刪除第 $NUM 個斷點                        |               |
| q         | 關閉 gdb                              |               |