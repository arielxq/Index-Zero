# 主線延伸

主線延伸直接對應主線中的通訊、資料、顯示與介面問題。它們不是額外的必修順序，而是完成某一章後用來補強理解的工具箱。

## 延伸資料流

```text
主線實作 → 觀察問題 → 對應導讀 → 修正模型／程式 → 回到主線驗證
```

## 序列通訊與整合

- [UART JSON、緩衝區與請求／回應](uart-json.md)
- [UART 程式導讀](uart-guide.md)
- [環境看板整合程式導讀](dashboard-guide.md)
- [整合專題故障分流](troubleshooting.md)

## 資料、顯示與介面

- [CSV 與圖表程式導讀](csv-guide.md)
- [感測資料品質](data-quality.md)
- [LCD 顯示程式導讀](lcd-guide.md)
- [74HC595 與點陣掃描導讀](matrix-guide.md)
- [Gradio 事件、狀態與原型邊界](gradio-boundaries.md)

## 閱讀方式

```text
UART 異常 → UART JSON／故障分流
圖表不可信 → CSV 導讀／資料品質
LCD 異常 → LCD 顯示導讀
點陣方向錯誤 → 點陣掃描導讀
Gradio 事件混亂 → Gradio 邊界
```
