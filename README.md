# AirDropUltra｜iPhone ↔ Mac 互傳捷徑

> 基於 AirDrop Plus 1.5.3，為搭配 Mac 端服務拆分的非官方「傳送」與「接收」捷徑。

本儲存庫目前只提供兩份 iPhone 捷徑，需搭配已安裝的 `AirDrop Plus Mac.app`。**Windows 繁中 v1.5.2 是另一份電腦端發行版**：本儲存庫未附該 EXE，也尚未驗證這兩份捷徑與它搭配使用的結果。

## 1. 準備 Mac

1. 開啟 `AirDrop Plus Mac.app`，從 macOS 選單列選擇「啟用傳輸」。
2. 在選單的「連線資訊與連接埠」查看 Mac 的主機名稱、區網 IP 與連接埠；用「複製連線金鑰」取得金鑰。這會取代目前 Mac 剪貼簿的內容。
3. 確認 iPhone 和 Mac 位於可互相連線的同一個區域網路。Mac 可用乙太網路，iPhone 可用 Wi-Fi。

## 2. 安裝並設定 iPhone 捷徑

用 iPhone 開啟對應連結，再點「取得捷徑」或「加入捷徑」。也可以下載已簽署的檔案，再用捷徑 App 開啟。

| 捷徑 | iCloud 安裝 | 檔案 |
| --- | --- | --- |
| 傳送 | [加入傳送](https://www.icloud.com/shortcuts/4524e36f678a420a935edb530cf7fa01) | [AirDropPlus-Send.shortcut](AirDropPlus-Send.shortcut) |
| 接收 | [加入接收](https://www.icloud.com/shortcuts/c717eb063dd24acda1a5e4dcc051fce3) | [AirDropPlus-Receive.shortcut](AirDropPlus-Receive.shortcut) |

打開捷徑 App，在兩份捷徑右上角點「⋯」進入編輯畫面，找到開頭的 `userconfig` 辭典，分別改成你的設定：

| 欄位 | 要填什麼 | 檔案內的範例 |
| --- | --- | --- |
| `host` | Mac 的區網 IP 或可解析的主機名稱，省略 `http://` | `192.0.2.10` |
| `port` | Mac 端 AirDrop Plus 設定的連接埠 | `12345` |
| `key` | Mac 端 AirDrop Plus 設定的驗證金鑰 | `CHANGE_ME` |

若有多個 Wi-Fi 環境，可在下方 `wifi-ip map` 辭典填入 Wi-Fi 名稱及該環境下的 Mac IP。不需要切換時，可移除 `YOUR_WIFI_NAME` 範例項目，讓捷徑使用 `host`。兩份捷徑各有自己的設定，請各自填寫。

## 3. 傳送與接收

- **iPhone → Mac，傳文字：**先在 iPhone 複製文字，再執行「AirDrop Plus 傳送」。
- **iPhone → Mac，傳檔案或照片：**在「檔案」或「照片」選取內容，點分享，選「AirDrop Plus 傳送」。
- **Mac → iPhone：**先在 Mac 複製文字、圖片或檔案，再在 iPhone 執行「AirDrop Plus 接收」。文字會複製到 iPhone 剪貼簿，請到其他 App 貼上；圖片與檔案會開啟分享選單，可從那裡選擇儲存或分享。

## 連不上時

確認 Mac 服務正在執行、iPhone 可存取區域網路，且兩份捷徑的主機、連接埠和金鑰都填對。若主機名稱無法解析，改填 Mac 的區網 IP；若使用訪客網路，確認網路沒有隔離裝置。捷徑沿用上游的 HTTP 連線，請在信任的區域網路使用。

## 改動與出處

- 改作自 [yeyt97/AirDropPlus 的 iOS 捷徑 1.5.3](https://github.com/yeyt97/AirDropPlus/commit/330c792208ce2c25572f0535f90530ed6946335a)；[原版安裝連結](https://www.icloud.com/shortcuts/71bfd351276c4d5bb12e538391bc7eb4)。
- 拆分傳送與接收流程，加入繁體中文設定說明、範例連線設定及可區分方向的圖示。接收文字仍會複製到剪貼簿，原版的接收通知已移除。
- 保留上游 [MIT 授權與原版權聲明](LICENSE)。這是非官方改作，與 Apple 無關。
