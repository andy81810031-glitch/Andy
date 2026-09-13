Git 學習筆記

一、第一次使用 Git：安裝與設定

1. 安裝 Git

先在電腦安裝 Git。VS Code 本身不是 Git，VS Code 只是可以呼叫電腦裡安裝好的 Git。

2. VS Code 安裝 Git Graph

Git Graph 是 VS Code 擴充套件，可以用圖形方式查看 Commit、Branch、Merge 與版本歷史。

它不是使用 Git 的必要工具，只是方便查看 Git 歷史。

3. 查看 Git 版本

git --version

用途：查看目前電腦安裝的 Git 版本，也可以用來確認 Git 是否安裝成功。

4. 設定 Git 使用者名稱

git config --global user.name "名字"

用途：設定 Git Commit 紀錄中使用的作者名稱。

5. 設定 Git 使用者 Email

git config --global user.email "信箱"

用途：設定 Git Commit 紀錄中使用的作者 Email。

--global 代表這項設定套用到目前使用者的所有 Git 專案。

6. 查看 Git 設定與設定來源

git config --list --show-origin

用途：列出目前所有 Git 設定，並顯示每個設定是從哪個設定檔讀取的。

二、建立一個新的 Git 專案

1. 初始化 Git Repository

git init

用途：把目前所在的資料夾初始化成 Git Repository（Git 儲存庫），開始使用 Git 管理版本。

Git 會建立隱藏的 .git 資料夾。

2. 把檔案加入暫存區

指定一個檔案：

git add index.html

加入目前目錄範圍內的變更：

git add .

用途：把檔案的變更加入 Staging Area（暫存區），準備下一次 Commit。

3. 建立 Commit

git commit -m "first"

用途：把已經 git add 到暫存區的變更建立成一個 Commit（版本紀錄），並將這次 Commit 的訊息寫成 first。

first 不是特殊指令，可以依照修改內容自行更改，例如：

git commit -m "新增首頁"
git commit -m "修改表格"

4. 將目前分支重新命名為 main

git branch -M main

用途：把目前所在的 Git 分支重新命名為 main。

三、連接 GitHub

1. 新增遠端 Repository

git remote add origin GitHub儲存庫網址

用途：把 GitHub Repository 加入目前的本機 Git 專案，並把這個遠端 Repository 命名為 origin。

簡單理解：

origin
  ↓
GitHub Repository 網址

2. 查看遠端 Repository

git remote -v

用途：查看目前 Git 專案設定了哪些 Remote（遠端儲存庫），以及它們的網址。

四、第一次 Push 到 GitHub

git push -u origin main

用途：把本機的 main 分支推送到 origin 遠端儲存庫，並建立本機 main 與遠端 origin/main 的追蹤關係。

因為 -u 建立了追蹤關係，所以之後通常可以直接使用：

git push

五、之後修改程式碼的常用流程

git add .
git commit -m "這次修改了什麼"
git push

流程：

修改程式碼
    ↓
git add .
    ↓
加入暫存區
    ↓
git commit -m "訊息"
    ↓
建立本機 Commit
    ↓
git push
    ↓
推送 Commit 到遠端 Repository

六、完整指令速查

第一次設定 Git

git --version
git config --global user.name "名字"
git config --global user.email "信箱"
git config --list --show-origin

第一次建立專案並推上 GitHub

git init
git add .
git commit -m "first"
git branch -M main
git remote add origin GitHub儲存庫網址
git remote -v
git push -u origin main

之後每次修改

git add .
git commit -m "這次修改了什麼"
git push

核心觀念

init 初始化 → add 加入暫存區 → commit 建立版本 → remote 連接遠端 → push 推到 GitHub。