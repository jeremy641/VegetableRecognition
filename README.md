# 🍎 AI 蔬果辨識系統 🍌

一個結合機器學習和 ChatGPT 的智能蔬果辨識系統，能夠檢測蔬果新鮮度並提供專業建議。

## ✨ 功能特色

### 🔍 雙重辨識模式
- **即時攝像頭辨識**：使用網路攝像頭進行即時蔬果檢測
- **圖片上傳辨識**：支援拖拽或點擊上傳圖片進行分析

### 🤖 AI 智能建議
- **自動觸發**：當辨識信心度達 70% 以上時自動獲取 ChatGPT 建議
- **專業內容**：提供處理保存、食用料理、營養科普、注意事項等建議
- **即時對話**：右側對話介面提供流暢的互動體驗

### 🎯 辨識類別
- 🍎 **蘋果**（良好/腐爛/未成熟）
- 🍌 **香蕉**（良好/腐爛/未成熟）
- 🍊 **橘子**（良好/腐爛/未成熟）
- ❓ **其他物品**

## 🚀 快速開始

### 前置需求
- 現代瀏覽器（Chrome、Firefox、Safari、Edge）
- 網路連接（載入 AI 模型和 ChatGPT API）
- 攝像頭（可選，用於即時辨識）
- OpenAI API Key（用於 ChatGPT 建議功能）

### 安裝步驟
1. 下載 `index.html` 檔案
2. 在瀏覽器中開啟檔案
3. 設定 OpenAI API Key（詳見下方設定步驟）
4. 等待 AI 模型載入完成
5. 開始使用！

### 🔑 OpenAI API Key 設定步驟

**步驟 1：開啟網頁**
- 直接雙擊 `index.html` 文件開啟

**步驟 2：開啟瀏覽器開發者工具**
- 按 `F12` 鍵，或右鍵選擇「檢查」

**步驟 3：切換到 Console 標籤**
- 在開發者工具中點擊「Console」標籤

**步驟 4：設定 API Key**
在 Console 中輸入以下指令（請替換為您的真實 API Key）：
```javascript
localStorage.setItem('openai_api_key', 'your-actual-api-key-here');
```

**步驟 5：驗證設定**
在 Console 中輸入以下指令檢查是否設定成功：
```javascript
console.log('API Key 已設定:', !!localStorage.getItem('openai_api_key'));
```
如果顯示 `true` 表示設定成功。

**步驟 6：重新載入頁面**
- 按 `F5` 或 `Ctrl+R` 重新載入頁面

## 🎮 使用方法

### 攝像頭辨識
1. 點擊「開始攝像頭辨識」按鈕
2. 允許瀏覽器存取攝像頭
3. 將蔬果放在攝像頭前
4. 系統會即時顯示辨識結果
5. 信心度達 70% 以上時自動獲取 AI 建議

### 圖片上傳辨識
1. 點擊上傳區域或拖拽圖片到指定區域
2. 系統自動開始分析圖片
3. 查看辨識結果和信心度
4. 自動獲取 ChatGPT 專業建議

## 🎨 介面設計

### 響應式佈局
- **桌面版**：左右雙欄設計，辨識功能在左，AI 建議在右
- **行動版**：上下堆疊佈局，適應小螢幕顯示

### 視覺特色
- 漸層背景設計，提供舒適的視覺體驗
- 狀態指示器：綠色（良好）、紅色（腐爛）、橙色（未成熟）
- 載入動畫和淡入效果
- 信心度達 90% 時播放提示音

## 🔧 技術架構

### 前端技術
- **HTML5**：結構化網頁內容
- **CSS3**：響應式設計和動畫效果
- **JavaScript**：互動邏輯和 API 整合

### AI 模型
- **Teachable Machine**：Google 提供的機器學習平台
- **TensorFlow.js**：瀏覽器端機器學習框架
- **模型 URL**：`https://teachablemachine.withgoogle.com/models/95JhNZvMx/`

### API 整合
- **OpenAI ChatGPT API**：提供專業蔬果建議
- **模型**：GPT-3.5-turbo
- **功能**：自動生成處理建議、營養科普、料理方法等

## 📊 辨識準確度

### 信心度指標
- **90% 以上**：高信心度（綠色顯示 + 提示音）
- **50-89%**：中等信心度（橙色顯示）
- **50% 以下**：低信心度（灰色顯示）

### 最佳辨識條件
- 光線充足的環境
- 蔬果佔畫面主要部分
- 背景簡潔，避免干擾
- 圖片清晰，無模糊

## 🛠️ 自訂設定

### OpenAI API 設定
```javascript
const OPENAI_API_KEY = "your-api-key-here";
const OPENAI_API_URL = "https://api.openai.com/v1/chat/completions";
```

