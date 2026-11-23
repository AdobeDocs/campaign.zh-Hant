---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 57%
---
# 工作

在應用程式伺服器上執行的批次工作

## 方法

| 方法 | 說明 |
| --- | --- |
| [取消](sm-job-cancel.md) | 取消工作 |
| [CheckIfJobInProcess](sm-job-checkifjobinprocess.md) | 檢查工作是否仍在執行 |
| [執行](sm-job-execute.md) | 同步執行工作 (在此模式下，進度資訊和取消無法使用)。 |
| [檔案存在](sm-job-filesexist.md) | 檢查檔案是否已存在於伺服器上 (作為檔案或在資源表中)。 |
| [GetJobsInProcess](sm-job-getjobsinprocess.md) | 傳回目前正在執行的非外部工作 |
| [GetStatus](sm-job-getstatus.md) | 取得工作處理進度資訊。 警告：此API不保證會傳回唯一記錄專案清單（呼叫者必須使用其ID刪除重複專案）。 |
| [HasWarning](sm-job-haswarning.md) | 查詢是否已為此工作產生警告或錯誤 |
| [暫停](sm-job-pause.md) | 暫停工作 |
| [提交](sm-job-submit.md) | 提交工作以進行非同步處理 |
| [SubmitFromModel](sm-job-submitfrommodel.md) | 從範本中提交工作 |
| [SubmitSoapCall](sm-job-submitsoapcall.md) | 提交工作以進行非同步處理 |
| [WaitJobCanceled](sm-job-waitjobcancelled.md) | 等待工作被取消 |

## 泛型方法

| 方法 | 說明 |
| --- | --- |
| [建立](f-create.md) | 建立與指定結構描述對應的新實體。 |
| [載入](f-load.md) | 載入並傳回與指定結構描述和索引鍵對應的實體。 |
| [儲存](m-entity-save.md) | 將實體儲存在資料庫中。 |
