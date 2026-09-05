# 個人專屬教練 · 三站原型

2026 Futuremode 黑客松的原型。外層是教練全流程，內層是**稽核**：

**站 1 上傳與方向** — 讀你已經留下的痕跡、挑一個人生形狀、拿資料回頭跟那個形狀對一次，產出這一季的「方向假設 v0」。
**站 2 目標樹草案** — 教練把願景拆成五層，你只負責確認、刪減，或回答三個它答不出來的問題。
**站 3 季度對帳** — 把一季的痕跡歸戶到各分支，算出進展、空白與歸不進去的投入，據此開下一季處方。

畫面用 **mist** 設計系統，來源與元件都在 `design/`。

## 線上版

| 頁面 | 網址 |
|---|---|
| 站 1 · 上傳與方向 | https://wu0h9625-boop.github.io/guru-intake-prototype/ |
| 站 2 · 目標樹草案 | https://wu0h9625-boop.github.io/guru-intake-prototype/02-plan.html |
| 站 3 · 季度對帳 | https://wu0h9625-boop.github.io/guru-intake-prototype/03-ledger.html |
| mist 元件參考站（每個元件的每個狀態） | https://wu0h9625-boop.github.io/guru-intake-prototype/design/ui/reference.html |

三站互相有導覽可以直接跳。三頁共用同一組假資料與同一條時間軸：計畫 2026-06-28 起草 → Q3 對帳 09-04。

## 這個 repo 有什麼

```
index.html        站 1 的單檔版（與 01-intake.html 同內容，Pages 的首頁）
01-intake.html    站 1 · 上傳與方向
02-plan.html      站 2 · 目標樹草案
03-ledger.html    站 3 · 季度對帳
design/           mist 設計系統的專案端副本 + 頁面來源
  ui/             token、元件、規格、元件參考站 —— 唯讀，會被設計系統的更新整個覆蓋
  pages/          頁面來源。只放 class，不寫樣式
  check.sh        交出去前跑這支：抓寫死的顏色尺寸、inline style、頁面層樣式、不存在的 token
```

根目錄那四個 HTML 都是**產生出來的**，不要手改——來源永遠是 `design/pages/`。
改法與規則見 [design/README.md](design/README.md)。

## 本機預覽

```bash
python3 design/serve.py design 8747
```

然後開 http://localhost:8747/pages/01-intake.html（站 2、站 3 換檔名），
元件參考站在 http://localhost:8747/ui/reference.html。

## 已知限制

- 前端假資料，沒有後端、沒有資料庫、沒有 API 串接。上傳區是靜態畫面，不會真的解析 PDF 或行事曆
- mist 目前沒有深色模式，三頁都只有亮色
- 資料為示範用途，那位「5 年 3 份工作、零 side project、近 3 個月 3 次獵頭面談」的使用者是虛構的
