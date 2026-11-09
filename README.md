# Ultra｜Windows 繁體中文 v1.5.2

[下載 Ultra Windows x64 ZIP](https://github.com/sunnylinisme/AirDropUltra/releases/download/v1.5.2-windows-zh-hant/Ultra-Windows-v1.5.2-zh-Hant-x64.zip) · [下載繁中教學影片（MP4）](https://github.com/sunnylinisme/AirDropUltra/releases/download/v1.5.2-windows-zh-hant/Ultra-Windows-v1.5.2-Tutorial-zh-Hant.mp4) · [發佈頁](https://github.com/sunnylinisme/AirDropUltra/releases/tag/v1.5.2-windows-zh-hant)

Windows x64 版，可透過區域網路與 iPhone 互傳檔案、圖片和剪貼簿文字。ZIP 內含 Windows 程式、相依檔、繁中說明及兩張捷徑安裝 QR Code；捷徑從下方連結個別安裝。

## 1. 設定 Windows

1. 將 `Ultra-Windows-v1.5.2-zh-Hant-x64.zip` 整包解壓縮。保留 `Ultra.exe` 同一層的 `_internal` 資料夾。
2. 首次啟動前，開啟 `Ultra/_internal/config/config.ini`。在 `[config]` 將 `key` 的 `CHANGE_ME_BEFORE_USE` 換成自己的連線金鑰，並記下 `port`（預設 `53843`）。
3. 執行 `Ultra/Ultra.exe`，確認系統匣有程式圖示。若防火牆詢問，只在信任的私人網路允許連線。
4. 在 Windows 終端機執行 `ipconfig`，記下目前使用的 Wi-Fi 或乙太網路介面的 **IPv4 位址**。讓 iPhone 與 Windows 接上可互相連線的區域網路。

如要設定開機啟動，以系統管理員身分執行 `Ultra/Ultra-Enable-Autostart.bat`。若曾設定原版的開機啟動，可在 Windows 啟動資料夾移除舊的 `AirDropPlus.lnk`，避免兩份程式同時啟動。

## 2. 安裝與設定 iPhone 捷徑

| 要做的事 | 安裝方式 |
| --- | --- |
| iPhone → Windows | [安裝傳送捷徑](https://www.icloud.com/shortcuts/4524e36f678a420a935edb530cf7fa01)，或掃描 ZIP 裡的 `Ultra-Send-QR.png` |
| Windows → iPhone | [安裝接收捷徑](https://www.icloud.com/shortcuts/c717eb063dd24acda1a5e4dcc051fce3)，或掃描 ZIP 裡的 `Ultra-Receive-QR.png` |

在 iPhone 開啟連結後點「取得捷徑」或「加入捷徑」。接著在捷徑 App 打開兩份捷徑的編輯畫面，分別修改開頭的 `userconfig`：

- `host`：Windows 的 IPv4 位址，例如 `192.168.1.20`，不要加 `http://`。
- `port`：與 Windows 設定檔相同的連接埠。
- `key`：與 Windows 設定檔相同的金鑰。

如不使用依 Wi-Fi 切換位址，可移除 `wifi-ip map` 中的 `YOUR_WIFI_NAME` 範例項目，讓捷徑直接用 `host`。兩份捷徑要分別設定。加入後可將捷徑顯示名稱改成「Ultra 傳送」和「Ultra 接收」。

## 3. 試傳一次

1. **iPhone 傳文字到 Windows：**在 iPhone 複製一小段文字，執行傳送捷徑，再到 Windows 的記事本貼上。
2. **iPhone 傳照片或檔案到 Windows：**在「照片」或「檔案」選取項目，從分享選單執行傳送捷徑。可到 Windows 的下載資料夾或程式設定的儲存位置查看。
3. **Windows 傳回 iPhone：**在 Windows 先複製文字、圖片或檔案，再在 iPhone 執行接收捷徑。文字可到其他 App 貼上；圖片與檔案會開啟分享選單，可選擇儲存。

## 連不上時

- **逾時：**確認 Windows 程式正在執行、IPv4 位址沒有填錯、兩端位於可互通的區域網路，並檢查 Windows 防火牆與 iPhone 的區域網路權限。訪客 Wi-Fi 可能會隔離裝置。
- **金鑰錯誤：**重新確認兩份捷徑的 `key` 都與 Windows 一致。
- **主機名稱無法解析：**直接填 Windows 的 IPv4 位址；ZIP 未附 Bonjour 安裝程式。

已核對 ZIP 內容及兩張 QR Code 的目的連結。依發佈者回報，Ultra 改名版已在 Windows 實機測試，運作正常。

## 原始專案與授權

改作自 [yeyt97/AirDropPlus](https://github.com/yeyt97/AirDropPlus)。原始版權聲明與 [MIT 授權](LICENSE) 隨包保留。此為非官方改作。
