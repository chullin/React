![alt text](ch1_img/0_image.png)

# 準備開發工具及環境

### npm
是 node.js 的預設套件管理工具
像是 python 中的 pip

是在 npm v5.2.0 之後內建的指令，可以自動安裝 package 並執行內部的指令

不需要手動安裝或指定完整路徑
使用方式很簡單，只需要輸入
```JS
npx package name
```

### node.js
要開發 React，而 React.js 是一個 JavaScript 函式庫，需要透過 node.js 運行

### nvm
用於 管理/切換 多版本 node.js 的工具


### 使用 create-react-app 創建一個專案
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