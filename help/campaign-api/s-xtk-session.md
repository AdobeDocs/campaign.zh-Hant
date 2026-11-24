---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 73%
---
# session

應用程式伺服器的工作階段

## 方法

| 方法 | 說明 |
| --- | --- |
| [ApplyDuplicateRules](sm-session-applyduplicaterules.md) | 將複製設定 (包括預設值) 套用至指定的文件 |
| [BearerTokenLogon](sm-session-bearertokenlogon.md) | 連線權杖 |
| [變更密碼](sm-session-changepassword.md) | 變更目前密碼 |
| [DeleteCollection](sm-session-deletecollection.md) | 根據條件刪除實體清單 |
| [差異](sm-session-diff.md) | 傳回文件的目前版本和原始版本。 |
| [重複](sm-session-duplicate.md) | 從來源文件建立新文件 |
| [複製到](sm-session-duplicateto.md) | 將新文件從來源文件複製到給定資料夾 |
| [DuplicateWithMappingId](sm-session-duplicatewithmappingid.md) | 使用 ID 對應，從來源文件複製新文件 |
| [加密](sm-session-encrypt.md) | 使用執行個體金鑰對字元字串進行加密。 |
| [EncryptServerPassword](sm-session-encryptserverpassword.md) | 使用伺服器金鑰對字元字串進行加密。 |
| [FormatDataPolicy](sm-session-formatdatapolicy.md) | 根據作為引數傳遞的資料原則，將轉換套用至字元字串。 在失敗的情況下保留字串不變。 |
| [GetActiveApplicationMenus](sm-session-getactiveapplicationmenus.md) | 傳回包含為目前登入啟用的應用程式選單的文件 |
| [GetCnxInfo](sm-session-getcnxinfo.md) | 從目前的連線中復原資訊。 |
| [GetDefaultEntity](sm-session-getdefaultentity.md) | 傳回包含空白實體及其預設值的文件 |
| [GetDirtyCacheEntities](sm-session-getdirtycacheentities.md) | 傳回骯髒的已快取實體 |
| [GetEntityIfMoreRecent](sm-session-getentityifmorerecent.md) | 如果實體的 MD5 金鑰與作為參數給定的金鑰不同，則載入實體 |
| [GetImages](sm-session-getimages.md) | 載入影像清單 |
| [GetNewIds](sm-session-getnewids.md) | 收集資料庫的內部索引鍵識別碼清單。 |
| [GetNewIdsEx](sm-session-getnewidsex.md) | 在給定序列名稱的情況下，從資料庫中取得唯一識別碼的清單。 |
| [GetOption](sm-session-getoption.md) | 傳回儲存在資料庫中的選項值。 |
| [GetPkList](sm-session-getpklist.md) | 取得執行個體識別碼的清單 |
| [GetServerTime](sm-session-getservertime.md) | 傳回伺服器日期和時間 |
| [GetUserInfo](sm-session-getuserinfo.md) | 有關目前操作者的資訊 |
| [雜湊密碼](sm-session-hashpassword.md) | 使用伺服器金鑰對密碼進行雜湊處理。 |
| [ImportCollection](sm-session-importcollection.md) | 使用匯入更新實體清單 |
| [KillSession](sm-session-killsession.md) | 關閉指定的工作階段 |
| [載入](sm-session-load.md) | 載入實體 |
| [LoadAsText](sm-session-loadastext.md) | 以文字形式檢索實體內容 |
| [LoadIfExists](sm-session-loadifexists.md) | 載入實體 (如果存在) |
| [登出](sm-session-logoff.md) | 關閉目前工作階段 |
| [登入](sm-session-logon.md) | 開啟工作階段 |
| [NewInstance](sm-session-newinstance.md) | 建立新文件，已預先初始化但未儲存 |
| [移除](sm-session-remove.md) | 刪除實體 |
| [伺服器關機](sm-session-servershutdown.md) | 請求伺服器關機 |
| [SetDefaultValues](sm-session-setdefaultvalues.md) | 在預設情況下根據 xpath 修正值 |
| [SetDefaults](sm-session-setdefaults.md) | 設定預設值 |
| [TestCnx](sm-session-testcnx.md) | 測試連線。 |
| [寫入](sm-session-write.md) | 更新實體 |
| [WriteCollection](sm-session-writecollection.md) | 更新實體清單 |

## 泛型方法

| 方法 | 說明 |
| --- | --- |
| [建立](f-create.md) | 建立與指定結構描述對應的新實體。 |
| [載入](f-load.md) | 載入並傳回與指定結構描述和索引鍵對應的實體。 |
| [儲存](m-entity-save.md) | 將實體儲存在資料庫中。 |
