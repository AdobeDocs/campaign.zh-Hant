---
title: 合作使用Campaign與Adobe Experience Manager
description: 瞭解如何使用Campaign和Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
source-git-commit: b267cb37a94bd389232ccfb9b8df69c9c2caa990
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# 合作使用Campaign與Adobe Experience Manager {#ac-aem}

Adobe Campaign與Adobe Experience Manager的整合可讓您直接在Adobe Experience Manager中管理電子郵件傳送的內容及表單。 您可以選擇匯入 **Adobe Experience Manager** 將內容加入Campaign或連線至 **Adobe Experience Manager雲端服務** 帳戶，可讓您直接在網頁介面中編輯內容。

![](../assets/do-not-localize/book.png) [瞭解如何在Campaign網頁介面中編輯您的Adobe Experience Manager作為Cloud Service內容](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/content/integrations/aem-content.html?lang=en)

![](../assets/do-not-localize/book.png) [在本檔案中進一步瞭解Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html#aem-and-adobe-campaign-integration-workflow)

## 使用Adobe Experience Manager製作 {#integrating-with-aem}

![](../assets/do-not-localize/speech.png)  作為「受管理的Cloud Service」使用者， [連絡人Adobe](../start/campaign-faq.md#support) 將Adobe Experience Manager與Campaign整合。

例如，這項整合可用於在Adobe Experience Manager中建立電子報，接著在Adobe Campaign中作為電子郵件促銷活動的一部分使用。

**從Adobe Experience Manager：**

1. 導覽至 [!DNL Adobe Experience Manager] 編寫執行個體，然後按一下頁面左上角的Adobe體驗。 選擇 **[!UICONTROL Sites]** 功能表中。

   ![](assets/aem_authoring_1.png)

1. 存取 **[!UICONTROL Campaigns > Name of your brand (here we.Shopping) > Main Area > Email]**.

1. 按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Page]** 下拉式選單中的。

   ![](assets/aem_authoring_2.png)

1. 選取 **[!UICONTROL Adobe Campaign Email]** 範本並命名您的Newsletter。

1. 建立頁面後，存取 **[!UICONTROL Page information]** 功能表並按一下 **[!UICONTROL Open Properties]**.

   ![](assets/aem_authoring_3.png)

1. 透過新增元件來自訂您的電子郵件內容，例如Adobe Campaign的個人化欄位。 [了解更多](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html?lang=en#editing-email-content)

1. 電子郵件準備就緒後，請導覽至 **[!UICONTROL Page information]** 功能表並按一下 **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_4.png)

1. 從第一個下拉式清單中選取 **[!UICONTROL Approve Adobe Campaign]** 作為工作流程模型並按一下 **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_5.png)

1. 免責宣告會出現在您的頁面頂端，指出： `This page is subject to the workflow Approve for Adobe Campaign`. 按一下 **[!UICONTROL Complete]** 在免責宣告旁確認檢閱並按一下 **[!UICONTROL Ok]**.

1. 按一下 **[!UICONTROL Complete]** 再次選擇並選取 **[!UICONTROL Newsletter approval]** 在 **[!UICONTROL Next Step]** 下拉式清單。

   ![](assets/aem_authoring_6.png)

您的Newsletter現已準備就緒，並已在Adobe Campaign中同步。

**從Adobe Campaign：**

1. 從 **[!UICONTROL Campaigns]** 標籤，按一下 **[!UICONTROL Deliveries]** 則 **[!UICONTROL Create]**.

1. 選擇 **[!UICONTROL Email delivery with AEM content (mailAEMContent)]** 範本來自 **[!UICONTROL Delivery template]** 下拉式功能表。

   ![](assets/aem_authoring_7.png)

1. 新增 **[!UICONTROL Label]** 至您的傳遞，然後按一下 **[!UICONTROL Continue]**.

1. 按一下 **[!UICONTROL Synchronize]** 以存取您的AEM傳遞。

   如果您的介面中看不到按鈕，請導覽至 **[!UICONTROL Properties]** 按鈕並存取 **[!UICONTROL Advanced]** 標籤。 確保 **[!UICONTROL Content editing mode]** 欄位已設定為 **[!UICONTROL AEM]**，然後輸入您的AEM執行個體詳細資訊 **[!UICONTROL AEM account]** 欄位。

   ![](assets/aem_authoring_8.png)

1. 選取先前在中建立的AEM傳遞 [!DNL Adobe Experience Manager] 並按一下以確認 **[!UICONTROL Ok]**.

1. 您可以直接從插入資產 [!DNL Adobe Experience Manager Assets] 或 [!DNL Adobe Experience Manager Assets Library] 在Adobe Campaign中編輯電子郵件時。 [了解更多](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/overview.html)。

   若要使用您的 **Adobe Experience Manager Assets資料庫**，存取 **[!UICONTROL Properties]** AEM ，並選取 **[!UICONTROL Advanced]** 標籤。 啟用 **[!UICONTROL Use above AEM instance as shared asset library]** 選項。

   ![](assets/aem_authoring_9.png)

1. 確定按一下 **[!UICONTROL Refresh content]** 按鈕，用於修改AEM傳遞。

您的電子郵件現在已準備好傳送給您的對象。
