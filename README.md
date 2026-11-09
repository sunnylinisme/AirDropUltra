# AirDropUltra｜Windows 繁體中文 v1.5.2

Windows x64 版，可透過區域網路與 iPhone 互傳檔案、圖片和剪貼簿文字。ZIP 內含 Windows 程式、相依檔、繁中說明及兩張捷徑安裝 QR Code；捷徑從下方連結個別安裝。

## 1. 設定 Windows

1. 從 [Releases](https://github.com/sunnylinisme/AirDropUltra/releases) 取得 `AirDropUltra-Windows-v1.5.2-zh-Hant-x64.zip` 後，將整包解壓縮。保留 `AirDropPlus.exe` 同一層的 `_internal` 資料夾。
2. 首次啟動前，開啟 `AirDropPlus/_internal/config/config.ini`。在 `[config]` 將 `key` 的 `CHANGE_ME_BEFORE_USE` 換成自己的連線金鑰，並記下 `port`（預設 `53843`）。
3. 執行 `AirDropPlus/AirDropPlus.exe`，確認系統匣有程式圖示。若防火牆詢問，只在信任的私人網路允許連線。
4. 在 Windows 終端機執行 `ipconfig`，記下目前使用的 Wi-Fi 或乙太網路介面的 **IPv4 位址**。讓 iPhone 與 Windows 接上可互相連線的區域網路。

## 2. 安裝與設定 iPhone 捷徑

| 要做的事 | 安裝方式 |
| --- | --- |
| iPhone → Windows | [安裝傳送捷徑](https://www.icloud.com/shortcuts/4524e36f678a420a935edb530cf7fa01)，或掃描 ZIP 裡的 `QR-Send.png` |
| Windows → iPhone | [安裝接收捷徑](https://www.icloud.com/shortcuts/c717eb063dd24acda1a5e4dcc051fce3)，或掃描 ZIP 裡的 `QR-Receive.png` |

在 iPhone 開啟連結後點「取得捷徑」或「加入捷徑」。接著在捷徑 App 打開兩份捷徑的編輯畫面，分別修改開頭的 `userconfig`：

- `host`：Windows 的 IPv4 位址，例如 `192.168.1.20`，不要加 `http://`。
- `port`：與 Windows 設定檔相同的連接埠。
- `key`：與 Windows 設定檔相同的金鑰。

如不使用依 Wi-Fi 切換位址，可移除 `wifi-ip map` 中的 `YOUR_WIFI_NAME` 範例項目，讓捷徑直接用 `host`。兩份捷徑要分別設定。

## 3. 試傳一次

1. **iPhone 傳文字到 Windows：**在 iPhone 複製一小段文字，執行「AirDrop Plus 傳送」，再到 Windows 的記事本貼上。
2. **iPhone 傳照片或檔案到 Windows：**在「照片」或「檔案」選取項目，從分享選單執行「AirDrop Plus 傳送」。可到 Windows 的下載資料夾或程式設定的儲存位置查看。
3. **Windows 傳回 iPhone：**在 Windows 先複製文字、圖片或檔案，再在 iPhone 執行「AirDrop Plus 接收」。文字可到其他 App 貼上；圖片與檔案會開啟分享選單，可選擇儲存。

## 連不上時

- **逾時：**確認 Windows 程式正在執行、IPv4 位址沒有填錯、兩端位於可互通的區域網路，並檢查 Windows 防火牆與 iPhone 的區域網路權限。訪客 Wi-Fi 可能會隔離裝置。
- **金鑰錯誤：**重新確認兩份捷徑的 `key` 都與 Windows 一致。
- **主機名稱無法解析：**直接填 Windows 的 IPv4 位址；ZIP 未附 Bonjour 安裝程式。

已核對 ZIP 內容及兩張 QR Code 的目的連結。依發佈者回報，Windows 與 iPhone 實機互傳測試正常。

## 原始專案與授權

改作自 [yeyt97/AirDropPlus](https://github.com/yeyt97/AirDropPlus)。原始版權聲明與 [MIT 授權](LICENSE) 隨包保留。此為非官方改作。
