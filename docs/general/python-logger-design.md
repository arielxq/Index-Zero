# 進階 logger 技巧與設計方法

## 資料流

```text
模組事件 → logger hierarchy → handler → formatter → 不同輸出目的地
```

模組使用自己的 logger 名稱，入口程式統一設定 handler，避免函式庫重複新增 handler 造成重複輸出。
