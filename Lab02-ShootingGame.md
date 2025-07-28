# Kiro 入門實作

歡迎您來到 Kiro 實作體驗！在這個實驗中，您將學習如何使用 Kiro 的 AI 能力來快速且高效地建構應用程式。

## 練習 2: 建構網頁射擊遊戲並部署到 AWS

在這個練習中，您將使用 Kiro 建立一個功能完整的網頁射擊遊戲，包含敵人血條、道具系統、Boss 關卡等進階功能，並將其部署到 AWS 無伺服器架構。

### 🎯 學習目標
- 使用 Kiro 建構複雜的互動式網頁遊戲
- 實作 AWS 無伺服器架構部署
- 掌握 AWS 資源管理和清理

### 📋 前置需求
- 具有完整權限的 AWS 帳戶
- 已配置 AWS CLI

### 🚀 逐步操作指南

### 📋 前置需求
- 已安裝並運行 Kiro IDE
- 具有 S3 和 CloudFront 存取權限的 AWS 帳戶
- 已配置 AWS CLI（用於部署）

#### 步驟 1: 建立專案資料夾
1. 在您的電腦上，建立一個名為 `MyShootingGame` 的資料夾
2. 這將成為您聊天機器人應用程式的專案工作區

#### 步驟 2: 在 Kiro 中開啟專案
1. 啟動 Kiro IDE
2. 點擊 **"Open a project"** 按鈕
3. 選擇剛才建立的 `MyShootingGame` 資料夾
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

#### 步驟 4: 建立遊戲專案
1. 在您的電腦上，建立一個名為 `MyShootingGame` 的資料夾
2. 在 Kiro 中開啟這個專案
3. 選擇 **"Vibe"** 模式進行開發

#### 步驟 5: 建立基礎射擊遊戲
在 Kiro 的聊天區域中，輸入以下提示：

```
Create a web-base shooting game and deploy to AWS

Could you help me to build a web-base shooting game
```

**提示說明：**
- 建立一個基於網頁的射擊遊戲
- 包含基本的射擊機制和敵人系統
- 準備部署到 AWS 環境

#### 步驟 6: 改善遊戲控制
當基礎遊戲建立完成後，使用以下提示改善操作體驗：

```
Some time the control is hard to target the enemies? Please help me to improve it.
```

**改善重點：**
- 優化瞄準機制
- 雙重控制支援：
  - **鍵盤控制**: WASD 移動，空白鍵射擊
  - **滑鼠/觸控控制**: 移動游標/手指移動，點擊/觸碰射擊
- 增加輔助瞄準功能

#### 步驟 7: 新增敵人血條和遊戲說明
繼續使用以下提示增強遊戲功能：

```
Please help me add a health bar on enemies to understand how many time left to take down it. Meanwhile, please add the how-to-play on the page
```

**新增功能：**
- 敵人血條顯示
- 遊戲操作說明頁面
- 視覺化的生命值指示器

#### 步驟 8: 實作道具系統
使用以下提示新增道具機制：

```
I would like to add some random dropped items to temporarily power up myself. Such as shooting more fast, or shooting more wide.
```

**道具系統包含：**
- 隨機掉落的強化道具
- **Triple Shot**: 三重射擊能力
- **Rapid Fire**: 快速射擊模式
- **Shield**: 防護盾保護
- 臨時性增益效果

#### 步驟 9: 新增 Boss 關卡系統
使用以下提示實作進階關卡機制：

```
In increments of five thousand, I would like to have a boss stage and increase the level difficulty
```

**Boss 系統特色：**
- 每 5000 分出現 Boss 關卡
- 逐步增加遊戲難度
- 特殊的 Boss 戰鬥機制

#### 步驟 10: 部署到 AWS 無伺服器架構
使用以下提示進行 AWS 部署：

```
Can you help me deploy to my AWS Account with serverless architecture? Please make sure the AWS CLI command you use is with "--no-paginate" and "--no-cli-pager"

Please deploy
```
**部署要求：**
- 使用 AWS 無伺服器架構
- 所有 AWS CLI 命令必須包含 `--no-paginate` 和 `--no-cli-pager` 參數
- 自動化部署流程

#### 步驟 11: 資源清理
完成測試後，使用以下提示清理 AWS 資源：

```
Please help me to terminate the related resources from my AWS account.
```

