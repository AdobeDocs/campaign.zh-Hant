---
title: 使用Adobe Campaign設定電子郵件
description: 瞭解如何在Adobe Campaign中設定電子郵件。
feature: Email
role: User
level: Beginner
exl-id: 36033255-1e75-41c1-9816-126777f7330a
source-git-commit: e0dbeb7402a46f76a26c28dd226bc069d52f2609
workflow-type: tm+mt
source-wordcount: '1188'
ht-degree: 10%

---

# 設定並傳送傳遞 {#configure-delivery}

存取傳遞參數以設定更多設定，並定義如何傳送訊息。 您可以定義傳遞[優先順序](#delivery-priority)、設定[波段](#sending-using-multiple-waves)，並測試您的傳遞傳送。 完成此設定後，您可以確認傳送，如[此區段](#confirm-delivery)所述。 然後立即傳送訊息，或根據傳遞[排程](#schedule-delivery-sending)傳送訊息。

## 設定其他引數 {#delivery-additional-parameters}

在傳送傳遞之前，您可以透過&#x200B;**[!UICONTROL Delivery]**&#x200B;索引標籤，在傳遞屬性中定義傳送引數。

![](assets/delivery-properties-delivery.png)

### 傳遞優先順序 {#delivery-priority}

使用&#x200B;**[!UICONTROL Delivery priority]**&#x200B;選項，透過將傳遞的優先順序等級從&#x200B;**[!UICONTROL Very low]**&#x200B;設定為&#x200B;**[!UICONTROL Very high]** （預設值為&#x200B;**[!UICONTROL Normal]**）來變更傳遞的傳送順序。

### 批次數量 {#delivery-batch-quantity}

使用&#x200B;**[!UICONTROL Message batch quantity]**&#x200B;選項定義在同一XML傳遞套件中分組的訊息數目。 如果引數設為0，訊息會自動分組。 封裝大小由計算`<delivery size>/1024`定義，每個封裝至少有8個和256個訊息。

>[!IMPORTANT]
>
>當透過複製現有傳遞建立傳遞時，此引數會重設。

### 測試您的傳送傳送

使用&#x200B;**[!UICONTROL Test SMTP delivery]**&#x200B;選項以測試透過SMTP的傳送。 處理傳遞直到連線到 SMTP 伺服器，但不傳送：對於傳遞的每個收件者，Campaign 會連線到 SMTP 提供者伺服器，執行 SMTP RCPT TO 命令，並在 SMTP DATA 命令之前關閉連線。

>[!NOTE]
>
>* 此選項不得在中間來源中設定。
>
>* 在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/additional-configurations/configure-delivery-settings.html#smtp-relay){target="_blank"}中進一步瞭解SMTP伺服器組態。

## 使用多個波段傳送 {#sending-using-multiple-waves}

若要平衡負載，您可以將傳送劃分為幾個批次。 設定批次數量及其相對於整個傳送的比例。

### 啟用波段 {#enable-waves}

若要定義波段，請遵循下列步驟：

1. 開啟傳遞屬性並瀏覽至&#x200B;**[!UICONTROL Delivery]**&#x200B;標籤。
1. 啟用&#x200B;**[!UICONTROL Send using multiple waves]**&#x200B;選項，然後按一下&#x200B;**[!UICONTROL Define waves...]**&#x200B;連結。

   ![](assets/delivery-define-waves.png)

### 設定波段 {#config-waves}

>[!NOTE]
>
>您只能定義兩個連續波段之間的大小和延遲。 無法設定每個波次的收件者選取條件。

您可以定義每個波段的大小，或將它們新增到行事曆中。

* **定義每個波段的大小**。 例如，如果您在對應欄位中輸入&#x200B;**[!UICONTROL 30%]**，則每個波段將代表傳遞中所包含訊息的30%，惟最後一個波段除外，後者將代表訊息的10%。

  在&#x200B;**[!UICONTROL Period]**&#x200B;欄位中，指定兩個連續波段開始之間的延遲。 例如，如果您輸入&#x200B;**[!UICONTROL 2d]**，第一個波段會立即開始，第二個波段會在兩天內開始，第三個波段會在四天內開始，依此類推。

  ![](assets/delivery-waves-size.png)

* **定義傳送每個波次的行事曆**。  例如，第一個波段代表傳遞中包含之訊息總數的25%，將立即開始。 接下來的兩個批次會完成傳遞，並設定為每六小時開始一次。

  在&#x200B;**[!UICONTROL Start]**&#x200B;欄中，指定兩個連續波段開始之間的延遲。 在&#x200B;**[!UICONTROL Size]**&#x200B;欄中輸入固定數字或百分比。

  ![](assets/delivery-waves-calendar.png)

### 波段排程檢查 {#check-waves}

特定型別規則&#x200B;**[!UICONTROL Wave scheduling check]**&#x200B;可確保最後一個波段是在傳遞有效性限制之前計畫。 在傳遞屬性的&#x200B;**[!UICONTROL Typology]**&#x200B;索引標籤中設定的行銷活動型別及其規則會顯示在[本區段](../../automation/campaign-opt/campaign-typologies.md#typology-rules)<!--ref TBC-->中。

>[!IMPORTANT]
>
>* 請確定最後一個批次沒有超過在&#x200B;**[!UICONTROL Validity]**&#x200B;索引標籤中定義的傳送期限。 否則，部分訊息可能不會傳送。 在[本節](delivery-failures.md#valid-period)中進一步瞭解傳遞的有效期。
>
>* 在設定最後一個波段時，您也必須設定足夠的重試時間。 在[本節](delivery-failures.md#retries)中進一步瞭解重試。

### 監視波段 {#monitor-waves}

若要監視您的傳送，請瀏覽至傳送記錄檔。 檢視[此頁面](send.md)

您可以看到已在已處理波段（**[!UICONTROL Sent]**&#x200B;狀態）中傳送的傳遞，以及將在剩餘波段（**[!UICONTROL Pending]**&#x200B;狀態）中傳送的傳遞。


### 波段範例 {#samples-waves}

以下兩個範例是使用多個波段的最常見使用案例。

* **在啟動程式期間**

  使用新平台傳送電子郵件時，網際網路服務提供者(ISP)會懷疑無法辨識的IP位址。 如果突然傳送大量電子郵件，ISP通常會將其標籤為垃圾郵件。

  為避免被標籤為垃圾訊息，您可以逐步增加使用波段傳送的數量。 這應該可以確保啟動階段的順利發展，並且讓您降低無效的位址的整體比率。

  若要這麼做，請使用&#x200B;**[!UICONTROL Schedule waves according to a calendar]**&#x200B;選項。 例如，將第一個波段設為10%，將第二個波段設為15%，以此類推。

  ![](assets/delivery-waves-ex-ramp-up.png)

* **具有客服中心的行銷活動**

  透過電話管理忠誠度行銷活動時，貴組織處理聯絡訂閱者之通話次數的能力有限。

  使用波段時，您可以將訊息數量限製為每天20則，例如考量客服中心的每日處理能力。

  若要這麼做，請選取&#x200B;**[!UICONTROL Schedule multiple waves of the same size]**&#x200B;選項。 輸入&#x200B;**[!UICONTROL 20]**&#x200B;作為波段大小，並在&#x200B;**[!UICONTROL Period]**&#x200B;欄位中輸入&#x200B;**[!UICONTROL 1d]**。

  ![](assets/delivery-waves-ex-call-center.png)

## 確認傳遞 {#confirm-delivery}

當傳遞已設定好並準備好傳送時，在確認傳送之前，請確定您已執行傳遞分析。

請依照下列步驟以執行此操作。

1. 按一下&#x200B;**[!UICONTROL Send]**，選取所需的動作。

   * 若要立即傳送傳遞，請選取&#x200B;**[!UICONTROL Deliver as soon as possible]**。
   * 若要排程傳送至之後的日期，請選取&#x200B;**[!UICONTROL Postpone the delivery]**。 [了解更多](#schedule-delivery-sending)

1. 按一下 **[!UICONTROL Analyze]**。如需詳細資訊，請參閱[本節](delivery-analysis.md)。

   ![](assets/delivery-send-analyze.png)

1. 完成後，按一下&#x200B;**[!UICONTROL Confirm delivery]**&#x200B;以啟動訊息的傳遞。

   ![](assets/delivery-send-confirm.png)

1. 您可以關閉傳遞精靈，並從&#x200B;**[!UICONTROL Delivery]**&#x200B;索引標籤追蹤傳遞的執行，可透過此傳遞的詳細資訊或傳遞清單存取。

   如需詳細資訊，請參閱以下章節：

   * [監視傳遞](send.md)
   * [瞭解傳遞故障](delivery-failures.md)

<!--About message tracking-->

## 排程傳遞傳送 {#schedule-delivery-sending}

為了排程傳遞，管理銷售壓力以及避免過度行銷，您可以推延郵件的傳遞。

1. 按一下&#x200B;**[!UICONTROL Send]**&#x200B;按鈕並選取&#x200B;**[!UICONTROL Postpone delivery]**&#x200B;選項。

1. 在&#x200B;**[!UICONTROL Contact date]**&#x200B;欄位中指定開始日期。

   ![](assets/delivery-send-postpone.png)

1. 開始傳遞分析並確認傳遞傳送。 但是，要到&#x200B;**[!UICONTROL Contact date]**&#x200B;欄位中指定的日期才會開始傳送傳遞。

   >[!IMPORTANT]
   >
   >開始分析後，您定義的聯絡日期即已固定。 如果您修改此日期，則必須重新啟動分析，以便將您的修改納入考量。

   ![](assets/delivery-send-scheduled.png)

在傳遞清單中，傳遞會以&#x200B;**[!UICONTROL Pending]**&#x200B;狀態出現。

您也可以透過傳遞的&#x200B;**[!UICONTROL Scheduling]**&#x200B;按鈕設定上游。

![](assets/delivery-scheduling-button.png)

這可讓您將傳送延遲到較晚日期，或將傳送儲存在臨時行事曆中。

* **[!UICONTROL Schedule delivery (no automatic execution)]**&#x200B;選項可讓您排程傳遞的臨時分析。

  儲存此設定時，傳遞會變更為&#x200B;**[!UICONTROL Targeting pending]**&#x200B;狀態。 分析將會在指定的日期啟動。

* **[!UICONTROL Schedule delivery (automatic execution on planned date)]**&#x200B;選項可讓您指定傳送日期。

  按一下&#x200B;**[!UICONTROL Send]**&#x200B;並選取&#x200B;**[!UICONTROL Postpone delivery]**，然後啟動分析並確認傳遞。 分析完成後，傳遞目標已準備就緒，訊息將於指定日期自動傳送。

日期和時間會以目前運運算元的時區表示。 位於連絡人日期輸入欄位下方的&#x200B;**[!UICONTROL Time zone]**&#x200B;下拉式清單可讓您自動將輸入的日期和時間轉換為選取的時區。

例如，如果您排程在倫敦時間8點自動執行傳遞，則時間會自動轉換為所選的時區：

![](assets/delivery-schedule-time-zone.png)

<!--
## Adjust delivery failure management {#delivery-failure-management}

### Configure retries {#configure-retries}

Temporarily undelivered messages due to a **Soft** or **Ignored** error are subject to an automatic retry. The delivery failure types and reasons are presented in this [section](../../delivery/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

>[!IMPORTANT]
>
>For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the retry settings in the delivery are no longer used by Campaign. Soft bounce retries and the length of time between them are determined by the Enhanced MTA based on the type and severity of the bounce responses coming back from the message's email domain.

For on-premise installations and hosted/hybrid installations using the legacy Campaign MTA, the central section of the **[!UICONTROL Delivery]** tab for delivery parameters indicates how many retries should be performed the day after the delivery and the minimum delay between retries.

![](assets/s_ncs_user_wizard_retry_param.png)

By default, five retries are scheduled for the first day of the delivery with a minimum interval of one hour spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Validity]** tab (see [Defining validity period](#defining-validity-period)).

### Define the validity period {#define-validity-period}

When the delivery has been launched, the messages (and any retries) can be sent until the delivery deadline. This is indicated in the delivery properties, via the **[!UICONTROL Validity]** tab.

![](assets/s_ncs_user_email_del_valid_period.png)

* The **[!UICONTROL Delivery duration]** field lets you enter the limit for global delivery retries. This means that Adobe Campaign sends the messages beginning on the start date, and then, for messages returning an error only, regular, configurable retries are performed until the validity limit is reached.

  You can also choose to specify dates. To do this, select **[!UICONTROL Explicitly set validity dates]**. In this case, the delivery and validity limit dates also let you specify the time. The current time is used by default, but you can modify this directly in the input field.

  >[!IMPORTANT]
  >
  >For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the **[!UICONTROL Delivery duration]** setting in your Campaign email deliveries will be used only if set to **3.5 days or less**. If you define a value higher than 3.5 days, it will not be taken into account.

* **Validity limit of resources**: The **[!UICONTROL Validity limit]** field is used for uploaded resources, mainly for the mirror page and images. The resources on this page are valid for a limited time (to save disk space).

  The values in this field can be expressed in the units listed in [this section](../../platform/using/adobe-campaign-workspace.md#default-units).
-->
