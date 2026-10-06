# 學習筆記

Python、ESP32、資料、介面與 App 整合的可擴充學習網站。

- Repository: <https://github.com/arielxq/Index-Zero>
- 網站: <https://arielxq.github.io/Index-Zero/>
- 編輯分支: `main`
- 發布分支: `gh-pages`

網站使用 MkDocs Material 建置。所有教材先寫在 `docs/`，再由 MkDocs 轉成 `site/` 靜態網站。

```text
main 的 Markdown
    ↓ mkdocs build
site/ 靜態 HTML、CSS、JavaScript
    ↓ python -m http.server 或 GitHub Pages
瀏覽器網站
```

## 1. 專案目錄結構

```text
Index-Zero/
├── docs/
│   ├── index.md                  # 首頁
│   ├── main/                     # 主線課程 01～08
│   ├── extensions/               # 主線延伸
│   ├── general/                  # 通用延伸
│   ├── advanced/                 # 進階實務
│   ├── optional/                 # 其他選做
│   ├── supplemental/             # 資訊補充
│   ├── stylesheets/extra.css     # 自訂樣式
│   └── javascripts/extra.js      # 自訂互動
├── mkdocs.yml                    # 導覽與網站設定
├── requirements.txt              # 建置依賴
├── .github/workflows/deploy.yml  # GitHub Pages 部署
├── .gitignore                    # 忽略本機產物
└── README.md                     # 本操作說明
```

## 2. 資料夾與網站內容對照

### 頂端同級分類

| 網站按鈕 | 導覽入口 | 本機路徑 | 網站顯示內容 |
| --- | --- | --- | --- |
| 首頁 | `docs/index.md` | `docs/` | 總目錄、總資料流、時間軸、硬體基準 |
| 主線課程 | `docs/main/index.md` | `docs/main/` | 環境準備到環境看板 |
| 主線延伸 | `docs/extensions/index.md` | `docs/extensions/` | UART、資料、LCD、點陣、Gradio 補充 |
| 通用延伸 | `docs/general/index.md` | `docs/general/` | Python、pyserial、資料、Gradio、網路、後端 |
| 進階實務 | `docs/advanced/index.md` | `docs/advanced/` | MQTT、RC522、FastAPI、ngrok、App、BLE |
| 其他選做 | `docs/optional/index.md` | `docs/optional/` | MAX7219 等額外硬體 |
| 資訊補充 | `docs/supplemental/index.md` | `docs/supplemental/` | GUI、App、耦合性與新增模板 |

### 首頁：`docs/index.md`

| 區塊 | 修改內容 |
| --- | --- |
| 網站簡介 | 首頁開場文字 |
| 總資料流 | Mermaid 系統資料流圖 |
| 學習時間軸 | 課程建議順序 |
| 硬體基準 | ESP32、DHT11、LCD、點陣等標準硬體 |
| 章節入口 | 首頁目錄與分類連結 |

### 主線課程：`docs/main/`

| 檔案 | 網站顯示內容 | 主要產出 |
| --- | --- | --- |
| `index.md` | 主線課程總覽 | 主線資料流與學習順序 |
| `01-uv.md` | 用 uv 建立 Python 虛擬環境 | 可重現的 Python 專案 |
| `02-data-flow.md` | 認識 AIoT 資料流 | 系統分層概念 |
| `03-uart.md` | UART：Python 與 ESP32 雙向通訊 | 傳遞資料與命令 |
| `04-csv-chart.md` | CSV 與趨勢圖 | 保存與分析資料 |
| `05-i2c-lcd.md` | LCD1602A 與 DHT11 | I2C 文字顯示 |
| `06-matrix.md` | 74HC595 與裸 8×8 點陣 | 行列掃描與圖樣輸出 |
| `07-gradio.md` | Gradio AIoT 儀表板 | 本機瀏覽器介面 |
| `08-dashboard.md` | 環境看板整合專題 | 完整 AIoT 資料流 |

### 主線延伸：`docs/extensions/`

