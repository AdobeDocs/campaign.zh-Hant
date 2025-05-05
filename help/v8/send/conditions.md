---
title: 條件式內容
description: 瞭解如何建立條件式內容
feature: Personalization
role: User
level: Beginner
exl-id: bcbf3101-d43c-4ed3-ab02-a9936ec55b71
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 10%

---

# 建立條件式內容{#conditional-content}

透過設定條件式內容欄位，您可以建立進階的個人化。滿足特定條件時，即可取代完整的文字區塊及/或影像。


## 在電子郵件中使用條件 {#conditions-in-an-email}

在下列範例中，瞭解如何建立訊息，以動態方式個人化收件者的城市和興趣。

* 根據收件者的城市變更訊息
* 根據收件者的興趣個人化優惠內容。

若要根據欄位值建立條件式內容，請套用下列步驟：

1. 開啟現有的傳遞，或建立新的電子郵件傳遞。
1. 在電子郵件內容編輯器中，按一下個人化圖示並選取&#x200B;**[!UICONTROL Conditional content > If]**。

   ![插入條件](assets/condition-insert.png)

   個人化元素會插入訊息內文中。 您現在必須加以設定。

1. 填寫&#x200B;**if**&#x200B;運算式的引數。

   * 選取運算式的第一個元素&#x200B;**`<FIELD>`**，然後按一下個人化圖示，以測試欄位取代它。
   * 將&#x200B;**`<VALUE>`**&#x200B;取代為將滿足條件的欄位值。 此值必須在引號中。
   * 指定滿足條件時要插入的內容。 這可以是文字、影像、表單、超文字連結等。

   電子郵件中的![狀況](assets/condition-in-email.png)

1. 按一下&#x200B;**[!UICONTROL Preview]**&#x200B;索引標籤，根據傳遞收件者檢視郵件內容。 選取條件為true的收件者以檢查內容。 然後選取其他為false的收件者，並再次檢查。

您可以新增其他案例，並根據一或多個欄位的值定義不同的內容。 若要這麼做，請使用&#x200B;**[!UICONTROL Conditional content > Else]**&#x200B;和&#x200B;**[!UICONTROL Conditional content > Else if]**。 這些運算式的設定方式與&#x200B;**if**&#x200B;運算式相同。

>[!CAUTION]
>
>新增&#x200B;**Else**&#x200B;和&#x200B;**Else if**&#x200B;條件後，必須刪除&#x200B;**%> &lt;%**&#x200B;字元。


## 使用案例：建立多語言電子郵件 {#creating-multilingual-email}

在下列範例中，瞭解如何建立多語言電子郵件。 內容會根據收件者偏好的語言，以一種或另一種語言顯示。

1. 建立電子郵件並選取目標母體。 在此範例中，顯示一個版本或另一個版本的條件將依據收件者設定檔的&#x200B;**語言**&#x200B;值。 這些值設定為&#x200B;**EN**、**FR**、**ES**。
1. 在電子郵件HTML內容中，按一下「**[!UICONTROL Source]**」標籤，然後貼上下列程式碼：

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

1. 選取不同慣用語言的收件者，以測試&#x200B;**[!UICONTROL Preview]**&#x200B;索引標籤中的電子郵件內容。

   >[!NOTE]
   >
   >由於電子郵件內容中未定義替代版本，因此在傳送電子郵件前請務必篩選目標母體。

## 教學課程影片 {#conditionnal-content-video}

此影片以多語言電子報為範例，示範如何新增條件式內容至傳遞。

>[!VIDEO](https://video.tv.adobe.com/v/3426541?quality=12&captions=chi_hant)
