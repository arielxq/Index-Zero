# 通用延伸

通用延伸可獨立閱讀，補足 Python、資料處理、序列埠、Gradio、網路安全與後端架構。它們也會在主線與進階專題中被反覆使用。

## 通用資料流

```mermaid
flowchart LR
    P[Python 基礎] --> S[pyserial]
    S --> D[資料處理與圖表]
    D --> G[Gradio]
    G --> N[網路與安全]
    N --> B[網站後端]
```

## Python 程式設計

- [pathlib 與檔案路徑](python-pathlib.md)
- [json 與 csv](python-json-csv.md)
- [datetime 與 time](python-time.md)
- [函式、類別與責任分工](python-design.md)
- [例外處理與錯誤訊息](python-errors.md)
- [logging 與除錯紀錄](python-logging.md)
- [進階 logger 技巧與設計方法](python-logger-design.md)
- [測試概念與 pytest 實作](python-testing.md)

## pyserial 與序列埠

- [連線、讀寫與逾時](serial-basics.md)
- [埠與資料除錯](serial-debug.md)
- [連線生命週期與 COM 埠除錯](serial-lifecycle.md)

## 資料處理與圖表

- [Pandas 基礎操作](pandas-basics.md)
- [Pandas 清理、篩選與彙整](pandas-cleaning.md)
- [Matplotlib 圖表基本元件](matplotlib-basics.md)
- [Matplotlib 可讀性與輸出](matplotlib-output.md)

## Gradio

- [介面、元件與版面](gradio-components.md)
- [事件、資料流與元件更新](gradio-events.md)
- [狀態、驗證與使用體驗](gradio-state.md)

## 網路、安全與後端

- [IPv4、IPv6 與連線路徑](network-path.md)
- [公私鑰、數位簽章與中間人防範](security.md)
- [高併發、分散式系統與資料同步](backend.md)