### 📁 預期專案結構
完成後，您的專案可能包含：
```
MyShootingGame/
├── src/
│   ├── index.html              # 主遊戲頁面
│   ├── game.js                 # 遊戲邏輯
│   ├── styles.css              # 遊戲樣式
│   ├── assets/                 # 遊戲資源
│   │   ├── sprites/            # 精靈圖片
│   │   └── sounds/             # 音效檔案
│   └── instructions.html       # 遊戲說明頁面
├── infrastructure/
│   ├── serverless.yml          # Serverless 配置
│   ├── cloudformation.yaml     # AWS 基礎架構
│   └── deploy.sh               # 部署腳本
├── scripts/
│   ├── deploy.sh               # 部署腳本
│   └── cleanup.sh              # 資源清理腳本
└── README.md                   # 專案文件
```

### 🎮 預期遊戲功能

完成後，您的射擊遊戲應該看起來像這樣：

#### 遊戲主畫面

<img width="1056" height="770" alt="截圖 2025-07-28 上午9 40 07" src="https://github.com/user-attachments/assets/af875885-5386-44c0-931a-953629b23c13" />

#### 遊戲說明頁面
<img width="1134" height="832" alt="截圖 2025-07-28 上午9 40 02" src="https://github.com/user-attachments/assets/8d93f33f-ad5f-4a2e-8c6b-51bee6a3f3df" />

### 🏗️ AWS 架構

**無伺服器組件：**
- **S3**: 靜態網站託管
- **CloudFront**: 全球內容分發
- **Lambda**: 後端邏輯處理（如需要）
- **API Gateway**: API 管理（如需要）
- **DynamoDB**: 分數記錄（如需要）

### 🔧 部署驗證

部署完成後，驗證以下項目：
1. 遊戲可透過 CloudFront URL 正常存取
2. 所有遊戲功能正常運作
3. AWS 資源已正確建立
4. 成本控制在合理範圍內

### 💡 開發秘訣

**與 Kiro 互動時：**
- 逐步建構功能，不要一次要求太多
- 測試每個功能後再繼續下一步
- 具體描述您想要的遊戲體驗
- 利用 Kiro 的迭代能力優化遊戲

**遊戲開發最佳實踐：**
- 保持遊戲循環的流暢性
- 適當的視覺回饋
- 平衡的遊戲難度曲線
- 響應式設計支援多種裝置

### 🐛 疑難排解

**遊戲開發問題：**
- 如果遊戲卡頓：檢查遊戲循環和渲染效率
- 如果控制不順：調整輸入處理和碰撞檢測
- 如果道具不生效：檢查狀態管理和計時器

**AWS 部署問題：**
- 如果部署失敗：檢查 AWS 權限和配額
- 如果遊戲無法載入：檢查 S3 和 CloudFront 配置
- 如果 CLI 命令失敗：確認已加入 `--no-paginate` 和 `--no-cli-pager`

**資源清理問題：**
- 如果清理不完整：手動檢查 AWS 控制台
- 如果有殘留費用：檢查所有相關服務
- 使用 Kiro 協助：「請協助我檢查是否有遺漏的 AWS 資源」

### ✅ 成功標準

當您完成以下項目時，練習即告完成：
- [ ] 基礎射擊遊戲正常運作（如截圖所示的遊戲畫面）
- [ ] 改善的控制系統提供良好體驗（支援鍵盤和滑鼠控制）
- [ ] 敵人血條和遊戲說明已實作（包含完整的 How to Play 頁面）
- [ ] 道具系統功能完整（Triple Shot, Rapid Fire, Shield 等）
- [ ] Boss 關卡系統正常運作（分數里程碑觸發）
- [ ] 成功部署到 AWS 無伺服器架構
- [ ] 所有 AWS CLI 命令使用正確參數（--no-paginate 和 --no-cli-pager）
- [ ] 能夠完全清理 AWS 資源

**視覺驗證：**
- [ ] 遊戲畫面與參考截圖相似（黑色背景，彩色敵人，三角形玩家）
- [ ] 操作說明頁面完整顯示控制方式和遊戲規則
- [ ] 分數和生命值正確顯示在畫面左上角

### 🎯 學習成果

完成此練習後，您將能夠：
- 使用 Kiro 建構複雜的互動式應用程式
- 實作完整的遊戲機制和系統
- 掌握 AWS 無伺服器架構部署
- 管理和清理 AWS 資源
- 應用遊戲開發最佳實踐


**🎮 準備好建構您的射擊遊戲了嗎？讓我們開始吧！**
