# Day 02 — 2026-10-30 — Lakehouse & Medallion / Lakehouse 與 Medallion

> **中文與英文對照 / Bilingual hands-on handbook** · 約 7 小時有效學習（不含休息）/ ~7 active study hours excluding breaks.
>
> **今日核心目標 / Today's mission:** **Lakehouse 與 Medallion (Lakehouse & Medallion)** + **企業 TDM Strategy (TDM strategy)**.

## 0. 今日先看這裡 / Start here (15 min)

**中文：** 今天的學習輸出包括 1 個 Databricks 實驗、1 個 TDM/產品實驗、1 次故障/負向測試，以及簡短設計紀錄。你已經懂 Python/SQL，因此重點是如何用於 Enterprise TDM，不重讀語法入門。

**English:** Produce one Databricks lab, one TDM/vendor lab, a negative test, and a short architecture decision note. Leverage existing Python/SQL experience rather than restarting fundamentals.

## 1. Databricks 官方課程 / Official lesson (75 min)

**直接開啟 / Open:**
1. [Databricks 官方技術教學 / Official documentation](https://docs.databricks.com/aws/en/lakehouse/medallion)
2. [原本 Bootcamp Day 02 詳細教材 / Your earlier lesson](https://github.com/tim5633/databricks-data-ai-engineering-bootcamp/blob/main/curriculum/day-02.md)
3. [Databricks Partner Academy / 公司課程入口](https://partner-academy.databricks.com/) — requires company entitlement.

**官網具體位置 / Exact public page section:** `Medallion architecture / Bronze Silver Gold`.

**介面點擊路徑 / UI click path:** Workspace → New → Notebook（SQL cell）.

**中文步驟：** (a) 打開上方第一個官方連結；(b) 找到 `Medallion architecture / Bronze Silver Gold` 的對應標題；(c) 看完範例並記錄三個重點；(d) 回到舊 Bootcamp Day 02 核對相同主題；(e) 如有 Partner Academy 權限，搜尋 `Lakehouse & Medallion` 並依登入後實際課程名稱學習。*沒有公開驗證的內部 Lesson 直達網址不會虛構。*

**English steps:** (a) Open the exact official resource; (b) locate the section named above; (c) examine its worked example and note three insights; (d) check your previous Day 02; (e) use the Academy course search if authenticated. *Gated course section names/URLs are not presented as verified.*

**時間 / Timing:** 15m official page → 25m guided examples → 20m old bootcamp lesson → 15m write your notes.

## 2. Databricks 可複製 Lab / Copy-and-run lab (100 min)

**中文預期 / Goal:** 用 CTE 模擬 Bronze → Silver → Gold.

**執行位置 / Run location:** Databricks SQL Editor 或 Notebook SQL Cell / SQL Editor or notebook SQL cell.

```sql
WITH bronze AS (SELECT 1 AS id, 'A' AS raw_status), silver AS (SELECT id, upper(raw_status) AS status FROM bronze) SELECT status, count(*) AS n FROM silver GROUP BY status;
```

**預期結果 / Expected result:** `A | 1`.

**逐步操作 / Execution steps:**
1. 中文：複製到新 Notebook / SQL Editor，先執行一次。English: Paste and run once.
2. 中文：比對實際輸出與上方 expected result。English: Compare with the expected output.
3. 中文：改一個輸入（例如 ID、status 或 amount）並預測結果。English: Change one input and predict output first.
4. 中文：加入一個不合法或異常輸入，確認失敗方式。English: Test one invalid case and record failure mode.
5. 中文：保存程式和執行證據到 `labs/day-02/`。English: Save code and evidence in the named folder.

**環境限制 / Environment caveat:** 部分功能需要 Unity Catalog 或適當權限，不能建立資料表時請使用自己的 schema 或本機模擬，並記錄差異。 / Some features require entitlements; use a permitted schema or a clearly marked offline simulation.

## 3. TDM / 工具官方學習 / Vendor learning (65 min)

**主題 / Topic:** 企業 TDM Strategy / TDM strategy.

**官方資源 / First-party resource:** [TDM strategy](https://www.genrocket.com/newsletter/test-data-lifecycle/).

**要做什麼 / Exact target:** Write goals, consumers and governance RACI. **中文：**寫出目標、消費者、責任分工 RACI。

**步驟 / Sequence:**
1. 中文：打開官方連結；找今天的關鍵詞 `TDM strategy`。English: Open the source and find today's key concepts.
2. 中文：寫下此功能解決的測試資料需求，以及對 PK/FK、Privacy 或 Refresh 的影響。English: Document the data requirement and integrity/privacy/refresh impact.
3. 中文：如果是 GenRocket 需登入才能看到的課程，進入 [Flight School](https://www.genrocket.com/flight-school-welcome/) 並搜尋今天的 Domain/Generator/Scenario 主題。不可假設已獲授權。English: Use the authenticated Flight School navigation if available; do not assume access.
4. 中文：如果是 MOSTLY AI，優先跟著 [SDK Quick Start](https://mostly-ai.github.io/mostlyai/) 及 [Tutorials](https://mostly-ai.github.io/mostlyai/tutorials/)；大型本機模型訓練可選做。English: Follow SDK Quick Start/Tutorials and treat resource-intensive local training as optional.

**資源身份說明 / Resource status:** 以上是官方公開頁面或已標示需要登入的入口；若未提供單一課內影片的 URL，表示目前無法公開核實，並不是已確認的精準 Section 連結。

## 4. TDM 可執行練習 / Reproducible TDM lab (100 min)

**中文任務 / Task:** 寫出目標、消費者、責任分工 RACI。使用的都是虛構資料，不能提交任何公司或客戶資料。

**English:** Reproduce write goals, consumers and governance raci with fictional inputs only. This is a baseline simulation, **not** proof of using GenRocket commercially.

```python
roles={"Data Owner":"approve policy","TDM Engineer":"provision test data","QA":"validate scenarios"}
assert len(roles)==3
print(roles)
```

**執行步驟 / Run:** (1) 在本機 `python3` 或 Notebook 執行 / run in local Python or notebook; (2) assert 應通過 / assertions must pass; (3) 改一筆輸入讓驗證失敗 / change input to trigger failing check; (4) 記錄修復方式 / record the fix.

**工具實作 / Tool-specific extension:** 如果今天有 GenRocket/MOSTLY AI 實際授權，就同時在該工具建立等價輸出，保留設定與結果截圖。沒有權限時只算完成 Python fallback，不算取得產品實務能力。 / If licensed, reproduce the result in the actual platform and collect evidence; otherwise label the fallback honestly.

## 5. Capstone 整合 / Capstone integration (45 min)

**中文：** 在架構圖標示今天技術在 `需求 → 合成資料 → 遮罩/子集 → Databricks Delta/Gold Copy → QA 環境 → 自動化測試 → 治理` 的位置，寫一段 100 字的設計取捨。

**English:** Mark where today's capability fits in `requirements → synthetic generation → masking/subsetting → Delta/Gold Copy → QA provision → tests → governance`. Write a 100-word decision note with one alternative.

## 6. 回顧與驗收 / Review and acceptance (35 min)

- [ ] **知識 / Knowledge:** 能用中文和英文各解釋 Lakehouse & Medallion / Lakehouse 與 Medallion。
- [ ] **程式 / Execution:** Databricks Lab 得到 `A | 1` 或有明確環境限制證據。
- [ ] **TDM / Vendor:** 完成 企業 TDM Strategy 的練習並保存檔案。
- [ ] **Quality:** 有一次可重現的負向測試與修復方法。
- [ ] **Privacy:** 沒有真實個人資料、客戶資料、密鑰或內部教材。
- [ ] **Evidence:** `labs/day-02/README.md` 含指令、輸出、截圖位置、問題及解法。

**完成定義 / Definition of done:** 能在 3 分鐘內展示今日結果；如果只是看完課程但 Lab 沒成功，不能標記完成。 / Demo the results in 3 minutes; watching videos alone does not count.

**遇到權限問題 / Blocked?** 改用公開文件 + 可執行 Python/SQL fallback，記錄 `BLOCKED: login/permission/feature`；正式產品操作保留待補。 / Use the public fallback and log the missing authorization or feature.
