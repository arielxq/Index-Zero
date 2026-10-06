# 04｜將感測資料存成 CSV 並繪製趨勢圖

## 本頁資料流

```text
UART 原始行 → 欄位解析 → 時間戳記 → CSV → Pandas DataFrame → Matplotlib 圖表
```

## 最小實作

```python
import csv
from datetime import datetime

with open("sensor.csv", "a", newline="", encoding="utf-8") as file:
    writer = csv.writer(file)
    writer.writerow([datetime.now().isoformat(), 25.0, 60.0])
```

資料欄位應固定為 `timestamp,temperature,humidity`，否則後續分析與圖表會失去一致性。

## 任務

- 先寫入一筆手動資料，確認檔案格式。
- 再把 UART 每筆資料寫入 CSV。
- 用 Pandas 讀取並檢查欄位型別。
- 產生溫度與濕度的時間趨勢圖。

## 品質檢查

```text
缺值 → 型別 → 合理範圍 → 時間順序 → 圖表
```

前往 [感測資料品質](../extensions/data-quality.md) 了解完整檢查。
