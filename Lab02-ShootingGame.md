# Lab 2: AWS 整合與進階應用

歡迎來到 Lab 2！在這個實驗中，您將學習如何使用 Kiro 建構更複雜的應用程式，並將其部署到 AWS 的無伺服器架構上。

## 練習 2: 建構網頁射擊遊戲並部署到 AWS

在這個練習中，您將使用 Kiro 建立一個功能完整的網頁射擊遊戲，包含敵人血條、道具系統、Boss 關卡等進階功能，並將其部署到 AWS 無伺服器架構。

### 🎯 學習目標
- 使用 Kiro 建構複雜的互動式網頁遊戲
- 學習遊戲開發的最佳實踐
- 實作 AWS 無伺服器架構部署
- 掌握 AWS 資源管理和清理

### 📋 前置需求
- 完成 Lab 1 的練習
- 具有完整權限的 AWS 帳戶
- 已配置 AWS CLI
- 基本的遊戲開發概念

### 🚀 逐步操作指南

#### 步驟 1: 建立遊戲專案
1. 在您的電腦上，建立一個名為 `MyShootingGame` 的資料夾
2. 在 Kiro 中開啟這個專案
3. 選擇 **"Vibe"** 模式進行開發

#### 步驟 2: 建立基礎射擊遊戲
在 Kiro 的聊天區域中，輸入以下提示：

```
Create a web-base shooting game and deploy to AWS

Could you help me to build a web-base shooting game
```

**提示說明：**
- 建立一個基於網頁的射擊遊戲
- 包含基本的射擊機制和敵人系統
- 準備部署到 AWS 環境

#### 步驟 3: 改善遊戲控制
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

#### 步驟 4: 新增敵人血條和遊戲說明
繼續使用以下提示增強遊戲功能：

```
Please help me add a health bar on enemies to understand how many time left to take down it. Meanwhile, please add the how-to-play on the page
```

**新增功能：**
- 敵人血條顯示
- 遊戲操作說明頁面
- 視覺化的生命值指示器

#### 步驟 5: 實作道具系統
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

#### 步驟 6: 新增 Boss 關卡系統
使用以下提示實作進階關卡機制：

```
In increments of five thousand, I would like to have a boss stage and increase the level difficulty
```

**Boss 系統特色：**
- 每 5000 分出現 Boss 關卡
- 逐步增加遊戲難度
- 特殊的 Boss 戰鬥機制

#### 步驟 7: 部署到 AWS 無伺服器架構
使用以下提示進行 AWS 部署：

```
Can you help me deploy to my AWS Account with serverless architecture? Please make sure the AWS CLI command you use is with "--no-paginate" and "--no-cli-pager"

Please deploy
```

**部署要求：**
- 使用 AWS 無伺服器架構
- 所有 AWS CLI 命令必須包含 `--no-paginate` 和 `--no-cli-pager` 參數
- 自動化部署流程

#### 步驟 8: 資源清理
完成測試後，使用以下提示清理 AWS 資源：

```
Please help me to terminate the related resources from my AWS account.
```

### 📁 預期專案結構
完成後，您的專案應包含：
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
![Space Shooter 遊戲畫面](../resources/images/shooting-game-gameplay.png)

#### 遊戲說明頁面
![Space Shooter 操作說明](../resources/images/shooting-game-instructions.png)

**核心遊戲機制：**
- 流暢的射擊控制系統（鍵盤 WASD 或滑鼠控制）
- 多種類型的敵人（綠色和紅色方塊）
- 敵人血條顯示
- 分數和生命值系統

**進階功能：**
- 隨機道具掉落系統
- 臨時強化效果（Triple Shot, Rapid Fire, Shield）
- Boss 關卡（每達到分數里程碑）
- 難度遞增機制

**使用者介面：**
- 專業的遊戲操作說明頁面
- 即時分數和生命值顯示
- 鍵盤和滑鼠/觸控雙重控制支援
- 道具效果提示和說明

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
