# pyserial 埠與資料除錯

## 資料流

```text
原始 bytes → repr → decode → 去除換行 → 格式檢查 → 可用資料
```

除錯時先印出 `repr(raw)`，可看見不可見換行、空白與編碼錯誤。