| 分類 | 檔案 | 網站顯示內容 |
| --- | --- | --- |
| 序列通訊與整合 | `uart-json.md` | UART JSON、緩衝區、請求／回應 |
| 序列通訊與整合 | `uart-guide.md` | UART 程式導讀 |
| 序列通訊與整合 | `dashboard-guide.md` | 環境看板程式導讀 |
| 序列通訊與整合 | `troubleshooting.md` | 整合專題故障分流 |
| 資料、顯示與介面 | `csv-guide.md` | CSV 與圖表程式導讀 |
| 資料、顯示與介面 | `data-quality.md` | 感測資料品質 |
| 資料、顯示與介面 | `lcd-guide.md` | LCD 顯示程式導讀 |
| 資料、顯示與介面 | `matrix-guide.md` | 74HC595 點陣掃描導讀 |
| 資料、顯示與介面 | `gradio-boundaries.md` | Gradio 事件、狀態與原型邊界 |

### 通用延伸：`docs/general/`

實際檔案放在同一個資料夾，但 `mkdocs.yml` 會把它們顯示成以下層級：

```text
通用延伸
├── Python 程式設計
│   ├── pathlib 與檔案路徑
│   ├── json 與 csv
│   ├── datetime 與 time
│   ├── 函式、類別與責任分工
│   ├── 例外處理與錯誤訊息
│   ├── logging 與除錯紀錄
│   ├── 進階 logger 技巧與設計方法
│   └── 測試概念與 pytest 實作
├── pyserial 與序列埠
│   ├── 連線、讀寫與逾時
│   ├── 埠與資料除錯
│   └── 連線生命週期與 COM 埠除錯
├── 資料處理與圖表
│   ├── Pandas 基礎操作
│   ├── Pandas 清理、篩選與彙整
│   ├── Matplotlib 圖表基本元件
│   └── Matplotlib 可讀性與輸出
├── Gradio
│   ├── 介面、元件與版面
│   ├── 事件、資料流與元件更新
│   └── 狀態、驗證與使用體驗
├── 網路與安全
│   ├── IPv4、IPv6 與連線路徑
│   └── 公私鑰、數位簽章與中間人防範
└── 網站後端概念
    └── 高併發、分散式系統與資料同步
```

| 網站分類 | 檔案命名範例 | 修改用途 |
| --- | --- | --- |
| Python 程式設計 | `python-pathlib.md` | Python 語法、檔案、錯誤、測試 |
| pyserial 與序列埠 | `serial-basics.md` | COM／TTY、讀寫、逾時與除錯 |
| 資料處理與圖表 | `pandas-basics.md` | DataFrame、清理、彙整、圖表 |
| Gradio | `gradio-components.md` | 元件、事件、狀態與驗證 |
| 網路與安全 | `network-path.md` | IP、連線路徑、簽章與安全 |
| 網站後端概念 | `backend.md` | 併發、分散式系統與同步 |

### 進階、其他選做與資訊補充

| 路徑 | 網站顯示內容 |
| --- | --- |
| `docs/advanced/` | MQTT、PubSubClient、HiveMQ、SPI、RC522、FastAPI、ngrok、Thunkable、Blynk、BLE |
| `docs/optional/` | MAX7219 點陣模組 |
| `docs/supplemental/` | GUI／App 解決方案、系統耦合性、新增筆記模板 |

## 3. 控制網站顯示的檔案

| 檔案 | 控制內容 | 何時修改 |
| --- | --- | --- |
| `mkdocs.yml` | 網站名稱、頂端 tabs、側欄順序與頁面階層 | 新增頁面或調整導覽 |
| `docs/stylesheets/extra.css` | 顏色、縮排、分類線、目前頁面樣式 | 調整網站外觀 |
| `docs/javascripts/extra.js` | 頁內錨點等互動 | 新增前端行為 |
| `requirements.txt` | MkDocs Material 依賴 | 更新建置套件 |
| `.github/workflows/deploy.yml` | 自動建置與 GitHub Pages 發布 | 修改部署流程 |

`mkdocs.yml` 中左邊是網站顯示名稱，右邊是相對於 `docs/` 的檔案路徑：

```yaml
- 通用延伸:
    - 通用延伸總覽: general/index.md
    - Python 程式設計:
        - pathlib 與檔案路徑: general/python-pathlib.md
        - json 與 csv: general/python-json-csv.md
```

## 4. 新增筆記的完整流程

以下示範新增「Python 裝飾器」到「通用延伸 → Python 程式設計」。

### 步驟 1：建立 Markdown

新增檔案：

```text
docs/general/python-decorators.md
```

