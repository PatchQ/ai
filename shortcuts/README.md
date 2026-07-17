# iOS Shortcut Files — Kobe Taipei 2026 Trip

這個 directory 包含 4 個 iOS Shortcut 嘅 import-ready **JSON definition** (基於 Shortcuts Playground schema)。
iPhone 用戶可以:

1. 打開 `https://shortcutsplayground.com/` (Mac/PC) 或 **Shortcuts app** (iPhone)
2. Copy JSON 內容 → Import
3. Save as shortcut 命名為指定名稱

或者用 Quick Setup:

---

## 🚀 Quick Setup (推薦)

### iPhone:
1. 打開 **Shortcuts** app
2. Tap 右上 **+** → 創建新 Shortcut
3. 命名為指定名稱 (e.g. `Hotel PDF - Daiwa Roynet Kobe`)
4. 加以下 Actions (按順序):

| # | Action | 設定 |
|---|--------|------|
| 1 | **Get Contents of URL** | URL = `Shortcut Input` (預設) |
| 2 | **Save File** | Destination Folder = 「我的 iPhone → 神戶2026」; Filename = `daiwa-roynet-kobe.pdf`; Overwrite = ✅ |

5. Tap **Settings** (右上 ⚙️):
   - ☑️ **Show in Share Sheet**
   - ☑️ **Allow Running When Locked**
   - ☑️ **Receive Shortcut Input** (URLs type)
6. **Done** ✅

---

## 📋 4 個 Shortcut 配置

### 1️⃣ Hotel PDF - Daiwa Roynet Kobe
- **Filename**: `daiwa-roynet-kobe.pdf`
- **Source URL**: `https://patchq.github.io/ai/pdfs/daiwa-roynet-kobe.pdf`
- **Days**: Day 1 (7/27)

### 2️⃣ Hotel PDF - USJ Oriental
- **Filename**: `usj-oriental.pdf`
- **Source URL**: `https://patchq.github.io/ai/pdfs/usj-oriental.pdf`
- **Days**: Day 3 (7/29)

### 3️⃣ Hotel PDF - GRIDS Osaka Namba
- **Filename**: `grids-osaka-namba.pdf`
- **Source URL**: `https://patchq.github.io/ai/pdfs/grids-osaka-namba.pdf`
- **Days**: Day 4 (7/30)

### 4️⃣ Hotel PDF - Palais de Chine Taipei
- **Filename**: `palais-de-chine.pdf`
- **Source URL**: `https://patchq.github.io/ai/pdfs/palais-de-chine.pdf`
- **Days**: Day 6 (8/1)

---

## 🔧 Advanced: 一次過 build 4 個 Shortcut

在 iPhone Shortcuts app，創建 **「Master Shortcut: Setup All Hotel PDFs」**，加 Actions:

```
1. Repeat [4 times] with index i:
   a. Switch on i:
      - Case 1: 
        - Get Contents of URL: https://patchq.github.io/ai/pdfs/daiwa-roynet-kobe.pdf
        - Save File: 神戶2026/daiwa-roynet-kobe.pdf
      - Case 2:
        - Get Contents of URL: https://patchq.github.io/ai/pdfs/usj-oriental.pdf
        - Save File: 神戶2026/usj-oriental.pdf
      - Case 3:
        - Get Contents of URL: https://patchq.github.io/ai/pdfs/grids-osaka-namba.pdf
        - Save File: 神戶2026/grids-osaka-namba.pdf
      - Case 4:
        - Get Contents of URL: https://patchq.github.io/ai/pdfs/palais-de-chine.pdf
        - Save File: 神戶2026/palais-de-chine.pdf
```

完成後，運行一次 → 4 個 PDF 全部下載到「神戶2026」folder。

---

## 🎯 配套 PWA Workflow

Trip 期間使用 `https://patchq.github.io/ai/`:
1. 開 PWA → 📅 日程 → Day X
2. 見到 🟢 綠色 check-in panel
3. Tap **⚡ iOS Shortcut** button
4. iOS 自動 trigger Shortcut → 下載 PDF → 存到「我的 iPhone → 神戶2026」
5. Files app 自動打開，顯示新下載的 PDF ✅