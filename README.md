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

### API 端點：

POST /api/products - 新增商品

GET /api/products - 獲取所有商品

GET /api/products/:id - 獲取單一商品

PATCH /api/products/:id - 更新商品

DELETE /api/products/:id - 刪除商品

## 技術選用

- ### React.js
    -組件化開發: 讓代碼可重用，開發效率高。
    -虛擬DOM: 提高性能，減少重渲染。
    -強大生態系統: 有大量工具與庫支持。

- ### JavaScript
    - 
    - 
    - 
- ### HTML/CSS、、
    - 
    - 
    - 
    
- ### MongoDB
    - 
    - 
    - 
### 後端


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

確保 Docker 已啟動

確保 MongoDB 容器正在運行



### API 預設運行在 http://localhost:7000

### REACT網站預設在http://localhost:3000
如有占用問題須更改localhost，請至webfinal-backend/server.js將以下的host修改


    // 設置 CORS
    app.use(cors({
      origin: 'http://localhost:3000',  // 確保這個端口是前端應用運行的端口
      methods: 'GET,POST,PATCH,DELETE',  // 支援的方法
      credentials: true  // 支援跨域的 cookie
    }));


