# final_project

產品管理後端 API 環境需求

Node.js  
Docker  
MongoDB  

安裝步驟

1. Clone 專案
2. 安裝依賴
3. 環境設定  

4.建立 .env 檔案在根目錄  

加入以下內容：

MONGODB_URI=mongodb://localhost:27017/product-db

PORT=3000

5.啟動 MongoDB：

docker run --name mongodb -d -p 27017:27017 mongo

6.啟動服務：

node server.js

API 端點：

POST /api/products - 新增商品

GET /api/products - 獲取所有商品

GET /api/products/:id - 獲取單一商品

PUT /api/products/:id - 更新商品

DELETE /api/products/:id - 刪除商品

資料結構

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

API 預設運行在 http://localhost:3000
