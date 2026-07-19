# iOS Shortcut Files — Kobe Taipei 2026 Trip

PWA 簡化版: 每個 check-in day 嘅 panel 只有 1 個 button (📂 打開「檔案」app)，透過 iOS Shortcut 觸發。

---

## 🚀 Setup (3 分鐘)

### 預先建立 folder (重要!):
1. iPhone **檔案** app → 「我的 iPhone」
2. 長按空白位 → **新增檔案夾** → 命名 `神戶2026`

### 創建 Shortcut:
1. 打開 **Shortcuts** app
2. Tap 右上 **+** → 創建新 Shortcut
3. 命名為 **`Open Files App`** (必須完全匹配, 包括大小寫)
4. 加 1 個 Action:
   - **Open Folder** (iOS 16+) → Folder = 「我的 iPhone → 神戶2026」
5. Settings ⚙️ → ☑️ Show in Share Sheet + ☑️ Allow Running When Locked
6. **Done** ✅

---

## 🎯 用戶 workflow

Trip 期間:
1. iPhone Safari → 開 PWA `https://patchq.github.io/ai/`
2. 📅 日程 → Day X (check-in day)
3. 見到 🟢 綠色 check-in panel + 📂 打開「檔案」app button
4. Tap button → iOS Shortcut 自動 trigger → 「檔案」app 自動打開「神戶2026」folder
5. 直接揀 PDF 出嚟用 ✅

---

## 📲 iOS 16+ 「Open Folder」action 詳細

`Open Folder` 係 iOS 16 開始加入嘅新 action:
- 直接跳到指定 folder 喺「檔案」app 入面
- 如果 folder 唔存在, action 會 fail (silently 或 throw)
- 必須 pre-create folder

可以設定嘅 folder 例子:
- 「我的 iPhone」 → 打開 root
- 「我的 iPhone / 神戶2026」 → 打開指定 subfolder
- 「iCloud Drive」 → 打開 iCloud
- 「最近項目」 → 打開 recents

---

## 🔧 Trip 完整 iPhone workflow (推薦)

1. **出發前** (一次性 setup):
   - iPhone **檔案** app → 「我的 iPhone」 → 長按 → 新增檔案夾 → 命名 `神戶2026`
   - iPhone **Shortcuts** app → 創建 `Open Files App` Shortcut → 加 **Open Folder** action → Folder = `我的 iPhone / 神戶2026`
   
2. **Trip 期間** (每次 check-in):
   - 抵達酒店 → 開 PWA → tap 📂 button
   - 「檔案」app 自動打開 → 見到 `神戶2026` folder
   - 拎酒店寄嚟嘅 booking confirmation PDF (已經預先 download 或 AirDrop 入呢個 folder)
   - 出示比 front desk check-in

---

## 🛠️ 預先 download 所有酒店 PDF

1. 打開 PWA → 主頁有 4 個酒店 card
2. Tap 每個酒店 card → 連到官網
3. 自己登入下載 booking confirmation PDF
4. 儲存到 `我的 iPhone / 神戶2026/` folder (用 iPhone 「檔案」app)

或者用 iCloud 共享連結:
- 將 PDF 上傳到 iCloud Drive
- 用 PWA 入面嘅 `shortcuts://run-shortcut?name=Open%20Files%20App` button
- 直接打開 iCloud folder

---

## 💡 Tips

- 將 PWA 加到 iPhone **Home Screen**: Safari → Share → Add to Home Screen → 用日曆 icon 較易搵到
- 第一次 setup 用 Mac (如果有) 更方便: Shortcuts app on macOS Monterey+ 都支援
- 如要進階 trigger (例如指定 PDF 自動下載 + 開啟)，可加 Get Contents of URL + Save File action 在 Open Folder 之前