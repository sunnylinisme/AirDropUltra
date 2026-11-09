# AirDropUltra｜iPhone ↔ Windows 互傳捷徑

> 基於 AirDrop Plus 1.5.3 的非官方傳送／接收捷徑改作。

這是 AirDrop Plus 1.5.3 的 iPhone 捷徑改作。將原本同一份捷徑的「傳送／接收」選單拆成兩份，讓你可以直接執行要用的動作。本專案提供捷徑；Windows 端服務請由[上游專案](https://github.com/yeyt97/AirDropPlus#installation)取得。

## 1. 準備 Windows

1. 依照[原專案安裝說明](https://github.com/yeyt97/AirDropPlus#installation)啟動 AirDrop Plus。
2. 在 Windows 系統匣開啟 AirDrop Plus 設定，記下 Windows 的區網 IP、服務連接埠與驗證金鑰。若需要查看 IP，可在 Windows 終端機執行 `ipconfig`，查找目前使用的網路介面的 IPv4 位址。
3. 讓 iPhone 和 Windows 連到可互相通訊的同一個區域網路。若 Windows 防火牆詢問，請只對信任的私人網路允許存取。

## 2. 安裝並設定 iPhone 捷徑

用 iPhone 開啟對應連結，再點「取得捷徑」或「加入捷徑」。也可以下載已簽署的檔案，再用捷徑 App 開啟。

| 捷徑 | iCloud 安裝 | 檔案 |
| --- | --- | --- |
| 傳送 | [加入傳送](https://www.icloud.com/shortcuts/4524e36f678a420a935edb530cf7fa01) | [AirDropPlus-Send.shortcut](AirDropPlus-Send.shortcut) |
| 接收 | [加入接收](https://www.icloud.com/shortcuts/c717eb063dd24acda1a5e4dcc051fce3) | [AirDropPlus-Receive.shortcut](AirDropPlus-Receive.shortcut) |

打開捷徑 App，在兩份捷徑右上角點「⋯」進入編輯畫面，找到開頭的 `userconfig` 辭典，分別改成你的設定：

| 欄位 | 要填什麼 | 檔案內的範例 |
| --- | --- | --- |
| `host` | Windows 的區網 IP 或可解析的主機名稱，省略 `http://` | `192.0.2.10` |
| `port` | Windows 端 AirDrop Plus 設定的連接埠 | `12345` |
| `key` | Windows 端 AirDrop Plus 設定的驗證金鑰 | `CHANGE_ME` |

若有多個 Wi-Fi 環境，可在下方 `wifi-ip map` 辭典填入 Wi-Fi 名稱及該環境下的 Windows IP。不需要切換時，可移除 `YOUR_WIFI_NAME` 範例項目，讓捷徑使用 `host`。兩份捷徑各有自己的設定，請各自填寫。

## 3. 傳送與接收

- **iPhone → Windows，傳文字：**先在 iPhone 複製文字，再執行「AirDrop Plus 傳送」。
- **iPhone → Windows，傳檔案或照片：**在「檔案」或「照片」選取內容，點分享，選「AirDrop Plus 傳送」。
- **Windows → iPhone：**先在 Windows 複製文字、圖片或檔案，再在 iPhone 執行「AirDrop Plus 接收」。文字會複製到 iPhone 剪貼簿，請到其他 App 貼上；圖片與檔案會開啟分享選單，可從那裡選擇儲存或分享。

## 連不上時

確認 Windows 服務正在執行、iPhone 可存取區域網路，且兩份捷徑的主機、連接埠和金鑰都填對。若主機名稱無法解析，改填 Windows 的區網 IP；若使用訪客網路，確認網路沒有隔離裝置。捷徑沿用上游的 HTTP 連線，請在信任的區域網路使用。

## 改動與出處

- 改作自 [yeyt97/AirDropPlus 的 iOS 捷徑 1.5.3](https://github.com/yeyt97/AirDropPlus/commit/330c792208ce2c25572f0535f90530ed6946335a)；[原版安裝連結](https://www.icloud.com/shortcuts/71bfd351276c4d5bb12e538391bc7eb4)。
- 拆分傳送與接收流程，加入繁體中文設定說明、範例連線設定及可區分方向的圖示。接收文字仍會複製到剪貼簿，原版的接收通知已移除。
- 保留上游 [MIT 授權與原版權聲明](LICENSE)。這是非官方改作，與 Apple 無關。
