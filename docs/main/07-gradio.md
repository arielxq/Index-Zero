# 07｜Gradio：建立本機 AIoT 儀表板

## 本頁資料流

```text
ESP32 → UART → Python service → Gradio callback → 瀏覽器元件
使用者操作 → Gradio event → Python → UART command → ESP32
```

## 介面分層

| 層 | 工作 |
| --- | --- |
| 通訊 | 讀取 UART 與送出命令 |
| 資料 | 驗證、保存與整理感測值 |
| 介面 | 表格、文字、圖表與按鈕 |
| 事件 | 將使用者操作接到服務函式 |

## 任務

1. 先用固定 Python 函式更新一個文字元件。
2. 加入 CSV 最近資料表。
3. 加入溫度／濕度圖表。
4. 最後才把按鈕連到 ESP32 控制命令。

!!! note "原型邊界"
    Gradio 適合本機快速驗證。需要多人使用、權限、公開 API 或長時間背景工作時，應轉向 FastAPI 與明確的服務層。

[下一步：08｜整合專題](08-dashboard.md)