### 模型參數調整
```javascript
// 調整信心度閾值
if (probability >= 0.7) {  // 可調整為 0.5-0.9
    getChatGPTAdvice(className, confidence);
}

// 調整 ChatGPT 參數
{
    model: "gpt-3.5-turbo",     // 可改為 gpt-4
    max_tokens: 1000,           // 回應長度
    temperature: 0.7            // 創意程度 0-1
}
```

## 🔒 隱私與安全

### 資料處理
- 所有圖片處理在本地瀏覽器進行
- 不會上傳圖片到外部伺服器
- 僅辨識結果會傳送給 ChatGPT API

### API 安全
- OpenAI API Key 需要妥善保管
- 建議使用環境變數或配置檔案管理
- 定期檢查 API 使用量和費用

## 🔍 設定驗證與故障排除

### 🔧 API Key 設定驗證

**方法 1：設定 API Key**
```javascript
localStorage.setItem('openai_api_key', 'your-actual-api-key-here');
```

**方法 2：檢查設定狀態**
```javascript
console.log('API Key 已設定:', !!localStorage.getItem('openai_api_key'));
```

**方法 3：查看完整配置**
```javascript
console.log('API 配置:', API_CONFIG);
```

**方法 4：測試 API 連接**
```javascript
// 檢查 API Key 格式
const apiKey = localStorage.getItem('openai_api_key');
console.log('API Key 長度:', apiKey ? apiKey.length : 0);
console.log('API Key 前綴:', apiKey ? apiKey.substring(0, 7) : 'null');
```

### 🐛 常見問題

### Q: 攝像頭無法啟動？
A: 檢查瀏覽器權限設定，確保允許網站存取攝像頭。

### Q: AI 模型載入失敗？
A: 確保網路連接正常，模型檔案較大需要時間載入。

### Q: ChatGPT 建議無法顯示？
A: 
1. 檢查 API Key 是否正確設定（使用上方驗證方法）
2. 確認 OpenAI 帳戶有足夠額度
3. 檢查網路連接是否正常
4. 查看瀏覽器 Console 是否有錯誤訊息

### Q: 辨識準確度不高？
A: 改善光線條件，確保蔬果清晰可見，避免背景干擾。

### Q: API Key 設定後仍無法使用？
A: 
1. 確認重新載入頁面
2. 檢查 API Key 是否完整（不要有多餘空格）
3. 確認使用的是有效的 OpenAI API Key
4. 檢查瀏覽器是否支援 localStorage

### 🔍 調試步驟

**步驟 1：檢查基本設定**
```javascript
// 在瀏覽器 Console 中執行
console.log('localStorage 支援:', typeof(Storage) !== "undefined");
console.log('API Key 存在:', !!localStorage.getItem('openai_api_key'));
console.log('模型載入狀態:', !!window.model);
```

**步驟 2：檢查網路連接**
```javascript
// 測試網路連接
fetch('https://api.openai.com/v1/models', {
    headers: {
        'Authorization': `Bearer ${localStorage.getItem('openai_api_key')}`
    }
}).then(response => {
    console.log('API 連接狀態:', response.status);
}).catch(error => {
    console.log('API 連接錯誤:', error);
});
```

**步驟 3：清除設定重新開始**
```javascript
// 清除所有設定
localStorage.removeItem('openai_api_key');
console.log('設定已清除，請重新設定 API Key');
```

## 📈 未來規劃

### 功能擴展
- [ ] 支援更多蔬果類別
- [ ] 新增營養成分資料庫
- [ ] 食譜推薦功能
- [ ] 保存期限預測

### 技術優化
- [ ] 模型準確度提升
- [ ] 離線模式支援
- [ ] 多語言介面
- [ ] 行動 App 版本

## 🤝 貢獻指南

歡迎提交 Issue 和 Pull Request 來改善這個專案！

### 開發環境
1. Fork 這個專案
2. 建立功能分支
3. 提交變更
4. 發起 Pull Request

## 📄 授權條款

本專案採用 MIT 授權條款，詳見 LICENSE 檔案。

## 📞 聯絡資訊

如有任何問題或建議，歡迎聯絡：
- 📧 Email: [jeremy641@gmail.com]
- 🐙 GitHub: [jeremy641]

---

**⭐ 如果這個專案對您有幫助，請給我們一個星星！**

## 🙏 致謝

- [Google Teachable Machine](https://teachablemachine.withgoogle.com/) - 提供機器學習平台
- [TensorFlow.js](https://www.tensorflow.org/js) - 瀏覽器端機器學習框架
- [OpenAI](https://openai.com/) - ChatGPT API 服務
- 所有貢獻者和使用者的支持
