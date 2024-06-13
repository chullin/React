# CSS 排版工具
* CSS Flex
* CSS Grid
* React Hook

這些技巧可以幫我們更掌握 React 的狀態控制 與 生命週期，還有跟時間控制相關的 setTimeout、setInterval(設定間隔)

# CSS Flex
Flex 是 Flexible Box 的縮寫

外容器(Container)、內元件(Items)

![alt text](flex.png)

如果把外容器的屬性用在內元件上

內元件的屬性用在外容器上

語法雖然沒錯，但會因為屬性放錯地方而沒有效用

當專案複雜時，它有可能會是別人的外元件，同時又是別人的外容器！

```HTML
<div className="flex-container">
    <div className="Item"></div>
    <div className="Item"></div>
    <div className="Item"></div>
</div>
```

為了使用 Flex，我們要先在外容器宣告

```CSS
.container{
    display: flex;
}
```


## 元件排列方式

在 Flex 中，我們可以決定元件是 
* 水平排列    (row, 左到右)
* 反轉水平排列(row-reverse, 右到左)
* 垂直排列    (column, 上到下)
* 反轉垂直排列(column-reverse, 下到上)

```CSS
.container{
    display:flex;
    flex-direction: row | row-reverse | column | column-reverse;
}
```

#### "主軸" 與 "交錯軸" 的定義會隨著 flex-direction 設置不同而改變！

## 元件"換行"處理
處理換行就代表是由上到下，所以方向是 column，換行是捲動(wrap)滾輪
* 換行
* 不換行
* 換行反轉
```CSS
.container{
    display:flex;
    flex-direction:column;
    flex-wrap:wrap | nowrap | wrap-reverse;
}
```
## 主軸對齊 justify-content
這個屬性要在 "容器" 上宣告

以橫向(左右)為主軸：

justify-content：
![alt text](image.png)

#### flex-first 是預設值！

## 交錯軸對齊 align-item"s"
以縱軸(上下)為主

align-items：
![alt text](image-1.png)

#### stretch (拉緊、拉伸)，所以效果是佈滿整版，這是預設值！


## 內元件的 Flex 屬性
* flex-grow：伸縮性，預設值 0，0 不會縮放，當空間還有剩餘時，會按照比例分配給同個空間下的內元件
* flex-shrink：收縮性，預設值 1，0 不會收縮，空間不夠時，會依照比例壓縮多少比例單位
* flex-basis：元件的基準值，可使用不同的單位，ex：px

```CSS
.item{
    flex: 1 1 100px;
}

/* 也可以 */

.item{
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 100px;
}
```

![alt text](image-2.png)