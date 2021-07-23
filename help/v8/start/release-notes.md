---
product: Adobe Campaign
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: 概覽
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 5d266b22661be2817e06ea71c1b0bec7f44a152d
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 7%

---

# 最新發行版本{#latest-release}

此頁面列出&#x200B;**最新Campaign v8版本**&#x200B;的新功能、改善和修正。

## 第 8.1.14 發行版本 {#release-8-1-14}

_2021年7月23日_

**新增功能？**

<table>
<thead>
<tr>
<th><strong>新工作流活動：變更資料來源</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新的<b>變更資料來源</b>工作流程活動可讓您變更工作流程工作表的資料來源。 這為管理不同資料來源（FDA、FFDA和本機資料庫）的資料提供更強大的彈性。</p>
<p>在Adobe Campaign工作流程中，資料是使用工作（或暫時）表格來管理。 工作流程執行時，工作表會在各工作流程活動中共用資料。 預設情況下，工作表與我們查詢的資料源建立在同一資料庫上。</p>
<p>使用Campaign v8時，主要設定檔表格會直接儲存在雲端資料庫中。 因此，查詢Profiles表格也會在雲端資料庫上建立工作表。 在某些情況下，將工作表移動到其他資料源以執行特定操作是有意義的。</p>
<p>如需詳細資訊，請參閱<a href="../config/workflows.md#change-data-source-activity">相關的文件</a>，以瞭解詳情。</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>LINE通道可用性</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>LINE管道現在可與Campaign v8搭配使用。 使用LINE與訊息中心時已進行下列增強：
</p>
<ul> 
<li><p>修正了無法在LINE傳送中鎖定訪客的問題。 
</p></li>
<li><p>修正從執行例項擷取訪客至行銷例項時，可能會導致錯誤的問題。
</p></li>
<li><p>修正使用訊息中心處理LINE傳送內容中即時事件的問題。</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**其他改善項目**

* 修正了無法針對特定傳送顯示&#x200B;**熱點點按**&#x200B;報表的問題。
* 修正了&#x200B;**重複資料刪除**&#x200B;工作流程活動可能導致錯誤重複計數的問題。
* 修正搭配「ID不是空白」篩選使用工作流程查詢時，可能導致轉變母體中顯示空白項目的問題。
* 修正無法在新目標對應中建立其他欄位的問題。
