# logging 與除錯紀錄

## 資料流

```text
程式事件 → logger → 等級 → 終端機／檔案 → 問題定位
```

使用 `DEBUG` 追蹤資料流，`INFO` 記錄正常生命週期，`WARNING` 記錄可復原異常，`ERROR` 記錄操作失敗。
