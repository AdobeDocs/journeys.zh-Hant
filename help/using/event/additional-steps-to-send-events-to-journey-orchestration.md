---
product: adobe campaign
title: 傳送事件至Journey Orchestration的其他步驟
description: 瞭解將事件傳送至Journey Orchestration的其他步驟
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 2%

---

# 傳送事件給[!DNL Journey Orchestration]的其他步驟 {#concept_xrz_n1q_y2b}



>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


>[!NOTE]
>
>建立事件時，[!DNL Journey Orchestration]會自動為此事件產生識別碼。 推播事件的系統不應產生ID，而應使用裝載預覽中可用的ID。 請參閱[此頁面](../event/previewing-the-payload.md)。

若要設定要傳送至&#x200B;**[!UICONTROL Streaming Ingestion APIs]**&#x200B;以及用於[!DNL Journey Orchestration]的事件，您必須遵循下列步驟：

1. 從Adobe Experience Platform API取得入口URL （請參閱[串流獲取API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=zh-Hant)）。
1. 從&#x200B;**[!UICONTROL Event]**&#x200B;功能表的裝載預覽複製裝載。 請參閱[此頁面](../event/defining-the-payload-fields.md)。

然後，您需要設定資料系統，使用您複製的裝載將事件推送至串流獲取API：

1. 設定對串流獲取API URL的POST API呼叫（稱為入口）。
1. 使用您從[!DNL Journey Orchestration]複製的裝載，該裝載位於串流獲取API之API呼叫的內文（「資料區段」）中。 如需範例，請參閱下文
1. 決定從何處取得裝載中出現的所有變數。 範例：如果事件應該要傳達位址，貼上的裝載將會顯示「address」：「string」。 「string」應該取代為會自動填入正確值的變數，也就是傳送訊息對象的電子郵件。 請注意，在裝載預覽的&#x200B;**[!UICONTROL Header]**&#x200B;區段中，我們會自動填入許多預期有助於您工作的值。
1. 選取「application/json」作為內文型別。
1. 使用索引鍵「x-gw-ims-org-id」在標題中傳遞您的IMS組織ID。 此值請使用您的IMS組織ID (「XXX@AdobeOrg」)。

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

若要方便識別貼上「資料」部分的位置，您可以使用JSON視覺化工具，例如[https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

若要排查串流擷取 API，請参閱此 [頁面](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html)。
