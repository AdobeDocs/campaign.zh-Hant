---
title: 增強式安全性附加元件
description: 開始使用Campaign Enhanced安全性附加元件
feature: Configuration
role: Developer
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: cec935c2c73e3df4d2e03d54305004df9bd2655e
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 1%

---


# 增強式安全性附加元件 {#enhanced-security}

若要讓您的網路連線更安全，並為您的資源提供更優異的安全性， [!DNL Adobe Campaign] 提供新的 **增強式安全性** 附加元件。

此附加元件目前包含兩個生態系統功能：

* [安全的CMK整合](#secure-cmk-integration)

* [安全的VPN通道](#secure-vpn-tunneling)

## 安全的CMK整合 {#secure-cmk-integration}

**安全客戶自控金鑰(CMK)整合** 可讓您透過AWS帳戶，使用自己的金鑰加密執行個體和資料<!--instead of Adobe-owned keys-->. 透過讓您負責產生和管理加密金鑰，此容量可讓您對金鑰擁有更多控制權，包括撤銷金鑰。

>[!CAUTION]
>
>如果您撤銷金鑰，必須注意會造成哪些影響。 [了解更多](#cmk-callouts)

若要啟用此功能，請遵循下列步驟：

1. 確定您有 [AWS](https://aws.amazon.com/){target="_blank"} 帳戶。

1. 使用AWS金鑰管理服務(KMS)產生具有自動循環的金鑰。 [瞭解如何](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}

1. 將Adobe至您的AWS帳戶套用提供給您的原則，以授予對資源的存取權。 [瞭解更多](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"} <!--link TBC-->

1. 與共用您的Amazon資源名稱（金鑰ARN） [!DNL Adobe Campaign]. 若要這麼做，請聯絡您的Adobe代表。 <!--or Adobe transition manager?-->

1. 建立並測試Amazon EventBridge規則，以啟用依Adobe監視金鑰&#x200B;。 [了解更多](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}

## 安全的VPN通道 {#secure-vpn-tunneling}

**安全的虛擬私人網路(VPN)通道** 是一種站台對站台VPN，可透過私人網路為傳輸中的資料(從您的設施到 [!DNL Adobe Campaign] 執行個體。

<!--As it connects two networks together, it is a site-to-site VPN.-->

為了確保高可用性(HA)，它使用兩個通道來避免在一個通道發生問題時造成任何中斷

支援三種使用案例：

* FDA over VPN<!--to access your on-premise database from the Campaign instance over VPN-->

* 執行個體從大型使用者端透過VPN登入

* 透過VPN執行個體SFTP存取

>[!CAUTION]
>
>僅支援內部部署資料庫和符合AWS的VPN裝置。 [了解更多](#vpn-callouts)

為確保正確使用此功能，請遵循以下准則：

* 根據Adobe端VPN設定來設定您的端VPN。

* 讓兩個通道都保持在HA上。

* 監視您的側邊通道。

* 您必須是通道的起始者，並在通道關閉時對齊以重新啟動連線。

* 在端點設定重試機制，以防連線失敗。

## 護欄 {#callouts}

以下列出與增強式安全性功能相關的一些護欄和限制。

* 請確定您的所有Secure CMK整合/Secure VPN通道使用案例運作正常。

<!--* Adobe shall reach out to you or your technical team if any issue is found on your side.

* Currently, when using Enhanced security features, any communication with Adobe must be performed manually via email.-->

* Adobe將監控：

   * 您的執行個體可用性，如果金鑰無法使用，則繼續發出警報。

   * VPN通道，並在出現任何問題時繼續發出警報。

### 安全的CMK整合護欄 {#cmk-callouts}

* Adobe不提供AWS帳戶。 您必須擁有自己的AWS帳戶，並將其設定為產生並與Adobe共用您的金鑰。

* 僅限 [AWS金鑰管理服務](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} 支援(KMS)金鑰。 不能使用KMS以外的客戶產生的金鑰&#x200B;。

* 首次設定將會涉及部分停機時間。&#x200B;URL停機時間長度將取決於資料庫的大小。

* 您擁有和維護金鑰時，如果金鑰發生任何變更，您必須聯絡Adobe&#x200B;。

* 您可以使用以下方式稽核您的金鑰 [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} 並視需要加以撤銷&#x200B;。

* 如果您撤銷、停用或刪除金鑰，則在您還原對應的動作之前，將無法存取加密的資源和執行個體。

  >[!CAUTION]
  >
  >如果您停用金鑰，並且沒有在7天內還原此動作，則您的資料庫只能從備份復原。
  >
  >如果您刪除金鑰但未在30天內還原此動作，則您的所有資料將會永久刪除並遺失&#x200B;。

### 安全的VPN通道護欄 {#vpn-callouts}

* 目前僅支援內部部署資料庫，例如<!--Richa to check the list with PM-->：

   * MySQL
   * netezza 
   * oracle 
   * SAP HANA 
   * SQL Server 
   * Sybase 
   * teradata 
   * 透過 HiveSQL 提供的 Hadoop

* 僅支援與AWS相容的VPN裝置。 相容裝置的清單位於 [此頁面](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}<!--check which list should be communicated-->.

* 不支援第三方或外部廠商的VPN連線。

* 不包括Adobe管理的其他VPN到私有雲端資料庫。
