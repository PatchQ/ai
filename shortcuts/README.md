# iOS Shortcut Files — Kobe Taipei 2026 Trip

這個 directory 包含 4 個 iOS Shortcut 嘅 setup instructions + Master Setup。
iPhone 用戶可以喺 Shortcuts app 內自己 create。

---

## 🚀 Single Shortcut Setup (推薦)

### iPhone:
1. 打開 **Shortcuts** app
2. Tap 右上 **+** → 創建新 Shortcut
3. 命名為指定名稱 (e.g. `Hotel PDF - Daiwa Roynet Kobe`)
4. 加以下 Actions (按順序):

| # | Action | 設定 |
|---|--------|------|
| 1 | **Get Contents of URL** | URL = `Shortcut Input` (自動接收 PWA 傳入嘅 URL) |
| 2 | **Save File** | Destination Folder = 「我的 iPhone → 神戶2026」; Filename = `daiwa-roynet-kobe.pdf`; Overwrite = ✅ |
| 3 | **Open Folder** (iOS 16+) | Folder = 「我的 iPhone → 神戶2026」→ 自動打開「檔案」app 跳到呢個 folder |

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
- **Folder**: `我的 iPhone / 神戶2026/`

### 2️⃣ Hotel PDF - USJ Oriental
- **Filename**: `usj-oriental.pdf`
- **Source URL**: `https://patchq.github.io/ai/pdfs/usj-oriental.pdf`
- **Days**: Day 3 (7/29)
- **Folder**: `我的 iPhone / 神戶2026/`

### 3️⃣ Hotel PDF - GRIDS Osaka Namba
- **Filename**: `grids-osaka-namba.pdf`
- **Source URL**: `https://patchq.github.io/ai/pdfs/grids-osaka-namba.pdf`
- **Days**: Day 4 (7/30)
- **Folder**: `我的 iPhone / 神戶2026/`

### 4️⃣ Hotel PDF - Palais de Chine Taipei
- **Filename**: `palais-de-chine.pdf`
- **Source URL**: `https://patchq.github.io/ai/pdfs/palais-de-chine.pdf`
- **Days**: Day 6 (8/1)
- **Folder**: `我的 iPhone / 神戶2026/`

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
2. Show in Files → 我的 iPhone / 神戶2026/  ← Master 最後一步
```

完成後，運行一次 → 4 個 PDF 全部下載到「神戶2026」folder → 自動打開「檔案」app 顯示呢個 folder。

---

## 🎯 配套 PWA Workflow

Trip 期間使用 `https://patchq.github.io/ai/`:
1. 開 PWA → 📅 日程 → Day X
2. 見到 🟢 綠色 check-in panel
3. Tap **⚡ iOS Shortcut** button
4. iOS 自動 trigger Shortcut → 下載 PDF → 存到「我的 iPhone → 神戶2026」→ 自動打開「檔案」app 到呢個 folder

---

## 📲 iOS 16+ 「Open Folder」action 詳細

`Open Folder` 係 iOS 16 開始加入嘅新 action:
- 直接跳到指定 folder 喺「檔案」app 入面
- 如果 folder 唔存在, action 會 fail (silently 或 throw)
- 必須 pre-create folder「神戶2026」喺「我的 iPhone」內

Setup 步驟:
1. **預先建立 folder**: iPhone Files app → 「我的 iPhone」 → 長按空白 → 新增檔案夾 → 命名 `神戶2026`
2. **Shortcut 內 Setup Open Folder action**:
   - Tap `Open Folder`
   - Tap `Folder` field
   - Navigate 到 `我的 iPhone / 神戶2026`
   - Tap to select

完成後, 每次 tap shortcut button → iOS 自動:
- Download PDF from URL
- Save 到 `神戶2026/`
- 自動打開「檔案」app 跳到 `神戶2026/` folder
- user 見到新下載嘅 PDF, tap 開 PDF viewer

---

## 🛠️ 預先建立 Folder 「神戶2026」

喺 Shortcut 嘅 Save File action 內:
- Tap "Destination" → "Folders" → 下方 "+" → 命名 `神戶2026` → Tap "On My iPhone" parent
- 完成後呢個 folder 會喺 Files app「我的 iPhone」下方

或者手動:
1. iPhone Files app → "我的 iPhone"
2. 長按空白位 → "新增檔案夾" → 命名 `神戶2026`

---

## 📥 Trip 期間 workflow

1. 抵達酒店 → 打開 iPhone PWA
2. Tap ⚡ **iOS Shortcut** button
3. Shortcut runs:
   - Download PDF from GitHub Pages
   - Save to `神戶2026/` (Overwrite if existing)
   - Open PDF viewer (iOS 17+) or show folder
4. 拎 PDF 出嚟比酒店 front desk check-in ✅