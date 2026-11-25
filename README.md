# celine.fu — 個人網站

線上：<https://afortunadofu-bot.github.io/celine.fu/>

| 路徑 | 內容 | 誰產生的 |
|---|---|---|
| `index.html` | 個人網頁（中英雙語）。漢堡選單裡有「分析作品集」那一區 | 手寫 |
| `work/` | 分析作品集，八頁 | **自動產生，不要手改** |
| `work/stats.json` | 全站共用的數字；小數據所品牌頁也 fetch 這一份 | 自動產生 |
| `index0416.html` | 2026-04 的舊版，備查 | 手寫 |

## work/ 怎麼更新

內容由壽星日 repo 的 `claude/analysis/` 產生，**不要直接改 `work/` 裡的檔案**，
下次重建就會被蓋掉。

```bash
cd "<壽星日 repo>/claude/analysis"
python build_db.py --live      # 要換成最新的線上資料時才跑
python publish_portfolio.py    # 重建 + 推這個 repo 與壽星日 repo
```

`publish_portfolio.py` 會把產出寫進這裡的 `work/`，兩個 repo 一起 commit + push。

---

## 版本紀錄

由新到舊。

### 2026-11-25　作品集併進這個站

- 新增 `work/`：分析作品集八頁（首頁、壽星日、Bandary、RelateStats、
  機電請款預估、投稿欄位預填、商圈自動分群、十一題 SQL 報告），
  由壽星日 repo 的 `analysis/build_site.py` 產生
- 漢堡選單加「分析作品集」一區，六個入口直接點進 `work/`
- 首頁「自己做的」那一區與頁尾的連結改成站內相對路徑
- 作品集每一頁左上角可以回到這個首頁
- 舊網址 `afortunadofu-bot.github.io/birthday-deals/*` 全部留轉址頁，
  之前貼出去的連結不會壞

### 2026-11-25　加「自己做的」一節，串起小數據所與作品集

- 新增 `#studio`：三個自有產品與作品集的入口；優惠數、收藏數、分群店家數、
  分類器準確率四個數字用 fetch 從 `work/stats.json` 即時抓，抓不到就留後備值
- 首頁標語補第二句，把「數字我自己算」的定位也講出來
  （原本在 `Website_celine` 那個版本，兩站合併到這裡）
- 選單、頁尾加上小數據所與作品集的連結；聯繫方式改成 06

### 2026-07-31 以前

個人網頁本體（雙語、專案卡、技能矩陣、時間軸）。
當時另外有一個 `Website_celine` 版本，2026-11-25 已經合併過來、那邊改成轉址。
