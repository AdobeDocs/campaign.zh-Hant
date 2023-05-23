---
title: 條件式內容
description: 瞭解如何建立條件內容
feature: Personalization
role: User
level: Beginner
exl-id: bcbf3101-d43c-4ed3-ab02-a9936ec55b71
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 9%

---

# 建立條件內容{#conditional-content}

透過設定條件式內容欄位，您可以建立進階的個人化。滿足特定條件時，便可以取代完整的文字區塊及/或影像。


## 在電子郵件中使用條件 {#conditions-in-an-email}

在下面的示例中，瞭解如何根據收件人的城市和興趣動態個性化建立消息。

* 根據收件人所在城市更改郵件，
* 根據收件人的興趣個性化報價內容。

要根據欄位的值建立條件內容，請應用以下步驟：

1. 開啟現有傳遞或建立新電子郵件傳遞。
1. 在電子郵件內容編輯器中，按一下個性化表徵圖並選擇 **[!UICONTROL Conditional content > If]**。

   ![插入條件](assets/condition-insert.png)

   個性化元素被插入消息主體中。 您現在必須配置它們。

1. 填寫 **如果** 表達式。

   * 選擇表達式的第一個元素， **`<FIELD>`**，然後按一下個性化表徵圖，將其替換為test欄位。
   * 替換 **`<VALUE>`** 的值。 此值必須用引號括起來。
   * 指定滿足條件時要插入的內容。 這可以是文本、影像、表單、超文本連結等。

   ![電子郵件中的條件](assets/condition-in-email.png)

1. 按一下 **[!UICONTROL Preview]** 頁籤，根據傳遞收件人查看郵件內容。 選擇條件為true的收件人以檢查內容。 然後選擇其為false的其他收件人，然後再次檢查。

您可以添加其它案例，並根據一個或多個欄位的值定義不同的內容。 要執行此操作，請使用 **[!UICONTROL Conditional content > Else]** 和 **[!UICONTROL Conditional content > Else if]**。 這些表達式的配置方式與 **如果** 表達式。

>[!CAUTION]
>
>的 **%> &lt;%** 添加後必須刪除字元 **埃爾塞** 和 **否則** 的下界。


## 用例：建立多語言電子郵件 {#creating-multilingual-email}

在下面的示例中，瞭解如何建立多語言電子郵件。 內容以一種語言或另一種語言顯示，具體取決於收件人的首選語言。

1. 建立電子郵件並選擇目標填充。 在本示例中，顯示一個版本或另一個版本的條件將基於 **語言** 收件人配置檔案的值。 這些值設定為 **EN**。 **FR**。 **ES**。
1. 在電子郵件HTML內容中，按一下 **[!UICONTROL Source]** 頁籤並貼上以下代碼：

   ```
   <% if (language == "EN" ) { %>
   <DIV id=en-version>Hello <%= recipient.firstName %>,</DIV>
   <DIV>Discover your new offers!</DIV>
   <DIV><a href="https://www.adobe.com/products/en">www.adobe.com/products/en</A></FONT></DIV><%
    } %>
   <% if (language == "FR" ) { %>
   <DIV id=fr-version>Bonjour <%= recipient.firstName %>,</DIV>
   <DIV>Découvrez nos nouvelles offres !</DIV>
   <DIV><a href="https://www.adobe.com/products/fr">www.adobe.com/products/fr</A></DIV><%
    } %>
    <% if (language == "ES" ) { %>
   <DIV id=es-version><FONT face=Arial>
   <DIV>Olà <%= recipient.firstName %>,</DIV>
   <DIV>Descubra nuestros nuevas ofertas !</DIV>
   <DIV><a href="https://www.adobe.com/products/es">www.adobe.com/products/es</A></DIV>
   <% } %>
   ```

1. Test **[!UICONTROL Preview]** 頁籤。

   >[!NOTE]
   >
   >由於電子郵件內容中未定義任何替代版本，因此請確保在發送電子郵件之前過濾目標填充。

## 教程視頻 {#conditionnal-content-video}

此影片以多語言電子報為範例，示範如何新增條件式內容至傳遞。

>[!VIDEO](https://video.tv.adobe.com/v/335682?quality=12)
