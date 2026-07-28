# Souji Rebrand Plan

> 離峰用 Pro 時照這個清單改 code

---

## 1. project.yml

```yaml
# 改這些：
name: PureMac → Souji
bundleIdPrefix: com.puremac → com.souji
# settings.base:
PRODUCT_BUNDLE_IDENTIFIER: com.puremac.app → com.souji.app
MARKETING_VERSION: 2.9.3 → 1.0.0
CURRENT_PROJECT_VERSION: 24 → 1
DEVELOPMENT_TEAM: H3WXHVTP97 → "" (先清空，之後有 Apple Developer 再填)
```

## 2. Info.plist

- `CFBundleName`: PureMac → Souji
- `CFBundleDisplayName`: PureMac → Souji
- `NSDesktopFolderUsageDescription`: PureMac → Souji
- `NSDocumentsFolderUsageDescription`: PureMac → Souji
- `NSDownloadsFolderUsageDescription`: PureMac → Souji
- `NSRemovableVolumesUsageDescription`: PureMac → Souji
- `NSSystemAdministrationUsageDescription`: PureMac → Souji
- `NSAppleEventsUsageDescription`: PureMac → Souji
- NSServices → NSMenuItem default: `"Uninstall with PureMac"` → `"Uninstall with Souji"`
- NSServices → NSPortName: `"PureMac"` → `"Souji"`

## 3. PureMac/PureMacApp.swift

- `struct PureMacApp: App` → `struct SoujiApp: App`
- Notification.Name extension → rename to `soujiMenuBarMonitorChanged`
- `"PureMac.MenuBarMonitorChanged"` → `"Souji.MenuBarMonitorChanged"`
- `@AppStorage("PureMac.OnboardingComplete")` → `"Souji.OnboardingComplete"`

## 4. PureMac/Models/AppLanguage.swift

**刪除語系：**
- case spanish = "es"
- case arabic = "ar"
- case portugueseBrazil = "pt-BR"
- case polish = "pl"
- case simplifiedChinese = "zh-Hans"

**新增語系：**
- case korean = "ko"

**更新 displayName：**
- .korean: return "Korean"

## 5. 語系檔

- 刪除：`ar.lproj/`, `es.lproj/`, `pl.lproj/`, `pt-BR.lproj/`, `zh-Hans.lproj/`
- 新增：`ko.lproj/Localizable.strings`（381 條字串，需韓文翻譯）
- 審閱 `zh-Hant.lproj/Localizable.strings` → 確認所有 "PureMac" → "Souji"
- 審閱 `ja.lproj/Localizable.strings` → 同

## 6. 其他 Swift 檔 — 搜尋 "PureMac" 字串

```bash
grep -rn '"PureMac"' --include='*.swift' .
grep -rn 'PureMac' --include='*.swift' . | grep -v '//' | grep -v 'import'
```

主要可能位置：
- CLI.swift（CLI mode command name）
- 部分 view 可能 hardcode "PureMac"
- UpdateService.swift（Sparkle feed URL）

## 7. 所有 .lproj 資料夾

確認每個 .lproj 內沒有殘留 PureMac.xcstrings（如果有就清掉）

## 8. Assets

- AppIcon → 換成 Souji 的圖示（暫用 SF Symbol 或簡單文字圖）
- 其他 asset images 檢查有無 PureMac logo

## 9. Homebrew

- `homebrew/` 資料夾更新 cask name 和 shasum

## 10. README.md

- 整份改寫為 Souji：品牌名、截圖路徑、安裝指令
- 保留 MIT License 聲明
- docs/ 下另外放 README.zh-Hant.md / .ja.md / .ko.md

## 11. docs/ 網站

- 整個 docs/ 將由 souji.wow.to 網站取代（見 website/ 資料夾）
- 之後不再用 GitHub Pages

## 12. Sparkle 更新

- UpdateService.swift 中的 feed URL 改成指向自己的 GitHub Releases
- 格式：`https://github.com/anthonytsai68/souji/releases/latest/download/appcast.xml`
