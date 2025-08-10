# 沖繩五日四夜（本地圖片版）部署說明

此套檔案已將外部圖片轉為本地 `images/` 路徑，避免 GitHub Pages 出現「死 link」。

## 檔案列表
- `Index2_local.html`：可直接上載並作為頁面檔案
- `images/`：已包含對應檔名之 **臨時佔位圖片**（灰底）
- `download_images.sh`：以 curl 下載 Wikimedia 正版圖片並覆蓋佔位圖
- `download_images.py`：以 Python/requests 下載同樣的圖片

## 使用方式（擇一）：
### 方案 1：用 bash + curl
```bash
cd 本資料夾
chmod +x download_images.sh
./download_images.sh
```

### 方案 2：用 Python
```bash
pip install requests
python3 download_images.py
```

以上腳本會把 `images/` 內的佔位圖覆蓋為真正圖片。完成後，把整個資料夾（包含 `Index2_local.html` 與 `images/`）上載至 GitHub Pages 專案。

## 注意
- 如欲保留原本的 Lazy Loading，可以在 `<img>` 上自行加回 `loading="lazy"`。
- 現已移除 `decoding="async"` 與 `loading="lazy"`，以提升 Safari 直接載入的穩定性。
