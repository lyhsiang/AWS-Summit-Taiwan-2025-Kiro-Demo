#  Kiro 入門實作

歡迎來到您第一次的 Kiro 實作體驗！在這個實驗中，您將學習如何使用 Kiro 的 AI 能力來快速且高效地建構應用程式。

## 練習 1: 使用 AWS Bedrock 建構聊天機器人 UI

在這個練習中，您將建立一個與 AWS Bedrock 整合的聊天機器人介面，展示 Kiro 如何協助您以最少的努力建構 AI 驅動的應用程式。

### 🎯 學習目標
建構並部署一個聊天機器人 UI，該 UI 將託管在 AWS S3 上並透過 CloudFront 提供服務，具備適當的安全配置和後端互動的佔位符功能。

### 📋 前置需求
- 已安裝並運行 Kiro IDE
- 具有 S3 和 CloudFront 存取權限的 AWS 帳戶
- 已配置 AWS CLI（用於部署）

### 🚀 逐步操作指南

#### 步驟 1: 建立專案資料夾
1. 在您的電腦上，建立一個名為 `MyCoolChatbot` 的資料夾
2. 這將成為您聊天機器人應用程式的專案工作區

#### 步驟 2: 在 Kiro 中開啟專案
1. 啟動 Kiro IDE
2. 點擊 **"Open a project"** 按鈕
3. 選擇剛才建立的 `MyCoolChatbot` 資料夾
4. Kiro 將初始化專案工作區

<img width="472" height="360" alt="Screenshot 2025-07-11 at 9 42 17 am" src="https://github.com/user-attachments/assets/ea7ce532-d7bc-4c7e-bf4a-ae1cb1701c49" />


#### 步驟 3: 存取 Let's Build 功能
1. 在 Kiro 中，導航到 **"Let's build"** 頁面
2. 您將看到兩個可用選項：
   - **Vibe** - 先聊天，再建構。探索想法並在發現需求時進行迭代
   - **Spec** - 先規劃，再建構。在開始編碼前建立需求和設計

3. 在這個練習中，選擇 **"Vibe"** 模式
4. 將模型設定為 **"Claude Sonnet 3.7"**（或最新可用版本）
5. 確保 **Autopilot** 已啟用

<img width="472" height="360" alt="Screenshot 2025-07-11 at 9 39 34 am" src="https://github.com/user-attachments/assets/52132c0b-3913-4a09-aac1-cb70cad5129c" />


#### 步驟 4: 建立聊天機器人 UI 並進行 AWS 部署
在聊天區域中，輸入以下提示：

```
Build and deploy a simple chatbot UI. I want the files to be hosted on S3 and served by CloudFront. For security reasons, I do not want public access to my S3 bucket. Also, do not enable versioning for the S3 bucket.

The chatbot UI interacts with the back end with POST requests. We will build the back end separately in later steps. For the time being, when the user enters a message, the chatbot UI does not send the POST request, but simply respond with an ACK.

Additional requirements:
- Clean, modern interface with a dark theme
- Chat messages displayed in a conversation format
- Input field for user messages and send button
- Title showing "AWS Bedrock 聊天機器人" (AWS Bedrock Chatbot)
- Support for Chinese and English text
- Responsive design that works on different screen sizes
- When user sends a message, show "ACK" response as placeholder
```

**提示說明：**
- 建構並部署一個簡單的聊天機器人 UI
- 檔案將託管在 S3 上並透過 CloudFront 提供服務
- 基於安全考量，S3 儲存桶不允許公開存取
- 不啟用 S3 儲存桶版本控制
- 暫時使用 "ACK" 回應作為後端互動的佔位符

#### 步驟 5: 檢視產生的基礎架構和程式碼
1. Kiro 將產生：
   - 聊天機器人 UI 檔案（HTML、CSS、JavaScript）
   - 用於 S3 和 CloudFront 的 AWS CloudFormation 或 CDK 範本
   - 部署腳本或指示
