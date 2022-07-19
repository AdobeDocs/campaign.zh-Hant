---
title: 管理 Campaign 的隱私權請求
description: 了解如何在 Campaign 管理隱私權請求
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 0f81d318-dbfd-45c8-b391-b1d14d23e9c8
source-git-commit: 41a213eea434b3fc6ee8b3ea3c29d4364f9c9761
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 71%

---

# 管理 Campaign 的隱私權請求 {#privacy}

根據您的業務性質及其運營的管轄區，您的資料操作可能受法律隱私法規的約束。 這些法規通常授予您的客戶請求訪問您從他們那裡收集的資料的權利，並授予您請求刪除儲存的資料的權利。 這些客戶對其個人資料的請求在文檔中稱為「隱私請求」。

Adobe 為資料控制方提供工具，可針對儲存在 Campaign 的資料建立並處理隱私權請求。然而，資料控制方應負責確認提出請求之資料主體身份，並確認傳回給請求者的資料與資料主體有關。若需進一步資訊了解個人資料及管理資料的不同實體，請參考 [Adobe Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hant#personal-data){target=&quot;_blank&quot;}。


要在市場活動中管理隱私請求，必須首先 [定義命名空間](#namespaces)。 然後，您就可以建立和管理隱私請求。 要執行隱私請求，請使用 **AdobePrivacy Service** 整合。 從Privacy Service推送到所有Adobe Experience Cloud解決方案的隱私請求由活動通過專用工作流自動處理。 [了解更多](#create-privacy-request)

![](../assets/do-not-localize/speech.png) 若需了解 **存取權限** 與 **被遺忘的權利** (刪除請求)，請參閱 [Adobe Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=zh-Hant#right-access-forgotten){target=&quot;_blank&quot;}


>[!NOTE]
>
>此功能可從 Campaign v8.3 開始使用。若要檢查您的版本，請參閱[此章節](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

## 定義命名空間 {#namespaces}

在建立隱私請求之前，您必須 **定義命名空間** 的下界。 命名空間是用於標識資料庫中資料主題的鍵。

>[!NOTE]
>
>瞭解有關中標識命名空間的詳細資訊 [Adobe Experience Platform文檔](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=zh-Hant){target=&quot;_blank&quot;}。

目前的 Adobe Campaign 不支援從 Experience Platform 身分識別命名空間服務匯入命名空間。 因此，在身分命名空間服務上建立命名空間後，必須在 Adobe Campaign 介面上手動建立對應的命名空間。 請依照下列步驟以執行此操作。

<!--v7?
Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.
-->

1. 在[身分識別命名空間服務](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace)上建立命名空間{target=&quot;_blank&quot;}。

1. 當 [列出標識命名空間](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces){target=&quot;_blank&quot;}可用於您的組織，您將獲得以下詳細資訊，例如：

   ```
   {
           "updateTime": 1632903236731,
           "code": "lumanamespace",
           "status": "ACTIVE",
           "description": "new namespace for Luma privacy requests",
           "id": 10998717,
           "createTime": 1632903236731,
           "idType": "Email",
           "namespaceType": "Custom",
           "name": "Luma Namespace",
           "custom": true
   }
   ```

1. 在Adobe Campaign，瀏覽 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]** 選擇 **[!UICONTROL New]**。

   ![](assets/privacy-namespaces-new.png)

1. 輸入 **[!UICONTROL Label]**。

1. 填寫新命名空間的詳細資訊，以符合在識別命名空間服務上建立的命名空間：

   * 這樣 **[!UICONTROL AEC Namespace ID]** 必須與&quot;id&quot;屬性匹配
   * 這樣 **[!UICONTROL Internal name]** 必須與&quot;code&quot;屬性匹配
   * 這樣 **[!UICONTROL Reconciliation key]** 必須與「idType」屬性匹配

   ![](assets/privacy-namespaces-details.png)

   這是將用於識別 Adobe Campaign 資料庫中資料主體的欄位&#x200B;**[!UICONTROL Reconciliation key]**。

1. 選擇目標對應<!--(**[!UICONTROL Recipients]**, **[!UICONTROL Real time event]** or **[!UICONTROL Subscriptions]**)-->，指定在 Adobe Campaign 中命名空間的協調方式。

   >[!NOTE]
   >
   >如果需要使用多個目標映射，請為每個目標映射建立一個命名空間。

1. 儲存您的變更。

您現在可以根據新的命名空間來建立隱私權要求。如果使用多個命名空間，請為每個命名空間相同的協調值建立一個隱私權請求。

## 建立隱私權請求 {#create-privacy-request}

的 **[!DNL Adobe Experience Platform Privacy Service]** 整合允許您通過單個JSON API調用在多解決方案上下文中自動執行隱私請求。 Adobe Campaign自動處理通過專用工作流從Privacy Service推送的請求。

請參閱[Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hant){target=&quot;_blank&quot;} 文件，瞭解如何從隱私權核心服務建立隱私權要求。

每個 **[!DNL Privacy Service]**  作業根據使用的命名空間數被拆分為Adobe Campaign的多個隱私請求，一個請求對應於一個命名空間。

此外，一個作業可在多個執行個體上執行。因此，會針對一個作業建立多個檔案。例如，如果要求有兩個命名空間，且在三個執行個體上執行，則總共會傳送六個檔案。每個命名空間和執行個體會有一個檔案。

檔案名稱的模式是：`<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**：Campaign 執行個體名稱
* **NamespaceId**：所使用命名空間的身份識別服務命名空間 ID
* **調解金鑰**：編碼調解金鑰

>[!CAUTION]
>
>要使用自訂命名空間類型提交請求，請善用 [JSON 方法](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=zh-Hant#json){target=&quot;_blank&quot;}，並將 namespaceId 加入請求，或使用 [API 呼叫](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/privacy-jobs.html?lang=zh-Hant#access-delete){target=&quot;_blank&quot;}發出請求。
>
>僅使用[隱私權使用者介面](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=zh-Hant#request-builder){target=&quot;_blank&quot;}，使用標準命名空間類型提交請求。

### 處理請求時搜尋的表格 {#list-of-tables}

執行刪除或存取隱私權要求時，Adobe Campaign 會根據所有包含收件者表格連結 (自有類型) 之表格中的&#x200B;**[!UICONTROL Reconciliation value]**，以搜尋所有資料主體的資料。

執行隱私請求時考慮的內置表清單包括：

* 收件者 (recipient)
* 收件者傳遞記錄 (broadLogRcp)
* 收件者追蹤記錄 (trackingLogRcp)
* 封存的事件傳遞記錄 (broadLogEventHisto)
* 收件者清單內容 (rcpGrpRel)
* 訪客優惠方案主張 (propositionVisitor)
* 訪客 (visitor)
* 訂閱歷史記錄 (subHisto)
* 訂閱 (subscription)
* 收件者優惠方案主張 (propositionRcp)

如果您建立的自訂資源具有收件者表格 (自有類型) 的連結，也會將這些帳戶列入考量。例如，如果您有連結至收件者表格的交易表格和連結至交易表格的交易詳細資料，則會同時將這些帳戶列入考量。
<!--
>[!CAUTION]
>
>If you perform Privacy batch requests using profile deletion workflows, please take into consideration the following remarks:
>* Profile deletion via workflows do not process children tables.
>* You need to handle the deletion for all the children tables.
>* Adobe recommends that you create an ETL workflow that add the lines to delete in the Privacy Access table and let the **[!UICONTROL Delete privacy requests data]** workflow perform the deletion. We suggest to limit to 200 profiles per day to delete for performance reasons.-->

### 隱私權請求狀態 {#privacy-request-statuses}

您可以在Adobe Campaign的隱私請求的不同狀態下找到以下狀態以及如何解釋它們：

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**：進行中，工作流程尚未處理要求。
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**：工作流程正在處理要求。
* **[!UICONTROL Delete pending]**：工作流程已識別所有要刪除的收件者資料。
* **[!UICONTROL Delete in progress]**：工作流程正在處理刪除。
* **[!UICONTROL Complete]**：要求處理已完成，並未發生錯誤。
* **[!UICONTROL Error]**：工作流程發生錯誤。原因會顯示在 **[!UICONTROL Request status]** 欄的「隱私權要求」清單中。例如，**[!UICONTROL Error data not found]** 表示在資料庫中找不到與資料主體 **[!UICONTROL Reconciliation value]** 相符的收件者資料。

Campaign Classic v7 文件中的&#x200B;**相關主題：**

* [隱私權與同意](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hant){target=&quot;_blank&quot;}

* [隱私權管理快速入門](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=zh-Hant){target=&quot;_blank&quot;}

* [隱私權管理法規](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=zh-Hant#privacy-management-regulations){target=&quot;_blank&quot;} (GDPR、CCPA、PDPA 和 LGPD)

* [選擇退出個人資訊銷售](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests/privacy-requests-ccpa.html?lang=zh-Hant){target=&quot;_blank&quot;} (特定於 CCPA)
