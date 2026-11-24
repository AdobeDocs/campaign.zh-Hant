---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 3%
---
# 登入

開啟工作階段

```text
[ String sessionToken, sessionInfo sessionInfo, String securityToken ] = Logon ( String login, String password, XML parameters )
```

## 參數

**登入**&#x200B;使用者帳戶

與使用者登入關聯的&#x200B;**密碼**&#x200B;密碼

**引數**&#x200B;連線設定

## 傳回值

**sessionToken**&#x200B;工作階段權杖

**sessionInfo**&#x200B;工作階段引數

**securityToken**&#x200B;安全性權杖

## 帳戶鎖定機制設定

登入() API內有帳戶鎖定機制。 這可防止在指定時間範圍內連續嘗試登入失敗的特定次數後，再出現任何登入嘗試。

有四個選項可用來設定鎖定機制：

* **XtkSecurity\_max\_Unsuccessul\_Attempts\_Allowed**：在指定期間內封鎖金鑰的最大失敗嘗試。 預設值為3。
* **XtkSecurity\_Initial\_Ban\_Duration**：首次禁止金鑰的持續時間。 預設持續時間為5分鐘。
* **XtkSecurity\_Max\_Ban\_Duration**：可禁止金鑰的最長持續時間。
* **XtkSecurity\_Examine\_Window**：追蹤禁止無效金鑰失敗登入嘗試次數的時間視窗。 預設持續時間為10分鐘。

例如，如果有人在10分鐘內嘗試3次不成功，則他的金鑰將會在5分鐘內遭到封鎖。

## 功能

**結構描述：** [xtk:session](s-xtk-session.md)

**靜態：**

是