```markdown
# Python 裝飾器

## 學習目標

理解裝飾器如何包裝函式。

## 先備知識

- 函式與參數
- [函式、類別與責任分工](python-design.md)

## 本頁資料流

```text
原始函式 → 裝飾器 → 包裝函式 → 執行結果
```

## 核心概念

在這裡撰寫筆記內容。

## 實作任務

### 任務 1：建立簡單裝飾器

#### 任務資料流

```text
函式 → decorator → 執行前後紀錄 → 函式結果
```

## 常見錯誤

記錄實際遇到的問題與排除方式。

## 關聯頁面

- [logging 與除錯紀錄](python-logging.md)

## 下一步

連結到下一篇相關筆記。
```

### 步驟 2：加入 `mkdocs.yml`

在 `Python 程式設計` 下加入：

```yaml
- 通用延伸:
    - 通用延伸總覽: general/index.md
    - Python 程式設計:
        - pathlib 與檔案路徑: general/python-pathlib.md
        - json 與 csv: general/python-json-csv.md
        - Python 裝飾器: general/python-decorators.md
```

順序會影響網站側欄順序。只建立 Markdown 而不修改 `mkdocs.yml`，新頁面不會出現在預期的導覽階層。

### 步驟 3：同步分類入口頁

編輯 `docs/general/index.md`，加入：

```markdown
- [Python 裝飾器](python-decorators.md)
```

### 步驟 4：嚴格建置

```bash
.venv/bin/mkdocs build --strict
```

## 5. 本地檢視：`python -m http.server`

可以使用 `python -m http.server`，但它只提供已建置完成的 `site/`，不會直接讀取 Markdown，也不會自動重新建置。

### 首次準備

在 repository 根目錄：

```bash
python3 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt
```

### 修改後建置

```bash
.venv/bin/mkdocs build --strict
```

### 啟動靜態服務

建置成功後：

```bash
cd site
python3 -m http.server 8000
```

開啟 <http://127.0.0.1:8000/>，停止服務按 `Ctrl+C`。

| 功能 | `python -m http.server` | 說明 |
| --- | --- | --- |
| 顯示已建置網站 | 可以 | 提供 `site/` 的 HTML、CSS、JavaScript |
| 讀取 Markdown | 不可以 | 需先執行 `mkdocs build` |
| 自動轉換 Markdown | 不可以 | 修改後要重新建置 |
| 搜尋與錨點 | 可以 | 已在建置時產生 |
| Mermaid 圖表 | 可以 | 需先完成 MkDocs 建置 |
| 修改後即時更新 | 不可以 | 重建後重新整理瀏覽器 |

完整流程：

```text
修改 docs/*.md 或 mkdocs.yml
    ↓
mkdocs build --strict
    ↓
cd site
    ↓
python3 -m http.server 8000
    ↓
http://127.0.0.1:8000/
```

## 6. 提交到 GitHub 並發布

### 提交前檢查

```bash
.venv/bin/mkdocs build --strict
git diff --check
git status
```

確認建置成功、頁面可開啟、新檔案已加入 `mkdocs.yml`，且沒有誤提交 `site/` 或 `.venv/`。

### Commit 與 Push

```bash
git add docs mkdocs.yml README.md
git commit -m "Add and improve learning notes"
git push origin main
```

如果也修改 CSS、JavaScript 或部署設定：

```bash
git add docs mkdocs.yml README.md requirements.txt .github
git commit -m "Update documentation website"
git push origin main
```

### 發布資料流

```text
push main
    ↓
GitHub Actions: Deploy documentation
    ↓
mkdocs gh-deploy --force
    ↓
更新 gh-pages
    ↓
GitHub Pages 顯示新版本
```

到 Repository 的 `Actions` 查看 `Deploy documentation` 是否為 `Success`。不要直接修改 `gh-pages`，它是由建置結果產生的發布分支。

## 7. 分支與責任

| 分支／位置 | 用途 | 是否直接編輯 |
| --- | --- | --- |
| `main` | Markdown、網站設定、部署工作流 | 是 |
| `gh-pages` | MkDocs 產生的靜態網站 | 否 |
| `site/` | 本機建置產物 | 否，已忽略 |
| `.venv/` | 本機 Python 虛擬環境 | 否，已忽略 |

核心原則：

```text
編輯 main → 本機 build 檢查 → push main → Actions 產生 gh-pages
```
