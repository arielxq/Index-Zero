# 選做實作：LightBlue 與 ESP32 交換固定資料

## 資料流

```text
LightBlue write → ESP32 Characteristic → 格式解析 → 狀態更新 → notify → LightBlue
```

先使用固定短字串驗證 Service、Characteristic 與方向，再增加設定格式與錯誤回覆。
