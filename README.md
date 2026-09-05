# 個人專屬教練 · 站 1（上傳與方向）

2026 Futuremode 黑客松的原型。三站流程的第一站：**讀你已經留下的痕跡 → 挑一個人生形狀 → 拿資料回頭跟那個形狀對一次**，
最後產出的不是願景，是一個這一季就能測完的「方向假設 v0」。

畫面用 **mist** 設計系統，來源與元件都在 `design/`。

## 線上版

| 頁面 | 網址 |
|---|---|
| 站 1 · 上傳與方向 | （Pages 部署後補上） |
| mist 元件參考站（每個元件的每個狀態） | （Pages 部署後補上） |

站 2（目標樹草案）與站 3（季度對帳）目前仍是 Claude Artifact，頁面頂端的導覽直接連過去。

## 這個 repo 有什麼

```
index.html      站 1 的單檔版。產生出來的，不要手改
design/         mist 設計系統的專案端副本 + 頁面來源
  ui/           token、元件、規格、元件參考站 —— 唯讀，會被設計系統的更新整個覆蓋
  pages/        頁面來源。只放 class，不寫樣式
  check.sh      交出去前跑這支：抓寫死的顏色尺寸、inline style、頁面層樣式、不存在的 token
```

`index.html` 與 `design/pages/01-intake.html` 是同一份內容的兩種形態，**來源永遠是後者**。
改法與規則見 [design/README.md](design/README.md)。

## 本機預覽

```bash
python3 design/serve.py . 8747
```

然後開 http://localhost:8747/ 看站 1，開 http://localhost:8747/design/ui/reference.html 看元件參考站。

## 已知限制

- 前端假資料，沒有後端、沒有資料庫、沒有 API 串接。上傳區是靜態畫面，不會真的解析 PDF 或行事曆
- mist 目前沒有深色模式，這一頁只有亮色
- 資料為示範用途，那位「5 年 3 份工作、零 side project、近 3 個月 3 次獵頭面談」的使用者是虛構的
