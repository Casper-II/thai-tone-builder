# Thai Tone Builder v0.4.3 — Mobile PWA / GitHub Pages

## 本版更新
- 以使用者提供的 `11_教材規則矩陣` 更新規則資料與 App 內嵌矩陣。
- 同步 `09_測試案例` 作為測試資料。
- 保留原始 Google Sheets 工作簿；**沒有修改 `02_母音表`，也沒有加入 `12_母音拼寫形式` 工作表**。
- 保留奶油色＋森林綠介面、按鍵式選擇、五張聲調運圖、RTGS／IPA 顯示欄位。
- PWA 包含 manifest、service worker、iOS 主畫面圖示、Android 安裝圖示、離線快取與手機響應式版面。
- Service Worker cache key 更新為 `thai-tone-builder-v043-mobile`。

## 規則使用原則
- 聲調判定以 `11_教材規則矩陣` 的原始文字比對；「不存在」或沒有調值的組合不會自行推測。
- 「長母音或 -ำ、-ไ、-ใ、เ-า」沿用既定定義：一般長母音，加上四種指定母音。
- `อ นำ` 僅限教材列出的固定詞，不泛化至所有組合。
- 前引字、複合聲母及例外若缺少已確認資料，仍會顯示待補資料，不自行補規則。
- RTGS／IPA 目前仍是欄位與預留顯示；完整轉寫引擎尚未完成。

## 部署到 GitHub Pages
1. 解壓縮 ZIP。
2. 將解壓縮後的所有檔案與資料夾上傳到 GitHub repository 根目錄（不要再包一層資料夾）。
3. Repository → Settings → Pages → Build and deployment → Source 選 `GitHub Actions`。
4. 確認 `.github/workflows/pages.yml` 存在於 repository 根目錄下的 `.github/workflows/`。
5. 到 Actions 等待 Pages workflow 顯示成功。
6. 網址格式：`https://<GitHub使用者名稱>.github.io/<repository名稱>/`。

## 手機安裝
### iPhone / iPad
1. 使用 Safari 開啟已部署的 HTTPS 網址。
2. 點「分享」→「加入主畫面」。
3. 確認名稱為 Tone Builder，點「新增」。
4. 從主畫面圖示開啟；首次載入完成後可測試離線使用。

### Android
1. 使用 Chrome 開啟已部署的 HTTPS 網址。
2. 點選瀏覽器的「安裝應用程式」或「加入主畫面」。
3. 安裝後從桌面圖示開啟。

## 離線測試
- 第一次需在網路連線狀態開啟，讓 Service Worker 完成快取。
- 關閉網路後重新開啟 PWA，確認頁面與五張運圖可載入。
- 更新版本後若手機仍顯示舊版，先連網重新開啟；必要時關閉舊分頁再開啟。

## 注意
此 ZIP 已具備手機版 PWA 所需檔案，但尚未自動發布到 GitHub Pages。真正的安裝網址必須在 repository 發布成功後才能確認。


## v0.4.3 修正版（TB-0001）
- 已將「中子音＋一般短母音＋無尾音＋無聲調符號」修正為「第二聲｜低調 [21]」。
- 已同步更新 `11_教材規則矩陣`、`tone_rules_matrix.json` 與 `index.html` 內嵌矩陣。
- `TB-0001` 測試案例保留為「第二聲｜低調 [21]」。
- 原始 `02_母音表` 保持不變；部署包僅保留含完整母音資料的 `Thai_Tone_Builder_Google_Sheets_Rule_Source.xlsx`。
