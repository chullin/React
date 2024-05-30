![alt text](ch1_img/0_image.png)

# 1.1 準備開發工具及環境

### npm
是 node.js 的預設套件管理工具
像是 python 中的 pip

npx 是在 npm v5.2.0 之後內建的指令，可以自動安裝 package 並執行內部的指令

不需要手動安裝或指定完整路徑
使用方式很簡單，只需要輸入
```JS
npx package name
```

### node.js
要開發 React，而 React.js 是一個 JavaScript 函式庫，需要透過 node.js 運行

### nvm
用於 管理/切換 多版本 node.js 的工具


# 1.2 使用 create-react-app 創建一個專案
create-react-app 是 Facebook 設計的建立 React.js 開發環境的套件

只需要一行指令就可以快速建立一個 React

他提供了一個標準的檔案結構和一系列有用的工具

簡單來說不需要自己設置安裝，就可以使用最新的 ES6 語法等等

create-react-app 支持 "自動化建構"、"模組管理"、"代碼分割" 等等功能
還提供 "開發伺服器"，可以在本地端測試應用程式

只需要輸入
```JS
> npx create-react-app 應用程式名稱
```

在使用 create-react-app 之前，要先確認自己的 
* Node >= 14.00
* npm  >= 5.6

![alt text](image.png)


萬事俱備之後，就可以使用以下指令建立專案了！
讓我們建立一個圈圈叉叉的專案
```JS
npx create-react-app tic-tac-toe
```
* 實作我放在 Repository [React_implement](https://github.com/chullin/React_implement)

![alt text](image-1.png)

![alt text](image-2.png)
沒想到要跑蠻久的，大概 5 分鐘?

太好玩了吧?! 跟著書一起做真的覺得很容易呢！
看著官網做我頭好痛

接著，開啟專案資料夾，並執行
```JS
cd tic-tac-toe
npm start
```

就會自己跳出瀏覽器

![alt text](image-3.png)

啟用成功！

創建好後，資料夾檔案內容如下

![alt text](image-4.png)

index.html 是裡面唯一一個 html 檔
另一個重要的檔案在 src 裡面的 index.js

在這個 index.js 中使用 ReactDOM 物件中的 createRoot() 將 React 元素顯示到 index.html 中相對應的 id (id=root) 中

![alt text](image-5.png)

![alt text](image-6.png)

而下面

```JS
<React.StrictMode>
    <App />
</React.StrictMode>
```
是用於引入 App.js 這個檔案的程式碼

![alt text](image-7.png)

這一頁裡面所描述的 JSX (JSX 在語法上看起來與HTML 相近，但它其實是JavaScript 的語法擴展)
所描述的就是我們啟動本機伺服器後，在網址輸入 localhost:3000 看到的內容。所以接下來我們圈圈叉叉遊戲就是要改掉這一頁的內容

因此，在這個檔案當中引入 app.css 以及 logo.svg 都跟我們遊戲專案無關，到時候再改寫這一頁的時候，可以放心的把他們都砍了


<hr>

### ESLint
ESLint 是一個檢查程式碼品質的工具，他可以用於檢查程式碼是否符合指定的規範，並指出不符合規範的地方

它支持多種程式語言，包括 JavaScript、TypeScript、Java 和 Python 等

你可以在程式碼中指定規範，然後通過命令列工具執行 ESLint，舉裡來說

* 找出語法錯誤
    * 是否使用了沒有宣告的變數、是否少了括號等等常見的語法錯誤
* 確保遵循最佳實踐
    * 不使用全域變數、建議使用 === 而非 ==、不使用 eval 等等
* 提醒你刪掉多餘的程式碼
    * 宣告了沒有使用的變數、import 沒有使用的模組、空的 class constructor 等等
* 統一基本的 coding style
    * 要不要加分號、使用單引號或雙引號、縮排使用 space 或 tab 等等


### 安裝 ESLint

它提供了一耶方便的指令與工具，讓我們可以透過選擇選項的方式照自己需求設定，因此先全域安裝 ESLint

### 好像要在專案底下安裝
```JS
npm install eslint -g
```

![alt text](image-8.png)

安裝好後先初始化
```JS
eslint --init
```
![alt text](image-10.png)
雖然一樣跳出很多 warnning，但似乎是安裝好了，不管它

輸入 `init` 之後就會開始詢問你問題

![alt text](image-9.png)
會依序問很多問題，詳看書上內容，雖然還是有一點點不一樣，像是其中問要安裝 版本8 還是 版本9

然後沒有問要不要用 JSON

然後目前因為減少複雜度，所以沒有使用 TypeScript

ESLint 有很多客製化規定可以調整，但似乎改版了，跟書上不一樣

### styled-components
styled-components 是一個 CSS-In-JS 函式庫，讓你可以在 JSX 中撰寫 CSS code

* 它可以幫我們做到 CSS 不容易做到的 條件式判斷
* CSS 的樣式跟 JSX 沒有違和感，套用 CSS 樣式就像是寫其他 React 元件一樣，像是父原件可以透過 props 做動態調整
* CSS-In-JS 還幫我們解決「命名衝突」的問題，它將 class name 做 hash 成為唯一的名稱
* 它也有提供 ThemeProvider 這樣一個外層的 component 來幫助我們實踐換網站主題設計的系統。可以直接在 Render 時直接傳到整個 App 每一個 Components 及 styled-components

書中有舉例，這邊就略

安裝 style-components
```JS
npm install --save styled-components
```

剛剛雖然提過它有避免命名衝突的好處，但在 debug 的時候就會有點痛苦，所有 class 都是 hash 值，完全沒有識別度
因此，如果專案是使用 create-react-app 可以將
styled-components
改為
styled-components/macro

```JS
// 原本的
import styled from 'styled-components';

// 改成
import styled from 'styled-components/macro'
```

這樣 DOM 結構上就不會只有 hash 過的 class name，還會有可辨識、可讀性高的名稱了