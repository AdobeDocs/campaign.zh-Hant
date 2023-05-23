---
product: campaign
title: 儲存格
description: 儲存格
feature: Workflows, Targeting Activity
exl-id: d85645a6-fc15-4c3a-9d67-d4230224e1f7
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 2%

---

# 儲存格{#cells}

的 **[!UICONTROL Cells]** 「活動」提供了各種子集的資料列視圖。 它方便了子集操作，還設計為利用個性化功能。

![](assets/wf_split_cells.png)

可以根據用戶需要配置此活動以輸入特定參數。 預設情況下，每個子集的詳細資訊將通過 **[!UICONTROL Cells]** 和 **[!UICONTROL Advanced]** 頁籤。

![](assets/wf_split_cells_with_customization.png)

在下面的示例中，輸入表單已修改：a **[!UICONTROL Data]** 已添加頁籤，以啟用提供和每個子集的優先順序的關聯。

![](assets/cells-activity-sample.png)

對於此配置，以下資訊已添加到工作流表單中。 **[!UICONTROL Administration > Configurations > Input forms]** Adobe Campaign瀏覽器節點：

```
<container img="nms:miniatures/mini-enrich.png" label="Data">
                <input xpath="@code"/>
                <container xpath="select/node[@alias='@numTest']">
                  <input alwaysActive="true" expr="'long'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Priority'" type="expr" xpath="@label"/>
                  <input label="Priority" maxValue="12" minValue="0" type="number"
                         xpath="@value" xpathEditFromType="@type"/>
                </container>
                <container xpath="select/node[@alias='@test']">
                  <input alwaysActive="true" expr="'string'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Identifier'" type="expr" xpath="@label"/>
                  <input label="Cell identifier" xpath="@value"/>
                </container>
                <container xpath="select/node[@alias='linkTest']">
                  <input alwaysActive="true" expr="'link'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'nms:offer'" type="expr" xpath="@dataType"/>
                  <input alwaysActive="true" expr="'Offre'" type="expr" xpath="@label"/>
                  <input computeStringAlias="@valueLabel" label="Offers" notifyPathList="@_cs|@valueLabel"
                         schema="nms:offer" type="linkEdit" xpath="@value"/>
                </container>
```

Adobe Campaign的輸入表單個性化是專家用戶保留的。