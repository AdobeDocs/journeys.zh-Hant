---
product: adobe campaign
title: 將事件傳送至Journey Orchestration的其他步驟
description: 了解將事件傳送至Journey Orchestration的其他步驟
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# 將事件傳送至的其他步驟 [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>建立事件時， [!DNL Journey Orchestration] 自動為此事件產生ID。 The system pushing the event should not generate an ID, it should use the one available in the payload preview. 請參閱[此頁面](../event/previewing-the-payload.md)。

配置要發送到的事件 **[!UICONTROL Streaming Ingestion APIs]** 和 [!DNL Journey Orchestration]，您需要遵循下列步驟：

1. 從Adobe Experience Platform API取得入口URL(請參閱 [串流獲取API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=zh-Hant))。
1. Copy the payload from the payload preview in the **[!UICONTROL Event]** menu. 請參閱[此頁面](../event/defining-the-payload-fields.md)。

然後，您需要設定資料系統，使用您複製的裝載將事件推送至串流獲取API:

1. Set up a POST API call to the Streaming Ingestion APIs URL (called an inlet).
1. 使用您從 [!DNL Journey Orchestration] (位於對串流獲取API呼叫的內文（「資料區段」）中。 See below for an example
1. 決定要在何處取得有效負載中所有變數。 Example: if the event is supposed to convey the address, the payload pasted will show &quot;address&quot;: &quot;string&quot;. &quot;string&quot; should be replaced by the variable that will automatically populate the right value, the email of the person to send a message to. Note that in the payload preview, in the **[!UICONTROL Header]** section, we autofill many values expected to facilitate your work.
1. 選取「application/json」作為內文類型。
1. 使用索引鍵「x-gw-ims-org-id」在標題中傳遞您的IMS組織ID。 若為值，請使用您的IMS組織ID(「XXX@AdobeOrg」)。

Here is an example of a Streaming Ingestion APIs event:

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

為方便您識別「資料」部件貼上位置，您可以使用JSON視覺化工具，例如 [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

若要疑難排解串流獲取API，請參閱 [頁面](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html).
