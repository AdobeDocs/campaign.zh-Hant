---
title: 開始使用Adobe Campaign analytics報表
description: 了解如何建立立方體
feature: Reporting
role: Data Engineer
level: Beginner
source-git-commit: cc7195e90c38489f8e3946d6abd190effd41941a
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 14%

---

# 開始使用Campaign分析報表 {#gs-cube}

Adobe Campaign隨附直覺式資料探索工具，可建立動態報表。

使用行銷分析功能來分析和測量資料、計算統計資料、簡化並最佳化報表建立和計算。 您可以建立報表並建立目標母體，並將它們儲存至清單中，以便在Adobe Campaign中用於目標定位或細分任務。

您可以擴充資料庫的探索和分析能力，同時讓最終使用者更容易設定報告和表格：他們只需在建立其報告或表格時，選取現有的（全設定好的）多維度資料集，以處理計算、測量和統計數據。

建立並設定多維度資料集後，便可以用於報告查詢方塊和網頁應用程式；可以在樞紐分析表內使用及操作多維度資料集。

使用Campaign Marketing Analytics模組可以：

1. 建立立方體和指標

   * 匯總資料並儲存在工作表中，以根據使用者需求預先計算指標，
   * 減少用於報告和查詢的各種計算中涉及的資料量，從而顯著優化指標計算時間，
   * 簡化資料存取，讓使用者能根據各種維度來控制資料（無論資料是否預先匯總）。

   有關詳細資訊，請參閱 [建立指標](cube-indicators.md).

1. 建立樞紐表及探索資料

   * 探索計算資料，配置測量，
   * 選取要顯示的資料及其顯示模式，
   * 個人化所使用的措施和指標，
   * 為非技術背景的使用者提供互動式分析工具。

   有關詳細資訊，請參閱 [使用立方體來探索資料](cube-tables.md).

1. 使用在多維資料集中計算和匯總的資料建立查詢。
1. 識別母體，並在清單中參照母體。

## 術語 {#terminology}

使用多維度資料集時的特定辭彙列於下方。

* **立方體**  — 多維資料集表示多維資訊：它為最終用戶提供了專為互動式資料分析而設計的結構。

* **數值表/方案**  — 事實表（或事實模式）包含分析所依據的原始或基本資料。 這些表主要是大量表（可能包含連結的表），計算時間可能很長。 例如，事實表可以是：broadlog表格、購買表格等

* **Dimension** -Dimension可讓您將資料分段至群組：建立維後，維將用作分析軸。 在大多數情況下，會針對指定的維度定義數個層級。 例如，對於臨時維度，層級會是月、天、小時、分鐘等。 這組層級代表維度階層，並啟用各種資料分析層級。

* **賓寧**  — 對於某些欄位，您可以定義組值的綁定，並更方便讀取資訊。 系結會套用至層級。 建議您在可能有許多不同值時定義捆綁。

* **測量**  — 最頻繁的措施是和、平均、最大、最小、標準差等。 可以計算度量：例如，要約的接受率是其被呈現的次數與被接受的次數之比。