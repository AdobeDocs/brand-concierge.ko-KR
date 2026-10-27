---
title: 라이브 채팅 및 모임 예약 개요
description: 사용 가능한 대표와의 라이브 채팅 또는 대표자 달력의 예약된 회의와 같이 Brand Concierge이 방문자를 사람에게 전달하는 방법에 대해 알아봅니다.
role: User, Admin
level: Beginner
TQID: https://experienceleague.adobe.com/vfX6M2-ts7d2-AxKGjaP1Ygkk3FGSGRl4CHslcKYSXU
product_v2:
  - id: b6ee73fe-bdc6-47d9-99a2-80194514dd40
    internal-label: Brand Concierge
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 91cbec8d6f4e4800e3bdc8c8f60bfe9ed168a963
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 0%
---
# 라이브 채팅 및 모임 예약 개요 {#overview}

컨시어지가 대부분의 질문에 직접 답변해 드립니다. 일부 대화에는 가격 협상, 조달 설문지, 데모 요청 등 사람이 필요합니다. 라이브 채팅 및 모임 예약은 Brand Concierge이 방문자가 이미 제공한 컨텍스트를 잃지 않고 해당 대화를 사람에게 전달하는 두 가지 방법입니다.

* 라이브 채팅은 동일한 채팅 창에서 방문자를 사용 가능한 담당자에게 즉시 연결합니다.
* 회의 예약은 방문자에게 담당자의 달력에서 실제 오픈 슬롯을 제공하고 회의를 예약합니다.

둘 다 동일한 스킬인 **[!UICONTROL 판매에 전달]**&#x200B;을(를) 제공하고, 두 가지 모두 [!DNL Adobe Marketo Qualifier]&#x200B;(이전의 [!DNL Sales Qualifier])을(를) 통해 전달합니다. 여기서 담당자는 일정을 연결하고, 가용성을 설정하고, 채팅을 수행합니다.

## 전달 작동 방식 {#how-it-works}

방문자가 사람에게 닿기 전에 4개의 조각을 일렬로 세워야 합니다.

| 조각 | 기능 | 설정 위치 |
| --- | --- | --- |
| 대표 프로필 | 달력을 연결하고 대표가 회의 및 채팅에 사용 가능한 경우 선언합니다. | [!DNL Adobe Marketo Qualifier] > **[!UICONTROL 프로필 설정]** |
| 라우팅 | 이 방문자를 받는 *어떤* 담당자를 결정하십시오. | [!DNL Adobe Marketo Qualifier] > **[!UICONTROL 라우팅 규칙]** 및 각 통합의 라우팅 유형 |
| 통합 | **[!UICONTROL 모임 예약]** 및 **[!UICONTROL 실시간 채팅]**&#x200B;을 통해 콘시어지가 사용 가능 여부를 확인하고 채팅을 시작하며 슬롯을 예약할 수 있습니다. | 작성기 > **[!UICONTROL 통합 찾아보기]** |
| 스킬 | **[!UICONTROL 판매에 전달]**&#x200B;은(는) 방문자의 의도에 따라 핸드오프를 제공할 *때*&#x200B;을(를) 결정합니다 | 작성기 > **[!UICONTROL 스킬 찾아보기]** |

런타임 시 방문자는 스킬의 **[!UICONTROL Use when]** 조건 중 하나와 일치하는 것을 말합니다. 이 기술은 연결된 모든 통합을 실행하고 호출합니다. 그러면 라우팅으로 담당자가 배정되고 방문자에게 채팅, 회의 또는 두 가지 모두를 제공합니다.

>[!NOTE]
>
>기술과 통합은 컨시어지의 일반적인 기본 구성 요소입니다. 기본 모델은 [기술 및 통합 프레임워크](../skills-and-integrations.md)를 참조하십시오.

## 방문자 경험 {#visitor-experience}

기술이 실행되면 컨시어지가 옵션들을 설명하고 이를 대화의 버튼으로 제시한다.

![전달 제공 컨시어지 응답, 지금 전문가와의 채팅 및 그 아래의 모임 예약 버튼 사용](../assets/sales-handoff-visitor-1.png){width="800" zoomable="yes"}

### 라이브 채팅 {#visitor-live-chat}

