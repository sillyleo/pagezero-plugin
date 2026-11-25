---
name: pagezero-page-research
description: 研究指定網站頁面的搜尋意圖、客戶問題、建議關鍵字和內容缺口，將研究結果保存至該站 Wiki。適用於針對單一頁面進行題材規劃。
---

以 `listSites` 找出使用者指定的網站和 `site_id`。網站或目標頁面不明確時先釐清。

使用者要求開始研究時，呼叫 `pageResearchBrief`，傳入該站的 `site_id` 和目標頁面 `target_url`。這會啟動使用模型額度的背景工作。若使用者提供了先前的 `workflow_run_id` 並要求查看結果，直接查詢該次工作。

以原 `site_id`、`workflow_run_id` 呼叫 `getWorkflowResult`。狀態為 queued 或 running 時回報進度，保留同一個工作 ID。完成後以 `section: "result"` 讀取 `wiki_documents`，將實際文件的標題及連結交給使用者。失敗時回報該次狀態。追蹤關鍵字或提示詞需要使用者另外要求。
