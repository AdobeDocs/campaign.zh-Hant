---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 77%
---
# 配送

此結構描述代表傳遞動作或範本。

範本是包含所有必要引數的傳遞範本。 傳遞範本可以從使用者端主控台手動執行，或是在事件發生時執行（從排程器啟動，或從SOAP呼叫以程式設計方式啟動）。

## 方法

| 方法 | 說明 |
| --- | --- |
| [AppendDeliveryPart](sm-delivery-appenddeliverypart.md) | 將部分新增到正在準備的傳遞中。 |
| [BuildForward](sm-delivery-buildforward.md) | 建立 HTML 頁面。 |
| [BuildMirror](sm-delivery-buildmirror.md) | 建立 HTML 鏡像頁面。 |
| [BuildMirrorEx](sm-delivery-buildmirrorex.md) | 建立 HTML 鏡像頁面。 |
| [BuildPreview](sm-delivery-buildpreview.md) | 建立要傳遞的內容預覽或是輸出檔案的某一行的預覽 (在外部模式下)。 |
| [BuildPreviewFromId](sm-delivery-buildpreviewfromid.md) | 建立要傳遞的內容預覽或是輸出檔案的某一行的預覽 (在外部模式下)。 |
| [BuildTargetDataSchema](sm-delivery-buildtargetdataschema.md) |  |
| [CleanupDelivery](sm-delivery-cleanupdeliveries.md) | 指定中間來源伺服器應該刪除某些傳遞。 |
| [CollectLogs](sm-delivery-collectlogs.md) | 為傳遞清單建立包含所有傳遞記錄訊息的表格 |
| [CreateFromModel](sm-delivery-createfrommodel.md) | 從範本 (根據其內部名稱) 建立傳遞。 |
| [DeployTriggerMessageSingle](sm-delivery-deploytriggermessagesingle.md) | 在執行例項上發佈交易式訊息。 如果發佈成功，則傳回true，否則傳回false。 |
| [部署觸發訊息](sm-delivery-deploytriggermessages.md) | 在執行執行個體上發佈選取的交易型訊息 |
| [診斷HTML](sm-delivery-diagnosehtml.md) | 開始 HTML 內容診斷 |
| [分派影像](sm-delivery-dispatchimages.md) | 告知應用程式伺服器傳送影像給中間來源伺服器。 |
| [ExecCommand](sm-delivery-execcommand.md) | 對傳遞執行命令。 |
| [ExecuteJob](sm-delivery-executejob.md) | 針對傳遞執行同步處理。 |
| [FinalizeMidPreparation](sm-delivery-finalizemidpreparation.md) | 完成中間來源模式下的傳遞分析。 |
| [GetDeviceList](sm-delivery-getdevicelist.md) |  |
| [GetDlStatusAndLogs](sm-delivery-getdlstatusandlogs.md) | 從日誌和傳遞狀態中檢索上次的記錄。 |
| [GetFilesToDownload](sm-delivery-getfilestodownload.md) | 傳回伺服器上與傳遞相關聯的檔案清單。 |
| [GetMidBroadLogs](sm-delivery-getmidbroadlogs.md) | 檢索上次在中間來源模式下修改的傳遞記錄。 |
| [GetMidDeliveries](sm-delivery-getmiddeliveries.md) | 檢索上次在中間來源模式下修改的傳遞的狀態。 |
| [GetMidXtkKey](sm-delivery-getmidxtkkey.md) | 傳回中間伺服器的 Xtk 金鑰 |
| [GetMirrorURL](sm-delivery-getmirrorurl.md) | 取得 HTML 鏡像頁面的 URL。 |
| [GetSeedList](sm-delivery-getseedlist.md) |  |
| [HtmlToText](sm-delivery-htmltotext.md) | 將 HTML 內容轉換為純文字 |
| [影像發佈](sm-delivery-imagepublishing.md) | 執行後續處理：將影像移至指定的資料夾，並使其可在線上使用 |
| [InstallTransactionalMessage](sm-delivery-installtransactionalmessage.md) | 在執行執行個體上安裝交易型訊息範本。 |
| [InvalidateDeliveryCache](sm-delivery-invalidatedeliverycache.md) | 必須在訊息準備結束時呼叫，除了中間來源以外 (私人方法)。 |
| [LaunchFCP](sm-delivery-launchfcp.md) | 開始傳遞的校樣複本 |
| [LoadExpandedContents](sm-delivery-loadexpandedcontents.md) | 載入元件清單，以進行相依性關係的預先處理 (個人化區塊、選項、其他指令碼物件等)。 |
| [暫停](sm-delivery-pause.md) | 暫停傳遞。 |
| [播放](sm-delivery-play.md) | 開始傳遞。 |
| [準備](sm-delivery-prepare.md) | 傳遞分析：目標選擇與個人化 |
| [PrepareAndStart](sm-delivery-prepareandstart.md) | 分析傳遞，並在沒有遇到錯誤時立即執行 |
| [PrepareFromId](sm-delivery-preparefromid.md) | 分析傳遞。 |
| [PrepareMessage](sm-delivery-preparemessage.md) | 訊息個人化 |
| [PrepareMessageImpl](sm-delivery-preparemessageimpl.md) | 訊息個人化 |
| [PrepareMultipartRelated](sm-delivery-preparemultipartrelated.md) | 儲存影像，以包含在資料庫內的電子郵件中 |
| [PrepareNotification](sm-delivery-preparenotification.md) | 分析正新增到現有傳遞動作的通知 |
| [PrepareProof](sm-delivery-prepareproof.md) | 考量到產生校樣的傳遞分析 |
| [PrepareTarget](sm-delivery-preparetarget.md) | 傳遞目標計數和仲裁 |
| [PrepareTargetImpl](sm-delivery-preparetargetimpl.md) | 傳遞目標計數和仲裁 |
| [PreviewExtraction](sm-delivery-previewextraction.md) | 擷取檔案預覽 |
| [優先順序記錄檔](sm-delivery-prioritizelogs.md) | 優先處理傳遞記錄，以獲得傳遞清單 |
| [PrioritizeTarget](sm-delivery-prioritizetarget.md) | 傳遞目標仲裁 |
| [佇列通知](sm-delivery-queuenotification.md) | 請求將參照傳遞範本的通知排入佇列。 |
| [重新計算統計資料](sm-delivery-recomputestats.md) | 重新計算傳遞動作的傳遞和追蹤統計資料。 |
| [SaveUrlInfo](sm-delivery-saveurlinfo.md) | 將此傳遞的 URL 儲存為 URL 範本。 |
| [停止](sm-delivery-stop.md) | 停止正在進行的傳遞。 |
| [StoreMirrorPageInfo](sm-delivery-storemirrorpageinfo.md) | 新增資訊以針對一組傳遞部分產生鏡像頁面。 |
| [StoreMirrorPageInfoEx](sm-delivery-storemirrorpageinfoex.md) | 新增資訊以針對一組傳遞部分產生鏡像頁面。 |
| [SubmitDelivery](sm-delivery-submitdelivery.md) | 從情境 (根據其內部名稱) 建立及提交傳遞。 |
| [SubmitDeliveryById](sm-delivery-submitdeliverybyid.md) | 從情境 (由其內部名稱識別) 建立及提交傳遞。 |
| [送出工作](sm-delivery-submitjob.md) | 針對傳遞提交工作以進行非同步處理 |
| [SubmitMidSourcing](sm-delivery-submitmidsourcing.md) | 在中間來源模式下提交傳遞。 |
| [SubmitNotification](sm-delivery-submitnotification.md) | 從情境建立並提交通知。 |
| [UpdateBroadLogs](sm-delivery-updatebroadlogs.md) | 更新傳遞記錄的狀態、執行錯誤處理並更新傳遞計數器。 |
| [UpdateCachedDelivery](sm-delivery-updatecacheddelivery.md) | 每次在記憶體中修改傳遞時都必須呼叫，好讓其他執行緒可以存取最新版本 (私用方法)。 |
| [UpdateImageConfig](sm-delivery-updateimageconfig.md) | 修改 imageConfig 節點，將已在伺服器上的影像列入考量。 |
| [ValidateWavesDefinition](sm-delivery-validatewavesdefinition.md) | 檢查用於波段定義的一致性資訊。 |

## 泛型方法

| 方法 | 說明 |
| --- | --- |
| [建立](f-create.md) | 建立與指定結構描述對應的新實體。 |
| [載入](f-load.md) | 載入並傳回與指定結構描述和索引鍵對應的實體。 |
| [儲存](m-entity-save.md) | 將實體儲存在資料庫中。 |
