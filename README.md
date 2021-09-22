# 0919 筆記

## markdown 筆記

```
# 表示主標題(H1)
##表示次標題(H2)

- 可以做出列次，相當於HTML內的ul-li

```

# 這是主標題

## 這是次標題

- 這是細項 01
- 這是細項 02

````

"```" <--鍵盤左上方的逗點，上下各三點，中間可以填寫程式碼
像這樣
console.log("Hi")

````

```
"[文字](網址)"、<>可以弄出超連結
```

[google.com](http://google.com)
<http://www.google.com>

三個星號可以做出分隔線

---

## git 使用指令

- git 作為版本控制使用(每次修改的紀錄、檔案放置、可追朔修改前的檔案)

- 工程師的履歷工具

### 常用基本操作

- cd : 進入至... cd 後面+空格+指定資料夾，ex:cd hello-git，代表前往 hello-git 的資料夾
- pwd : 顯示目前路徑
- mkdir : 建立新資料夾，ex:mkdir hello-git
- rm : remove，ex: rw readme.md，刪除 readme.md，切記勿亂用(rm -f)
- cat : 查詢檔案內容
- touch : 建立檔案，ex:touch hello-git.txt
- nano : 進入修改檔案，也可以直接從此建立檔案

### cd 使用細項

- cd ~ : 回到目錄
- cd .. : 回到上一層

### git alias

- co : checkout
- br : branch(建立分支)
- ci : commit(檔案說明，通常用於 add 後)
- st : status(查看目前檔案狀態)
- log : 有 lg、l、la(log all)

### 設定

- git config --global user.name "使用者名稱"
- git config --global user.email "使用者 email"
- git config --list : 確認輸入資料

### 其它 git 指令

- git init : 控管此資料夾，建立儲存庫(repository)，會產生.git 的隱藏檔
- rm -r .git : 若不想控管此資料夾，輸入此指令
- git blame : 可以查看此檔案為誰編輯的(很好用)

### repository(repo)指令

在 git 中會有三種地方，工作目錄(working directory)、暫存區域(staging area)、儲存庫(repository)
一般操作都會先在儲存庫，在 add 至暫存區，最後 push 上去

- git status : 查詢目前 init 資料夾的檔案狀態
- git add : 將檔案加入，ex: git add readme.md，更新檔案後也是這樣加進來
- git commit -m : 加入檔案的說明，ex:git commit -m "欲說明的內容"
- git commit -am : 上述兩條的集合體，不過限用於"已經 add 過的檔案"，意即欲"更新"的檔案才能用
- git diff : 查詢修改前後的差異
- git restore : 反悔，若不想更新可以用此指令，會還原檔案，此指令還可以當作上一步使用，非常好用
- git restore --staged : 將反悔的過程加入至暫存區
- git checkout : 前進至(回到)指定檔案版本，ex: git checkout "commit" "檔案名稱+副檔名"
- git HEAD : 回到現在的版本

### 推上 github

- 建立遠端 : 先在 github 建立資料夾，提取 https or SSH，再輸入 git remote add origin(遠端名，自訂) https://github.com(提取的https or SSH)即可
- git push : 將檔案推上至 github(前提是檔案已經 add、commit)
  若第一次 push 會需要輸入 git push -u origin(遠端名稱，看當初的命名) main(分支)
  之後更新完就只要輸入 git push

### git flow

我們在維護過程中，不會將檔案直接 push 到主要區域，通常會有分上線區、工作(作業)區...等，在完成最後作品中才會推到主要區域，而這些區域我們稱為分支，會有好幾條分支(branch)，最後才會合併(merge)在一起，成為我們最後的完整資料

- git branch : 建立分支，ex: git branch main(分支名稱)
- git switch : 切換分支，ex git switch main(切換至 main)
- 將預設分支設定成 main

---

第一步 :

- 輸入 nano ~/ .gitconfig
  第二步 :
- 進入後直接在最下方輸入

```
[init]
    defaultBranch = main
```

---

- merge : 將分支合併
  在最後分支上輸入指令即可，假設 main 為最後的分支，other 為其它分支，那就先 switch 到 main，再輸入 git merge other 即可

- 有時候 merge 會出錯，同時修改到桐個檔案導致，所以要先請欲 push 的人先回到次分支，再 push 一次

## Node.js

### 可以在不使用 web 的前提執行 JS 的工具(非框架--node.js 常用框架為 express)

### 安裝

- 使用 nvm : 可以進行 node.js 的版本控制，可以自由的切換 node.js 的版本
