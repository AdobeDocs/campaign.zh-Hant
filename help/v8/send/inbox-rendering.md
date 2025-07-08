---
product: campaign
title: Campaign中的收件匣轉譯
description: 瞭解如何擷取電子郵件呈現，並提供在專用報告中
feature: Inbox Rendering, Monitoring, Email Rendering
role: User
version: Campaign v8, Campaign Classic v7
exl-id: a3294e70-ac96-4e51-865f-b969624528ce
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 8%

---

# 收件匣轉譯{#inbox-rendering}

## 關於收件匣轉譯 {#about-inbox-rendering}

在按下&#x200B;**傳送**&#x200B;按鈕之前，請確定您的郵件會以最佳方式顯示在各種Web使用者端、網頁郵件與裝置上。

為了執行此操作，Adobe Campaign會利用[Litmus](https://litmus.com/email-testing){target="_blank"}網頁型電子郵件測試解決方案來擷取呈現，並將這些呈現呈現顯示在專用報告中。 這可讓您在可能接收訊息的不同內容中預覽所傳送的訊息，並檢查主要桌上型電腦和應用程式中的相容性。

>[!CAUTION]
>收件匣轉譯與[週期性傳遞](../../automation/workflow/recurring-delivery.md)不相容。

Litmus是功能豐富的電子郵件驗證和預覽應用程式。 它可讓電子郵件內容建立者在超過70個電子郵件轉譯器中預覽其訊息內容，例如Gmail收件匣或Apple Mail使用者端。

適用於Adobe Campaign中&#x200B;**收件匣轉譯**&#x200B;的行動裝置、傳訊及網路郵件使用者端列於[Litmus網站](https://litmus.com/email-testing){target="_blank"} （按一下&#x200B;**檢視所有電子郵件使用者端**）。

>[!NOTE]
>
>測試傳送中的個人化時，不需要收件匣轉譯。 可以使用&#x200B;**[!UICONTROL Preview]**&#x200B;和[校樣](preview-and-proof.md#send-proofs)等Adobe Campaign工具檢查Personalization。

## 關於Litmus權杖 {#about-litmus-tokens}

由於Litmus是協力廠商服務，因此能以每次使用點數計量的模式運作。 每次使用者呼叫Litmus功能時，評分都會扣除。

在Adobe Campaign中，評分會與可用轉譯（稱為權杖）的數量相對應。

>[!NOTE]
>
>可用的Litmus權杖數量取決於您購買的Campaign授權。 檢查您的授權合約。

每次您在傳送中使用&#x200B;**[!UICONTROL Inbox rendering]**&#x200B;功能時，產生的每次轉譯都會將您的可用Token減少一次。

>[!IMPORTANT]
>
>代號會說明每個個別轉譯，而非整個收件匣轉譯報表，這表示：
>
>* 每次產生收件匣轉譯報告時，每個傳訊使用者端都會扣除一個權杖：一個適用於Outlook 2000轉譯、一個適用於Outlook 2010轉譯、一個適用於Apple Mail 9轉譯，以此類推。
>* 對於相同的傳送，如果您再次產生收件匣轉譯，可用權杖的數量會再次減少產生的轉譯數量。
>

剩餘的可用代號數目會顯示在[收件匣轉譯報告](#inbox-rendering-report)中。

![](assets/s_tn_inbox_rendering_tokens.png)

收件匣轉譯功能通常用於測試新設計電子郵件的HTML架構。 每個轉譯最多需要大約70個權杖（取決於通常測試的環境數量）。 但是，在某些情況下，您可能需要多個收件匣轉譯報告才能完整測試您的傳送。 因此，可能需要更多權杖才能完成數項檢查。

## 存取收件匣轉譯報告 {#accessing-the-inbox-rendering-report}

在您建立電子郵件傳送並定義其內容以及目標定位群體後，請遵循下列步驟。

如需建立、設計和鎖定傳送的詳細資訊，請參閱[本節](defining-the-email-content.md)。

1. 在傳遞的頂端列上，按一下&#x200B;**[!UICONTROL Inbox rendering]**&#x200B;按鈕。

1. 選取&#x200B;**[!UICONTROL Analyze]**&#x200B;以啟動擷取處理作業。

   ![](assets/s_tn_inbox_rendering_button.png)

   已傳送證明。 傳送電子郵件後幾分鐘，即可在該校訂中存取轉譯縮圖。 如需傳送校樣的詳細資訊，請參閱[本節](preview-and-proof.md#send-proofs)。

1. 傳送後，證明會出現在傳送清單中。 按兩下。

   ![](assets/s_tn_inbox_rendering_delivery_list.png)

1. 前往校訂的&#x200B;**收件匣轉譯**&#x200B;標籤。

   ![](assets/s_tn_inbox_rendering_tab.png)

   此時會顯示「收件匣轉譯」報告。

## 收件匣轉譯報告 {#inbox-rendering-report}

此報表會顯示收件者看到的收件匣呈現。 根據收件者開啟電子郵件傳送的方式，呈現可能會有所不同：在瀏覽器中、行動裝置上，或透過電子郵件應用程式。

頂端區段顯示透過圖形化色彩編碼表示法重新分割已接收、不想要（垃圾郵件）、未接收或待接收的訊息數目。

![](assets/s_tn_inbox_rendering_summary.png){width="40%" align="left"}

將滑鼠指標暫留在圖表上，即可顯示每種顏色的詳細資料。 按一下清單上的專案以隱藏或顯示圖表中的對應類別。

報告正文分為三個部分： **[!UICONTROL Mobile]**、**[!UICONTROL Desktop]**&#x200B;和&#x200B;**[!UICONTROL Webmails]**。 向下捲動報告，以顯示分為這三種類別的所有呈現。

![](assets/s_tn_inbox_rendering_report.png)

若要取得每個報告的詳細資料，請按一下相對應的卡片。會針對所選取接收方法來顯示呈現。

![](assets/s_tn_inbox_rendering_example.png)