2. 檢視產生的檔案和基礎架構程式碼
3. 先在本地測試介面
4. 使用 Kiro 的聊天功能進行調整：
   - "讓聊天氣泡更圓潤"
   - "調整 CloudFront 分發設定"
   - "改善 S3 儲存桶安全配置"

#### 步驟 6: 部署到 AWS
1. 遵循 Kiro 的部署指示
2. 驗證以下項目：
   - S3 儲存桶已建立且無公開存取權限
   - CloudFront 分發已正確配置
   - S3 儲存桶已停用版本控制
3. 測試已部署的聊天機器人 UI
4. 確認發送訊息時 ACK 回應正常運作

### 📁 預期專案結構
完成後，您的專案應包含：
```
MyCoolChatbot/
├── src/
│   ├── index.html          # 主要 HTML 檔案
│   ├── styles.css          # 聊天機器人樣式
│   └── script.js           # 具有 ACK 功能的 JavaScript
├── infrastructure/
│   ├── cloudformation.yaml # AWS 基礎架構範本
│   └── deploy.sh           # 部署腳本
├── README.md               # 專案文件
└── package.json            # 專案配置（如適用）
```

### 🎨 預期結果
您的聊天機器人應該看起來像這樣：

<img width="1451" height="999" alt="image (33)" src="https://github.com/user-attachments/assets/acaf9da2-b454-4f55-96f8-50442153e309" />


**已實現的主要功能：**
- 符合 AWS 設計模式的深色主題介面
- 雙語支援（中文/英文）
- 具有適當間距的乾淨訊息氣泡
- 具有發送按鈕的響應式輸入區域
- 具有 AWS Bedrock 品牌的專業標題
- ACK 回應功能（後端的佔位符）
- 使用 CloudFront 分發的 S3 託管
- 安全的 S3 儲存桶配置（無公開存取）
- S3 儲存桶未啟用版本控制

### 🔧 下一步
聊天機器人 UI 部署完成後：
1. 在 CloudFront URL 上徹底測試介面
2. 驗證 ACK 回應正常運作
3. 檢查 AWS 控制台以確認：
   - S3 儲存桶無公開存取權限
   - CloudFront 分發處於活躍狀態
   - S3 未啟用版本控制
4. 準備練習 2，我們將建構後端 API

### 💡 成功秘訣
- 使用 Kiro 的對話式方法 - 用自然語言描述您想要的內容
- 不要猶豫要求修改或改進
- Kiro 會從您的回饋中學習，所以請具體說明您喜歡或不喜歡的地方
- 充分利用 Vibe 模式的迭代特性

### 🐛 疑難排解
如果遇到問題：

**本地開發：**
1. 檢查所有檔案是否已正確儲存
2. 驗證您的瀏覽器支援現代 JavaScript 功能
3. 透過發送訊息測試 ACK 功能

**AWS 部署：**
1. 驗證 AWS CLI 已正確配置
2. 檢查 S3 儲存桶權限（不應為公開）
3. 確認 CloudFront 分發狀態為「已部署」
4. 測試 CloudFront URL，而非直接使用 S3 URL

**常見問題：**
- 如果部署失敗：檢查 S3 和 CloudFront 的 AWS 權限
- 如果 ACK 無法運作：檢查 JavaScript 控制台是否有錯誤
- 如果樣式損壞：檢查已部署版本中的 CSS 檔案路徑

使用 Kiro 的聊天功能尋求協助：「部署失敗了，您能協助排解 CloudFormation 範本的問題嗎？」

---

### ✅ 成功標準
當您完成以下項目時，練習即告完成：
- [ ] 聊天機器人 UI 在本地運行並具有 ACK 回應
- [ ] 已建立無公開存取權限的 S3 儲存桶
- [ ] CloudFront 分發正在提供聊天機器人 UI 服務
- [ ] S3 儲存桶未啟用版本控制
- [ ] 可透過 CloudFront URL 存取聊天機器人
- [ ] 已部署版本中的 ACK 回應正常運作

