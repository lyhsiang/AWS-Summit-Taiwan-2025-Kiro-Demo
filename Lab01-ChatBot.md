#  Kiro 入門實作

歡迎您來到 Kiro 實作體驗！在這個實驗中，您將學習如何使用 Kiro 的 AI 能力來快速且高效地建構應用程式。

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

<img width="472" height="360" alt="Screenshot 2025-07-11 at 9 39 34 am" src="https://github.com/user-attachments/assets/52132c0b-3913-4a09-aac1-cb70cad5129c" />

#### 步驟 3: 存取 Let's Build 功能
1. 在 Kiro 中，導航到 **"Let's build"** 頁面
2. 您將看到兩個可用選項：
   - **Vibe** - 先聊天，再建構。探索想法並在發現需求時進行迭代
   - **Spec** - 先規劃，再建構。在開始編碼前建立需求和設計

3. 在這個練習中，選擇 **"Vibe"** 模式
4. 將模型設定為 **"Claude Sonnet 3.7"**（或最新可用版本）
5. 確保 **Autopilot** 已啟用

<img width="472" height="360" alt="Screenshot 2025-07-11 at 9 42 17 am" src="https://github.com/user-attachments/assets/ea7ce532-d7bc-4c7e-bf4a-ae1cb1701c49" />



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
完成後，您的專案可能包含：
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
- 具有 AWS Bedrock 的標題
- ACK 回應功能正常
- 使用 CloudFront 分發的 S3 託管
- 安全的 S3 儲存桶配置（無公開存取）

### 🔧 下一步
聊天機器人 UI 部署完成後：
1. 在瀏覽器上輸入 CloudFront URL 測試介面
2. 回應正常運作
3. 檢查 AWS 控制台以確認：
   - S3 儲存桶無公開存取權限
   - CloudFront 分發處於 active 狀態
4. 準備練習 2，我們將建構後端 API

### 💡 成功秘訣
- 使用 Kiro 的對話式方法 - 用自然語言描述您想要的內容
- 不要猶豫要求修改或改進
- Kiro 會從您的回饋中學習，所以請具體說明您喜歡或不喜歡的地方
- 充分利用 Vibe 模式的迭代特性

### 🐛 疑難排解

有時候，Kiro 可能會在某個問題上卡住很長時間。當這種情況發生時，您可以給出正確方向的提示。以下是我們在測試中發現的一些範例：

#### 🔧 **常見 Kiro 問題與解決方案**

**1. S3 儲存桶公開存取問題**
- **問題**: Kiro 嘗試建立具有公開存取權限的 S3 儲存桶，但這些嘗試被 AWS 組織中的服務控制政策 (SCP) 阻止
- **解決方案**: 告訴 Kiro「具有公開存取權限的 S3 儲存桶是安全風險。建議 Kiro 使用預簽名 URL 或使用 CloudFront 與 S3 通訊」

**2. S3 儲存桶政策名稱問題**
- **問題**: Kiro 嘗試在儲存桶政策中使用 S3 儲存桶名稱
- **解決方案**: 使用 ARN 而不是儲存桶名稱

**3. Bedrock 基礎模型存取問題**
- **問題**: 您需要在 Bedrock 控制台中手動啟用基礎模型 - Kiro 無法為您執行此操作。有時，Kiro 嘗試使用您沒有存取權限的基礎模型
- **解決方案**: 如果是這種情況，只需告訴 Kiro「您沒有存取此模型的權限」。Kiro 將更新程式碼以使用不同的基礎模型

**4. CloudFront 快取失效問題**
- **問題**: 當 Kiro 部署新版本的前端時，它可能會忘記使 CloudFront 上的快取版本失效。您最終會看到前端的舊版本
- **解決方案**: 手動使 CloudFront 分發的快取失效，或要求 Kiro 在部署腳本中包含快取失效步驟

**5. CloudFront URL 變更**
- **問題**: Kiro 可能會刪除先前的部署並重新部署堆疊。在這種情況下，您會獲得新的 CloudFront URL
- **解決方案**: 記錄新的 URL 並更新任何相關的參考

#### 🔍 **進階疑難排解**

**設定 MCP 以存取 AWS 文件**
如果 Kiro 能夠存取 AWS 文件，其中一些問題可以更快解決。您可以要求 Kiro 設定 MCP 以存取 AWS 文件伺服器：

```
設定 MCP，讓我們可以存取 AWS 文件。
```

**本地開發問題：**
1. 檢查所有檔案是否已正確儲存
2. 驗證您的瀏覽器支援現代 JavaScript 功能
3. 透過發送訊息測試 ACK 功能

**AWS 部署問題：**
1. 驗證 AWS CLI 已正確配置
2. 檢查 S3 儲存桶權限（不應為公開）
3. 確認 CloudFront 分發狀態為「已部署」
4. 測試 CloudFront URL，而非直接使用 S3 URL

**其他常見問題：**
- 如果部署失敗：檢查 S3 和 CloudFront 的 AWS 權限
- 如果 ACK 無法運作：檢查 JavaScript 控制台是否有錯誤
- 如果樣式損壞：檢查已部署版本中的 CSS 檔案路徑

#### 💬 **與 Kiro 有效溝通的技巧**

當遇到問題時，使用 Kiro 的聊天功能並提供具體的指導：

**範例對話：**
- 「部署失敗了，您能協助排解 CloudFormation 範本的問題嗎？」
- 「S3 儲存桶不應該有公開存取權限，請使用 CloudFront 來提供內容」
- 「請在部署後使 CloudFront 快取失效」
- 「我沒有存取 Claude 3.5 Sonnet 模型的權限，請使用其他可用的模型」

記住，Kiro 是一個學習型 AI 助手，清晰和具體的指導將幫助它更好地理解您的需求並提供適當的解決方案。

---

### ✅ 成功標準
當您完成以下項目時，練習即告完成：
- [ ] 聊天機器人 UI 在本地運行並具有 ACK 回應
- [ ] 已建立無公開存取權限的 S3 儲存桶
- [ ] CloudFront 分發正在提供聊天機器人 UI 服務
- [ ] S3 儲存桶未啟用版本控制
- [ ] 可透過 CloudFront URL 存取聊天機器人
- [ ] 已部署版本中的 ACK 回應正常運作


### ✅ 成功範例
https://d1anwh1nuk505t.cloudfront.net
