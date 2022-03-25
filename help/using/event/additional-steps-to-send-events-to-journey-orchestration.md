---
product: adobe campaign
title: 將事件發送到Journey Orchestration的其他步驟
description: 瞭解將事件發送到Journey Orchestration的其他步驟
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# 將事件發送到的其他步驟 [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>建立事件時， [!DNL Journey Orchestration] 自動生成此事件的ID。 推送事件的系統不應生成ID，它應使用負載預覽中可用的ID。 請參閱[此頁面](../event/previewing-the-payload.md)。

配置要發送到的事件 **[!UICONTROL Streaming Ingestion APIs]** 和 [!DNL Journey Orchestration]，您需要執行以下步驟：

1. 從Adobe Experience PlatformAPI獲取入口URL(請參見 [流式接收API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=zh-Hant))。
1. 從中的負載預覽複製負載 **[!UICONTROL Event]** 的子菜單。 請參閱[此頁面](../event/defining-the-payload-fields.md)。

然後，您需要配置資料系統，該資料系統使用您複製的負載將事件推送到Streaming Ingestion API:

1. 設定對流接收API URL的POSTAPI調用（稱為入口）。
1. 使用從中複製的負載 [!DNL Journey Orchestration] API調用的正文（「資料部分」）中。 有關示例，請參閱下面
1. 確定從何處獲取負載中存在的所有變數。 示例：如果事件應傳遞地址，則貼上的負載將顯示「地址」：&quot;字串&quot;。 &quot;string&quot;應替換為自動填充正確值的變數，即要向其發送消息的人員的電子郵件。 請注意，在負載預覽中， **[!UICONTROL Header]** 部分，我們將自動填充許多值以便您工作。
1. 選擇「application/json」作為正文類型。
1. 使用鍵「x-gw-ims-org-id」在題頭中傳遞您的IMS組織ID。 有關值，請使用IMS組織ID(「XXX@AdobeOrg」)。

以下是流接收API事件的示例：

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

為便於識別貼上「data」部件的位置，可以使用JSON可視化工具，如 [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

要排除流接收API故障，請參閱 [頁](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html)。
