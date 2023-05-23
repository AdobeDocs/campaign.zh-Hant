---
title: 使用目標對應
description: 瞭解如何使用和建立目標映射
feature: Audiences, Profiles
role: User, Developer
level: Beginner, Intermediate
exl-id: 5256fc15-1878-4064-9c75-7876a3826b83
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 4%

---

# 使用目標對應{#gs-target-mappings}

預設情況下，交貨模板目標 **[!UICONTROL Recipients]**。 因此，其目標映射使用 **nms：收件人** 的子菜單。

您可以使用其它目標映射進行交貨，或建立新的目標映射。

## 內置目標映射 {#ootb-mappings}

Adobe Campaign提供以下內置目標映射：

| 名稱 | 用於 | 結構描述 |
|---|---|---|
| 收件者 | 傳遞給收件人（內置收件人表） | nms：收件人 |
| 訪客 | 向通過轉介（病毒式營銷）收集個人資料的訪問者交付。 | mns：訪問者 |
| 訂閱 | 向訂閱新聞通訊等資訊服務的收件人提供 | nms：訂閱 |
| 訪客訂閱 | 向訂閱資訊服務的訪問者發送 | nms:visitorSub |
| 運算子 | 交付給Adobe Campaign運營商 | nms：運算子 |
| 外部檔案 | 通過包含交付所需的所有資訊的檔案進行交付 | 沒有連結架構，沒有輸入目標 |

## 建立目標映射 {#new-mapping}

還可以建立目標映射。 您可能需要添加自定義目標映射，例如：

* 使用自定義收件人表，
* 您可以配置篩選維，該維與目標映射螢幕上的內置目標維不同。

瞭解有關中的自定義收件人表的詳細資訊 [此頁](../dev/custom-recipient.md)。

Adobe Campaign目標映射建立嚮導可幫助您建立使用自定義目標映射所需的所有架構。

1. 瀏覽到 **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** Adobe Campaign探險家。

1. 建立新目標映射並選擇自定義方案作為目標維。

   ![](assets/new-target-mapping.png)


1. 指示儲存配置檔案資訊的欄位：姓氏、名字、電子郵件、地址等

   ![](assets/wf_new_mapping_define_join.png)

1. 指定資訊儲存的參數，包括擴展架構的尾碼，以便它們能夠輕鬆識別。

   ![](assets/wf_new_mapping_define_names.png)

   您可以選擇是否儲存排除(**排除日誌**)，帶消息(**廣播**)或單獨的表中。

   您還可以選擇是否管理此交貨映射的跟蹤(**跟蹤日誌**)。

1. 然後選擇要考慮的擴展。 擴展類型取決於您的市場活動設定和載入項。

   ![](assets/wf_new_mapping_define_extensions.png)

   按一下 **[!UICONTROL Save]** 按鈕啟動交貨映射建立：所有連結的表都會基於所選參數自動建立。
