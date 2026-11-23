---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 2%
---
# 工作流程

工作流程定義

## 方法

| 方法 | 說明 |
| --- | --- |
| [清理](sm-workflow-cleanup.md) | 清除工作流程歷史記錄。 |
| [DeleteResult](sm-workflow-deleteresult.md) | 清除一或多個活動的結果。 |
| [執行](sm-workflow-execute.md) | 立即執行工作流程並等待它完成。 |
| [ExecuteInstance](sm-workflow-executeinstance.md) | 立即執行工作流程並等待它完成。 |
| [GetLogin](sm-workflow-getlogin.md) | 傳回執行帳戶的資訊。 |
| [GetValidationParameters](sm-workflow-getvalidationparameters.md) | 傳回進行中工作流程任務的引數。 |
| [終止](sm-workflow-kill.md) | 無條件停止工作流程。 |
| [暫停](sm-workflow-pause.md) | 暫停執行進行中的工作流程。 |
| [PostEvent](sm-workflow-postevent.md) | 從任何種類的活動產生事件。 |
| [回覆](sm-workflow-reply.md) | 回應進行中的驗證型別工作。 |
| [重新啟動](sm-workflow-restart.md) | 將工作流程停止和工作流程開始連結在一起。 |
| [RestartTask](sm-workflow-restarttask.md) | 強制重新啟動一或多個已完成的工作。 |
| [SetLogin](sm-workflow-setlogin.md) | 變更執行帳戶。 |
| [模擬](sm-workflow-simulate.md) | 在模擬模式下啟動工作流程。 |
| [SimulateWithParameters](sm-workflow-simulatewithparameters.md) | 在模擬模式下啟動工作流程並提供引數給它。 |
| [繁衍](sm-workflow-spawn.md) | 從範本建立工作流程執行個體、套用修補程式，然後啟動此工作流程。 |
| [SpawnWithParameters](sm-workflow-spawnwithparameters.md) | 從範本建立工作流程執行個體，然後叫用此執行個體上的[StartWithParameters](sm-workflow-startwithparameters.md)方法。 |
| [SpawnWithParametersEx](sm-workflow-spawnwithparametersex.md) | 從模型建立工作流程執行個體，並叫用此執行個體上的[StartWithParameters](sm-workflow-startwithparameters.md)或[SimulateWithParameters](sm-workflow-simulatewithparameters.md)方法。 |
| [開始](sm-workflow-start.md) | 開始或繼續執行工作流程。 |
| [StartWithParameters](sm-workflow-startwithparameters.md) | 啟動工作流程並提供引數給它。 |
| [停止](sm-workflow-stop.md) | 停止進行中的工作流程。 |
| [喚醒](sm-workflow-wakeup.md) | 強制提前處理所有待處理任務。 |
| [WakeupTask](sm-workflow-wakeuptask.md) | 強制進階處理一或多個擱置中的工作。 |

## 泛型方法

| 方法 | 說明 |
| --- | --- |
| [建立](f-create.md) | 建立與指定結構描述對應的新實體。 |
| [載入](f-load.md) | 載入並傳回與指定結構描述和索引鍵對應的實體。 |
| [儲存](m-entity-save.md) | 將實體儲存在資料庫中。 |
