---
title: 傳遞狀態
description: 進一步瞭解傳遞控制面板上可用的狀態
feature: Monitoring, Deliverability
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 3%

---

# 傳遞狀態 {#delivery-statuses}

傳送傳送後，傳送控制面板會顯示狀態，讓您監視傳送是否成功。 可能的狀態會在下節中詳細說明。

![](assets/delivery-status.png)

如需您可以遇到的不同傳送失敗及其解決方法的詳細資訊，請參閱[瞭解傳送失敗](delivery-failures.md)。

**相關主題：**

* [傳送及監視您的電子郵件](send.md)
* [瞭解傳遞失敗](delivery-failures.md)
* [開始使用傳遞能力](about-deliverability.md)

## 傳遞狀態清單 {#list-delivery-statuses}

<table> 
 <thead> 
  <tr> 
   <th> 狀態<br /> </th> 
   <th> 定義與解決方案<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已傳送<br /> </td> 
   <td> 傳遞已正確傳送給訊息提供者（但收件者不一定會收到它）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已忽略<br /> </td> 
   <td> 因為收件者的地址發生錯誤，所以未將傳遞傳送給收件者。 該檔案位於封鎖清單上、已隔離、未提供或重複。<br /> </td> 
  </tr> 
  <tr> 
   <td> 失敗<br /> </td> 
   <td> 例如，由於地址無效或收件匣已滿，傳遞無法連線至收件者。 它也可以連結到個人化區塊的問題，因為它們可能會在結構描述不符合傳遞對應時產生錯誤。 請參閱<a href="delivery-failures.md" target="_blank">瞭解傳遞失敗</a><br /> </td> 
  </tr>
  <tr> 
   <td> 擱置中<br /> </td> 
   <td> 傳遞已準備就緒可供傳送，且將由傳遞伺服器(MTA)處理。 檢視<a href="#pending-status" target="_blank">擱置狀態</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 不適用<br /> </td> 
   <td> 伺服器(MTA)已將傳遞列入考量，但未處理。<br /> </td> 
  </tr>  
  <tr> 
   <td> 傳遞已取消<br /> </td> 
   <td> 操作員已取消傳遞。<br /> </td> 
  </tr> 
  <tr> 
   <td> 服務提供者已將其列入考量<br /> </td> 
   <td> 對於SMS傳遞，SMS服務提供者會收到傳遞。<br />對於電子郵件傳遞，訊息已成功從Campaign轉送至MTA （郵件傳輸代理程式）。</td> 
  </tr> 
  <tr> 
   <td> 已在行動<br />上收到 </td> 
   <td> 收件者在其行動裝置上收到簡訊。<br /> </td> 
  </tr>
  <tr> 
   <td> 已傳送給服務提供者<br /> </td> 
   <td> 傳遞已傳送給SMS服務提供者，但尚未收到。<br />
   </td> 
  </tr> 
  <tr> 
   <td> 已準備<br /> </td> 
   <td> 僅用於外部聯結器（例如行動裝置頻道）的中介狀態。 它遵循'Pending'狀態，而且是會判斷下列狀態的外部聯結器。<br /> </td> 
  </tr> 
 </tbody> 
</table>

若要瞭解如何最佳化Adobe Campaign電子郵件的傳遞能力，請參閱[本節](about-deliverability.md)。 如需傳遞能力的更深入探討，請參閱[Adobe傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant)。

## 擱置狀態 {#pending-status}

確認傳遞後，您可以看到傳遞的狀態為&#x200B;**[!UICONTROL Pending]**。 此狀態表示執行程式正在等待某些資源的可用性。

**[!UICONTROL Pending]**&#x200B;狀態可能首先表示您的傳送已排程且擱置到指定日期。 如需詳細資訊，請參閱[排程傳遞傳送](configure-and-send.md#schedule-delivery-sending)區段。

如果您的傳遞尚未傳送且其狀態仍為&#x200B;**[!UICONTROL Pending]**，則可能是下列結果：

* **同時執行過多行銷活動**

  在&#x200B;**[!UICONTROL NmsOperation_LimitConcurrency]**&#x200B;選項中定義同時行銷活動的限制。 預設值為 10。

  身為「受管理的Cloud Services」使用者，您可以視需要使用Adobe調整此限制。 在[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options.html){target="_blank"}中進一步瞭解選項。

* **資源可用性問題**

  MTA （郵件傳輸代理程式）在處理您的傳遞之前，可能正在等候資源變成可用。

>[!NOTE]
>
>身為Campaign v8受管理的Cloud Services使用者，MTA基礎架構會由Adobe監控和管理。 如果您持續遇到傳送擱置的問題，請聯絡Adobe客戶服務。

**相關主題：**

* [傳送及監視您的電子郵件](send.md#email-monitoring)
* [瞭解傳遞失敗](delivery-failures.md)
* [監視您的Campaign環境](../start/monitor.md#monitor-deliveries)

