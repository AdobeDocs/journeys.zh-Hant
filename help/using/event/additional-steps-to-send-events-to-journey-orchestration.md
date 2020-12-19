---
product: adobe campaign
solution: Journey Orchestration
title: 傳送活動至歷程協調的其他步驟
description: 瞭解將活動傳送至Journey Orchestration的其他步驟
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 7%

---



# 傳送事件至[!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}的其他步驟

>[!NOTE]
>
>建立事件時，[!DNL Journey Orchestration]會自動產生此事件的ID。 推送事件的系統不應產生ID，而應使用裝載預覽中可用的ID。 請參閱[本頁](../event/previewing-the-payload.md)。

要配置要發送到&#x200B;**[!UICONTROL Streaming Ingestion APIs]**&#x200B;並用於[!DNL Journey Orchestration]的事件，需要執行以下步驟：

1. 從Adobe Experience Platform API取得入口URL（請參閱[串流擷取API](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/streaming/overview.html)）。
1. 從&#x200B;**[!UICONTROL Event]**&#x200B;功能表的裝載預覽複製裝載。 請參閱[本頁](../event/defining-the-payload-fields.md)。

然後，您需要設定資料系統，使用您複製的裝載將事件推送至串流擷取API:

1. 設定串流擷取API URL的POST API呼叫（稱為入口網站）。
1. 使用您從API呼叫Streaming Ingestion API的內文（「資料區段」）中[!DNL Journey Orchestration]複製的裝載。 請參閱下方的範例
1. 確定要在何處取得裝載中所有變數。 範例：如果事件應傳達地址，貼上的裝載將顯示「地址」:「字串」。 &quot;string&quot;應由變數取代，變數會自動填入正確值，即要傳送訊息給之人員的電子郵件。 請注意，在裝載預覽的&#x200B;**[!UICONTROL Header]**&#x200B;區段中，我們會自動填入許多值，以方便您工作。
1. 選取「application/json」作為內文類型。
1. 使用索引鍵&quot;x-gw-ims-org-id&quot;，將您的IMS組織ID傳入頁首。 若為值，請使用您的IMS組織ID(「XXX@AdobeOrg」)。

以下是串流擷取API事件的範例：

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

為方便識別貼上「data」部件的位置，您可使用JSON視覺化工具，例如[https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

若要疑難排解串流擷取API，請參閱此[頁面](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/streaming/troubleshooting.html)。
