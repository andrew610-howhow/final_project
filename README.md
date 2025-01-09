# WEB-FINAL-PROJECT 
# 主題名稱:線上商品展示與管理平台
## 專案主題與目標
我們製作了一個可以任意更動商品的電商平台，使用者可以透過標籤或搜尋找尋心儀的產品下單，可以在購物車選擇到貨地點與如何付款

管理方可以藉由複製圖片網址來預覽呈現的樣子，並按照規格新增、刪除、修改各類商品的圖片、名稱、價格、庫存、標籤等

目標讓使用者可以輕鬆使用各類功能，管理者也可以用簡單的步驟修改上架的產品

### 產品管理後端 API 環境需求

Node.js  
Docker  
MongoDB  

### 下載步驟
    git clone https://github.com/andrew610-howhow/final_project.git
    cd --/webfinal
    
### 前端處理

    cd webfinal-frontend\webfinal-frontend
    npm install
    npm start

### 後端處理

1.cd進資料夾

    cd webfinal-backend\final_project

2.建立 .env 檔案在根目錄  

並加入以下內容：

    MONGODB_URI=mongodb://localhost:27017/product-db
    PORT=7000

3.啟動 MongoDB：

    docker run --name mongodb -d -p 27017:27017 mongo

4.啟動服務：

    node import-data.js
    node server.js


## 技術選擇與理由

- ### React.js
    - 組件化開發: 讓代碼可重用，開發效率高，組員可以分別開發不同頁面。
    - 單向數據流: 提供更易於管理和預測的數據處理。
    - 強大生態系統: 有大量工具與庫支持，可以輕鬆擴展功能，並應對複雜的狀態管理和路由需求。

- ### JavaScript
    - 跨平台性: 作為一個解釋型語言，JavaScript 不僅能運行在瀏覽器中，還可以在服務器端（如 Node.js）運行，使開發者能夠使用同一語言進行前後端開發。
    - 事件驅動: JavaScript 的事件驅動模型非常適合處理用戶交互，並且能夠支持非同步操作（如 AJAX 請求），這對動態網站至關重要。
    - 廣泛的應用範圍: JavaScript 是網頁開發的標準語言，並且隨著 Node.js 的崛起，它的應用範圍已擴展到後端開發。
      
- ### HTML/CSS  
    - 結構與樣式分離: 清晰的開發流程。
    - 兼容性強: 支援所有主流瀏覽器。
    - 響應式設計: 自適應不同設備，提供優秀體驗。
    
- ### MongoDB
    - 靈活的數據模型: MongoDB 支援動態架構，資料庫結構不需要事先定義，這使得資料模型能夠隨著需求變化進行調整，特別適合快速開發和原型設計。
    - 高擴展性: MongoDB 支援水平擴展，可以根據需求動態增加更多的伺服器來處理增長的資料。
    - NoSQL: MongoDB 是一種文檔型 NoSQL 資料庫，它使用 JSON 格式存儲資料，適合處理結構不固定的大數據或高變動的資料。
  



### 資料結構

商品資料結構：

jsonCopy{

    "name": "商品名稱",
    
    "price": 100,
    
    "stock": 10,
    
    "image": "圖片URL",
    
    "description": "商品描述",
    
    "product_id": "產品編號",
    
    "launch_date": "發售日期",
    
    "tags": ["標籤1", "標籤2"]
    
}

### API 端點：

POST /api/products - 新增商品

GET /api/products - 獲取所有商品

GET /api/products/:id - 獲取單一商品

PATCH /api/products/:id - 更新商品

DELETE /api/products/:id - 刪除商品

## 注意事項

確保 Docker 已啟動

確保 MongoDB 容器正在運行


### API 預設運行在 http://localhost:7000

### REACT網站預設在http://localhost:3000
如有占用問題須更改localhost，請至webfinal-backend/server.js將以下程式的localhost修改


    // 設置 CORS
    app.use(cors({
      origin: 'http://localhost:3000',  // 確保這個端口是前端應用運行的端口
      methods: 'GET,POST,PATCH,DELETE',  // 支援的方法
      credentials: true  // 支援跨域的 cookie
    }));


