# Misc 2
網頁內容 沒問題
=> Header
    curl -I
字串結尾有等號
    可能是base64編碼，拿去解碼
內容提到皮卡丘喜歡黃色
    檢視原始碼
    發現<body bgcolor="white">
    改成 yellow
# Misc 3
g++ 

# Crypto 1

# Web2

## PHP weak type

$db 的這個 user

    array("username" => "sena", "password" => "0e959146861158620914280512624073")

只要輸入的密碼經過 md5 hash 後開頭是 0e 即可，在 PHP 中會以科學記號來解讀他，所以值等於 0

因此密碼輸入 QNKCDZO 即可