방문자가 채팅을 선택하는 경우, 컨시어지는 라우팅 시 사용 가능한 담당자를 찾는 동안 연결 상태를 표시합니다.

![방문자가 지금 전문가와 대화를 선택한 후 전문가 상태에 대한 연결을 보여 주는 컨시어지](../assets/sales-handoff-visitor-2.png){width="800" zoomable="yes"}

방문자가 참가하기 전에 짧은 사전 채팅 양식을 작성합니다. 이러한 답변은 대화와 함께 이동하며 채팅 받은 편지함에 **[!UICONTROL 양식 세부 정보]**(으)로 담당자에게 표시되므로 방문자는 다른 답변을 반복하지 않아도 됩니다.

방문자는 언제든지 채팅을 종료할 수 있으며 확인하라는 메시지가 표시됩니다.

![방문자에게 전문가와의 채팅 종료를 확인하는 채팅 확인 대화 상자 종료](../assets/sales-handoff-visitor-4.png){width="800" zoomable="yes"}

### 회의 예약 {#visitor-meeting-booking}

방문자가 미팅을 예약하는 경우, 컨시어지는 라우트된 담당자의 달력에서 실제로 열려 있는 슬롯이 있는 달력을 방문자 자신의 시간대로 표시합니다.

![월 일정과 사용 가능한 시간 목록을 표시하는 대화에서 모임 카드를 예약하세요](../assets/sales-handoff-visitor-3.png){width="800" zoomable="yes"}

방문자가 슬롯을 확인한 후 선택적으로 [!DNL Microsoft Teams] 링크가 포함된 대표자의 확인 이메일을 받게 됩니다. 대화 컨텍스트가 초대장과 함께 대표에게 전달됩니다.

## 시작하기 전에 필요한 사항 {#prerequisites}

* 담당자가 [!DNL Adobe Admin Console]의 사용자로 추가된 상태로 [!DNL Adobe Marketo Qualifier]에 액세스할 수 있습니다.
* 캘린더에 연결된 담당자 1명 이상 **[!UICONTROL 모임 예약]** 통합을 활성화하려면 먼저 활성화해야 합니다.
* 라이브 채팅 가용성을 설정한 최소 한 명 이상의 담당자. **[!UICONTROL Live Chat]** 통합을 활성화하려면 먼저 활성화해야 합니다.
* 통합 및 기술을 추가할 수 있는 Composer의 컨시어지.

>[!NOTE]
>
>실시간 채팅 및 모임 예약에는 [!DNL Adobe Marketo Engage]이(가) 필요하지 않습니다. 이 정보가 없으면 담당자, 모임 및 채팅 데이터가 [!DNL Adobe Marketo Qualifier]에 남아 있습니다. [!DNL Marketo Engage]이(가) 필요합니다. [!DNL Marketo] 리드 및 회사 특성에 빌드된 사용자 지정 라우팅 규칙과 [!DNL Marketo] 개인 레코드에 다시 기록되는 컨시어지 활동 유형.

## 라이브 채팅 및 모임 예약 설정 {#setup-path}

순서대로 작업하십시오.

1. [Adobe Marketo Qualifier에서 담당자 설정](representative-setup.md) — 일정을 연결하고, 확인 이메일을 정의하고, 일정 및 실시간 채팅 사용 가능 여부를 설정합니다.
1. [대화 상대에게 라우팅](routing-rules.md) - 라운드 로빈, 직접 에이전트 또는 [!DNL Marketo] 특성에 빌드된 사용자 지정 규칙을 선택합니다.
1. [라이브 채팅 및 모임 예약 활성화](configure-in-composer.md) — 두 통합을 연결하고 **[!UICONTROL 판매에 전달]** 스킬을 활성화합니다.
1. [채팅 받은 편지함](chat-inbox.md) — 대화 점수를 매기는 등 채팅이 도착하면 담당자가 수행하는 작업입니다.
1. [Marketo Engage의 Brand Concierge 데이터](marketo-activities.md) - [!DNL Marketo]에 다시 기록된 리드 필드와 활동 유형과 스마트 캠페인에서 사용하는 방법입니다.
1. [모임 및 실시간 채팅 모니터링](monitor.md) - 예약 목록 및 성과 대시보드.

## 데이터 보존 {#retention}

라이브 채팅 대화는 30일 동안 유지됩니다.
