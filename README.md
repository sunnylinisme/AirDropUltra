# AirDropUltra｜Windows 繁體中文 v1.5.2

這是 AirDrop Plus 的 Windows x64 繁體中文版本，用於在區域網路上與相容的 iPhone 捷徑傳送檔案、圖片和剪貼簿內容。

## 下載

Windows 繁體中文 v1.5.2 已打包，**尚未上傳 GitHub Release**。上傳後，可到 [Releases](https://github.com/sunnylinisme/AirDropUltra/releases) 下載 `AirDropUltra-Windows-v1.5.2-zh-Hant-x64.zip`。Windows 發佈包不附 iPhone 捷徑。

## Windows 使用方式

1. 解壓縮整個 ZIP，保留 `AirDropPlus.exe` 旁的 `_internal` 資料夾。
2. 啟動前，用文字編輯器開啟 `AirDropPlus/_internal/config/config.ini`，將 `[config]` 裡的 `key` 換成自己的連線金鑰。
3. 執行 `AirDropPlus/AirDropPlus.exe`。若 Windows 防火牆詢問，僅對信任的私人網路允許連線。
4. 在自己的相容 iPhone 捷徑中填入 Windows 的區網 IPv4 位址、程式使用的連接埠，以及同一把金鑰。兩台裝置必須在可互相連線的區域網路。
5. 如果主機名稱無法解析，可在 Windows 終端機用 `ipconfig` 查詢 IPv4 位址，再直接填入 IP。

## 原始專案與授權

本版本改作自 [yeyt97/AirDropPlus](https://github.com/yeyt97/AirDropPlus)，保留原始版權聲明及 [MIT 授權](LICENSE)。此為非官方改作。
