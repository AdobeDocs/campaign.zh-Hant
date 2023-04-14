---
title: 條件式內容
description: 了解如何建立條件式內容
feature: Personalization
role: User
level: Beginner
exl-id: bcbf3101-d43c-4ed3-ab02-a9936ec55b71
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 9%

---

# 建立條件式內容{#conditional-content}

透過設定條件式內容欄位，您可以建立進階的個人化。滿足特定條件時，便可以取代完整的文字區塊及/或影像。


## 在電子郵件中使用條件 {#conditions-in-an-email}

在以下範例中，了解如何建立訊息，並依收件者的城市和興趣進行動態個人化。

* 根據收件者的城市變更訊息，
* 根據收件者的興趣個人化優惠方案的內容。

要根據欄位的值建立條件式內容，請應用以下步驟：

1. 開啟現有的傳送，或建立新的電子郵件傳送。
1. 在電子郵件內容編輯器中，按一下個人化圖示並選取 **[!UICONTROL Conditional content > If]**.

   ![插入條件](assets/condition-insert.png)

   個人化元素會插入訊息內文。 您現在必須進行設定。

1. 填入 **if** 運算式。

   * 選取運算式的第一個元素， **`<FIELD>`**，然後按一下個人化圖示，將其取代為測試欄位。
   * 取代 **`<VALUE>`** 填入將滿足條件的欄位值。 此值必須用引號表示。
   * 指定在滿足條件時要插入的內容。 這可以是文字、影像、表單、超文字連結等。

   ![電子郵件中的條件](assets/condition-in-email.png)

1. 按一下 **[!UICONTROL Preview]** 標籤，以根據傳送收件者檢視訊息內容。 選取條件為true的收件者以檢查內容。 然後，選取另一個收件者，其為false，然後再次檢查。

您可以新增其他案例，並根據一或多個欄位的值定義不同內容。 若要這麼做，請使用 **[!UICONTROL Conditional content > Else]** 和 **[!UICONTROL Conditional content > Else if]**. 這些運算式的設定方式與 **if** 運算式。

>[!CAUTION]
>
>此 **%> &lt;%** 新增後必須刪除字元 **Else** 和 **若** 條件。


## 使用案例：建立多語言電子郵件 {#creating-multilingual-email}

在以下範例中，了解如何建立多語言電子郵件。 內容會根據收件者的偏好語言，以一種或另一種語言顯示。

1. 建立電子郵件並選取目標母體。 在此範例中，顯示一個版本或另一個版本的條件將以 **語言** 收件者設定檔的值。 這些值會設為 **EN**, **FR**, **ES**.
1. 在電子郵件HTML內容中，按一下 **[!UICONTROL Source]** 標籤，然後貼上下列程式碼：

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

1. 在 **[!UICONTROL Preview]** 頁簽，方法是選取使用不同偏好語言的收件者。

   >[!NOTE]
   >
   >由於電子郵件內容中未定義任何替代版本，因此請務必在傳送電子郵件前篩選目標母體。

## 教學課程影片 {#conditionnal-content-video}

此影片以多語言電子報為範例，示範如何新增條件式內容至傳遞。

>[!VIDEO](https://video.tv.adobe.com/v/335682?quality=12)
