---
title: 64位元結構描述
description: 瞭解適用於Campaign Standard移轉客戶的Adobe Campaign v8中的64位元結構描述
feature: Technote
role: Admin
exl-id: ab5f01fd-4ad5-46e9-b132-011fe0f7bbd2
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: ab81f6c3-9317-564f-af92-6670a8784294
    internal-label: Technote
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 7%
---
# 64位元結構描述 {#sixty-four-bit-tables}

為了方便從Campaign Standard轉換到Campaign v8，有幾個表格已從32位元變更為64位元。 事實上，Campaign Standard在數個現成可用的綱要中支援64位元的PK，而Campaign v8在大部分綱要中支援32位元的PK。

## 限制

* 這項技術變更僅適用於從Campaign Standard移轉的客戶。
* 結構描述和broadlog延伸不支援64位元。 它將保持在32位元。
* 與傳送給技術使用者的傳遞相關的記錄將無法在Campaign v8中使用。
* 僅支援PostgreSQL。

## 修改的結構描述

以下是變更為64位元及其修改屬性的結構描述清單。

| 結構描述名稱 | 屬性名稱 |
|--- |--- |
| nms:broadLogRcp | ID |
| nms:trackingLogRcp | ID |
| nms:excludeLogRcp | ID |
| nms:broadLogVisitor | ID |
| nms:trackingLogVisitor | ID |
| nms:propositionRcp | interactionId |
| nms:propositionVisitor | interactionId |
| nms:webTrackingLog | ID |
| nms:tmpBroadcast | message-id |
| nms:tmpMarketingPressure | message-id |
| nms:tmpBroadcastExclusion | message-id |
| nms:tmpBroadcastPaper | message-id |
| nms:broadLogAppSubRcp | ID |
| nms:trackingLogAppSubRcp | ID |
| nms:excludeLogAppSubRcp | ID |
| nms:webEvent | broadLogSrc-id， broadLogRemkt-id |
| nms:broadLogMid | mktBroadLogId |
| nms:mirrorPageSearch | remoteMessageId |
