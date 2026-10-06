# pyserial 連線、讀寫與逾時

## 資料流

```text
COM／TTY → Serial 設定 → read／write → bytes → decode／encode
```

連線至少要明確設定埠名、baud rate、timeout，並在程式結束時關閉資源。
