# json 與 csv

## 資料流

```text
Python dict／list → 序列化 → JSON／CSV → 傳輸或儲存 → 反序列化／讀取
```

JSON 適合結構化訊息與 UART，CSV 適合表格資料與分析；兩者不要混用責任。
