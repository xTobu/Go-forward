# go-foward

> Learning Record of Golang

---

govendor
https://seans.tw/2017/govendor-intro/

```golang
govendor init
govendor init 這個指令會協助你的專案建立 vendor/ 資料夾，並建立 vendor.json。(一開始都必須執行這個指令)

govendor add +external
如果你的專案已經開發一段時間，而且之前都是使用 go get 的方式下載第三方套件，你就必須使用 govendor add +external，將專案裡有使用到的套件(而且 $GOPATH/src 裡已經下載了)，複製到自己的 vendor/ 資料夾。(如果是新的專案就不需執行)

govendor fetch [url]
當開發專案中需要安裝(或更新)某一些第三方套件時，可以直接執行 govendor fetch，這時 govendor 就會幫你將包下載到 vendor/。

govendor fetch [url]@[tag]
這個就比較特殊一點的用法，tag 可以直接輸入你想下載第三方套件的某一個 git commitID，又或是 git tag。下面有一些官方提供的案例：

govendor fetch golang.org/x/net/context@a4bbce
govendor fetch golang.org/x/net/context@v1   # Get latest v1.*.* tag or branch.
govendor fetch golang.org/x/net/context@=v1  # Get the tag or branch named "v1".
govendor sync
當你在專案裡有使用 git 的時候，你可能不希望 vendor/ 裡的程式碼一併被包進去。這時你就必須在 .gitignore 裡加上 vendor/*/，那麼在 commit 時，第三方套件就不會被加進去了(vendor/vendor.json 還是會哦！)。當 git clone 專案時，只需執行 govendor sync 就可以把第三方套件(指定版本)都下載下來了！
```
