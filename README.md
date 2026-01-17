# 🔍 BrowserOCR - 瀏覽器端 PaddleOCR 文字辨識工具

基於 PaddleOCR v5 的純瀏覽器端 OCR 文字辨識應用，無需後端伺服器，所有處理均在本地完成，保護您的隱私。

🔗 **線上展示**：[https://nicolaskodak.github.io/BrowserOcr/](https://nicolaskodak.github.io/BrowserOcr/)

## ✨ 功能特色

- 🖼️ **文字框偵測** - 自動偵測圖片中的文字區域
- 📝 **文字辨識** - 支援繁體中文、簡體中文、英文等多語言辨識
- 🔒 **隱私保護** - 完全在瀏覽器端運行，圖片不會上傳到任何伺服器
- 💾 **智慧快取** - 模型與字典自動快取於 IndexedDB，首次載入後即可離線使用
- 🎨 **優雅介面** - 採用莫蘭迪大地色系，提供舒適的視覺體驗
- ⚡ **即時反饋** - 顯示辨識進度和處理狀態
- 📊 **詳細結果** - 提供文字內容、信心度、坐標等完整資訊

## 🛠️ 技術棧

- **OCR 引擎**：PaddleOCR v5 (ONNX 格式)
- **推理框架**：ONNX Runtime Web
- **影像處理**：OpenCV.js
- **儲存方案**：IndexedDB
- **純前端**：原生 HTML/CSS/JavaScript

## 📦 本地部署

### 方法 1：直接開啟

1. 克隆儲存庫：
```bash
git clone https://github.com/nicolaskodak/BrowserOcr.git
cd BrowserOcr
```

2. 啟動本地伺服器：
```bash
# 使用 Python
python -m http.server 8000

# 或使用 Node.js
npx serve

# 或使用 PHP
php -S localhost:8000
```

3. 開啟瀏覽器訪問 `http://localhost:8000`

### 方法 2：部署到 GitHub Pages

1. Fork 此專案到您的 GitHub 帳號

2. 前往儲存庫的 Settings → Pages

3. 在 Source 選擇 `main` 分支，資料夾選擇 `/ (root)`

4. 點擊 Save，等待約 1-2 分鐘

5. 訪問 `https://你的使用者名稱.github.io/BrowserOcr/`

### 方法 3：部署到其他平台

支援部署到任何靜態網站託管服務：

- **Vercel**：連結 GitHub 儲存庫，自動部署
- **Netlify**：拖放資料夾或連結 Git
- **Cloudflare Pages**：連結 GitHub，選擇分支
- **Firebase Hosting**：使用 `firebase deploy`

## 📖 使用說明

1. **選擇圖片**：點擊「選擇圖片」按鈕，上傳包含文字的圖片
2. **等待載入**：首次使用時會自動下載模型（約 30-50MB），之後會從快取載入
3. **開始辨識**：點擊「偵測文字」按鈕開始處理
4. **查看結果**：
   - 預覽區會顯示偵測到的文字框
   - 右側文字框顯示完整辨識結果
   - 下方表格顯示每個文字框的詳細資訊

## 🔧 專案結構

```
BrowserOcr/
├── index.html          # 主頁面
├── assets/            
│   ├── opencv.js      # OpenCV.js 函式庫
│   └── ort.js         # ONNX Runtime (若有本地版本)
├── README.md          # 本文件
└── .gitignore         # Git 忽略檔案
```

## 🌐 瀏覽器支援

- ✅ Chrome 90+
- ✅ Edge 90+
- ✅ Safari 14+
- ✅ Firefox 88+

## ⚠️ 注意事項

- 首次使用需要下載模型檔案（約 30-50MB），請確保網路連線穩定
- 建議使用現代瀏覽器以獲得最佳效能
- 處理大尺寸圖片可能需要較長時間
- 若要清除快取的模型，請在瀏覽器開發者工具中刪除 IndexedDB 中的 `paddleocr_models_db`

## 🤝 貢獻

歡迎提交 Issue 或 Pull Request！

## 📄 授權

MIT License

## 🙏 致謝

- [PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR) - 優秀的 OCR 開源專案
- [ONNX Runtime](https://onnxruntime.ai/) - 高效能的推理引擎
- [OpenCV.js](https://docs.opencv.org/4.x/d5/d10/tutorial_js_root.html) - 強大的影像處理函式庫

---

如果這個專案對您有幫助，請給個 ⭐️ Star 支持一下！
