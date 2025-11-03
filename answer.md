# 第2次隨堂題目-隨堂-QZ2
>
>學號：112111121   (學號和姓名都要寫)
><br />
>姓名：呂佩衫
>

本份文件包含以下主題：(至少需下面兩項，若是有多者可以自行新增)
- [x] 說明內容

## 說明程式與內容

開始寫說明，該說明需說明想法，
並於之後再對上述想法的每一部分將程式進一步進行展現，
若需引用程式區則使用下面方法，
若為.cs檔內程式除了於敘述中需註明檔案名稱外，
還需使用語法` ```語言種類 程式碼 ``` `，其中語言種類若是要用python則使用py，java則使用java，C/C++則使用cpp，
下段程式碼為語言種類選擇csharp使用後結果：

```csharp
public void mt_getResult(){
    ...
}
```

若要於內文中標示部分網頁檔，則使用以下標籤` ```html 程式碼 ``` `，
下段程式碼則為使用後結果：

```html
<%@ Page Language="C#" AutoEventWireup="true" ...>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<meta http-equiv="Content-Type" ...>
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        </div>
    </form>
</body>
</html>
```
更多markdown方法可參閱[https://ithelp.ithome.com.tw/articles/10203758](https://ithelp.ithome.com.tw/articles/10203758)

請在撰寫"說明程式與內容"該塊內容，請把原該塊內上述敘述刪除，該塊上述內容只是用來指引該怎麼撰寫內容。

1. a.

Ans: 




1. b.

Ans:首先先利用funtion去宣告getLowStock這個函式，
這個函式主要是要找出庫存低於10的項目，所以依照題目去列，
利用filter去找到庫存(item.stock)少於10的項目
找到哪些是庫存少於10之後，利用map去把項目的名稱(item.name)取出來
最後輸出那些是庫存少於10的項目
並且回傳項目名稱
```Java
function getLowStock(products) {

  //先找出庫存少於10的項目
  const lowStockItems = products.filter(item => item.stock < 10);

  //再來是取出這些項目的名稱
  const itemNames = lowStockItems.map(item => item.name);

  //最後輸出庫存少於10的結果
  console.log("庫存少於10的項目：",itemNames);
  return itemNames;
}
```
以下是利用終端機執行出來的畫面：
![alt text](<螢幕擷取畫面 2025-11-03 152251.png>)

反覆練習有對function更理解，知道這個是宣告函式的部分

<!-- 請撰寫時，最後一句話再寫一次 --> 反覆練習有對function更理解，知道這個是宣告函式的部分


1. c.

Ans:要撰寫updateStock(products,updates)這個函式一樣先用funtion
我的方法是先利用map去製作一個新的陣列，並存在updated裡，
接下來做判斷動作，
if的第一個是如果updates有出現重複的商品名稱，把舊的覆蓋掉，換成新的
再利用展開的運算子去建立新的物件
如果沒有更新，就回傳原本舊的商品庫存
接下來就是輸出更新後的庫存
也要回傳輸出後的東西
```Java
function updateStock(products, updates) {
  
  //先用map建立新的陣列
  const updated = products.map(item => {

    if (updates[item.name] !== undefined) {
      return {...item, stock: updates[item.name] };
    } else{
      return {...item };
    }
  });

  updated.forEach(item => {
    console.log(`${item.name}的庫存: ${item.stock}`);
  });

  return updated;
}
```
以下是1b檔案利用終端機執行的所有截圖畫面：
![alt text](<螢幕擷取畫面 2025-11-03 152013-1.png>)
![alt text](<螢幕擷取畫面 2025-11-03 152020-1.png>)
![alt text](<螢幕擷取畫面 2025-11-03 152025-1.png>)

<!--  請撰寫時，第一句話再寫一次  -->要撰寫updateStock(products,updates)這個函式一樣先用funtion

2. a.

Ans:這題需要利用switch的方法進行路由，並且分成三種不同網址，
依照題目分成網址有'/'、'/calculator'以及不是以上這兩種的其他網址
直接按照題目去分，因已經有設有answer這個變數，所以當這些網址被區分開的時候，直接利用answer=去顯示我們要的文字並且跳出
才可以繼續執行其他網頁
```Java
  switch (url) {
    case '/':
      answer = 'index.html輸出部分';
      break;

    case '/calculator':
      answer = 'index2.html輸出的部分';
      break;

    default:
      answer = 'error.html輸出的部分';
      break;      
  }     
```
以下是各網頁執行結果截圖：  
![alt text](<螢幕擷取畫面 2025-11-03 141237.png>)
這個是網址是'/'的時候的頁面

![alt text](<螢幕擷取畫面 2025-11-03 141609.png>)
這個是當網址後加了'/calculator'會出現的畫面

![alt text](<螢幕擷取畫面 2025-11-03 141715.png>)
這個截圖是網址都不屬於以上兩種會出現的畫面

<!--  請撰寫時，第一句話再寫一次  --> 這題需要利用switch的方法進行路由，並且分成三種不同網址，

2. b.

Ans: 跟2a很像，但是又很不一樣的題目，需要將2a原本只有顯示文字畫面變成ejs的網頁畫面，
以上原理很簡單，但實際操作好難，因為要讀的是檔案，所以用的rendfile去讀ejs，這塊對我來說不太熟悉，
完全是用硬背下來的，考前練習也是查網路才寫得出來這些，目前還沒有完全理解，
但有理解跟上一題差不多，只是如果是檔案要如何去讀檔案，以及什麼檔案還沒有理解完。

```Java
  if (req.url === '/') {
    filePath = './index.ejs';
  } else if (req.url === '/calculator') {
    filePath = './index2.ejs';
  }
 
  else if (req.url.endsWith('.css') || req.url.endsWith('.js')) {
    fileOtherFile = '.' + req.url;
  } else {
    filePath = './index3.ejs';
  }
```
這是我執行後的網頁畫面：
![alt text](<螢幕擷取畫面 2025-11-03 160610.png>)
![alt text](<螢幕擷取畫面 2025-11-03 162702.png>)


<!--  請撰寫時，第一句話再寫一次  -->跟2a很像，但是又很不一樣的題目，需要將2a原本只有顯示文字畫面變成ejs的網頁畫面，

2. c.

Ans:

<!--  請撰寫時，第一句話和最後一句再寫一次  -->

2. d.

Ans:


