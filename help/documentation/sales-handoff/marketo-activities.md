---
title: Marketo Engage의 Brand Concierge 데이터
description: Adobe Marketo Engage에 작성된 리드 소스 필드 및 세 가지 컨시어지 활동 유형과 스마트 목록 및 스마트 캠페인에서 이를 사용하는 방법을 이해합니다.
role: User, Admin
level: Beginner
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
source-git-commit: ec567c798c52edaba7e2cfb41a837d8058bcceb7
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 4%
---
# Marketo Engage의 Brand Concierge 데이터 {#marketo-activities}

[!DNL Adobe Marketo Engage]이(가) 연결되면 양식을 작성하고 모임을 예약하거나 라이브 채팅을 시작하는 모든 방문자는 [!DNL Marketo]의 개인 레코드가 되고 해당 레코드에 기본 활동 유형으로 관리인 참여가 기록됩니다. 즉, 다른 [!DNL Marketo] 활동에서와 마찬가지로 컨시어지 동작에 대해 스마트 목록과 스마트 캠페인을 작성할 수 있습니다.

>[!NOTE]
>
>라이브 채팅 및 모임 예약 자체는 [!DNL Marketo Engage]이(가) 필요하지 않습니다. 이 페이지가 없으면 이 페이지에 설명된 데이터는 [!DNL Adobe Marketo Qualifier]에 유지됩니다. [실시간 채팅 및 모임 예약 개요](overview.md#prerequisites)를 참조하세요.

## 리드 생성 및 소스 속성 {#lead-creation}

컨시어지를 통해 만든 사람은 꼬리표가 붙어있어 언제 어디서 왔는지를 알 수 있다.

| 필드 | 값 |
| --- | --- |
| **[!UICONTROL 개인 Source]** | `Brand Concierge` |
| **[!UICONTROL 원래 Source 유형]** | `Chat` |
| **[!UICONTROL 원본 Source 정보]** | `Concierge` |
| **[!UICONTROL 등록 Source 유형]** | `Chat` |
| **[!UICONTROL 등록 Source 정보]** | `Concierge` |

![Marketo 개인 레코드 정보 탭에서 개인 Source이 Brand Concierge으로 설정되어 있으며 채팅 및 컨시어지 소스 필드가 표시되어 있음](../assets/sales-handoff-marketo-1.png){width="800" zoomable="yes"}

## 활동 유형 {#activity-types}

세 가지 기본 활동 유형이 개인 레코드에 푸시됩니다. 세 가지 모두 트리거와 필터로 사용할 수 있습니다.

![Marketo 활동 로그에는 컨시어지 참여, 컨시어지에서 모임 예약, 컨시어지 항목의 라이브 채팅에 참여 표시](../assets/sales-handoff-marketo-2.png){width="800" zoomable="yes"}

### 컨시어지 서비스 {#engage-with-concierge}

방문자가 컨시어지 서비스를 이용할 때 기록됩니다.

| 속성 | 설명 |
| --- | --- |
| 컨시어지 이름 | 방문자가 참여한 컨시어지 |
| 대화 ID | 대화의 식별자. 작성기에서 이를 사용하여 전체 대본 열기 |
| 페이지 URL | 참여가 발생한 페이지 |
| 생성 위치 | 대화가 만들어진 시기 |
| 지속 시간 | 대화가 지속된 시간 |

>[!NOTE]
>
>논의된 주제, 요약 및 언어를 포함하여 이 활동 유형의 일부 속성이 아직 채워지지 않았습니다. 향후 릴리스가 예정되어 있습니다.

### 컨시어지에서 회의 예약 {#schedule-meeting}

단일 예약에 대해 **두 번**&#x200B;을 기록했습니다. 이렇게 하면 결과와 의도를 구분할 수 있습니다.

**먼저 시작 시** 방문자가 회의 예약 옵션을 선택하고 예약 양식이 표시되었습니다. 모임 상태는 `Started`입니다.

| 속성 | 설명 |
| --- | --- |
| 모임 상태 | `Started` |
| 페이지 URL | 방문자가 예약을 시작한 페이지 |
| 컨시어지 ID | 방문자가 참여한 컨시어지 |
| 개인 ID | [!DNL Marketo]명의 개인 레코드 |

**예약 시** 방문자가 슬롯을 확인했습니다. 모임 상태는 `Scheduled`입니다.

| 속성 | 설명 |
| --- | --- |
| 모임 상태 | `Scheduled` |
| 영업 담당자 이름 | 그 회의는 대표자와 함께 예약되었다 |
| 영업 담당자 이메일 | 담당자 이메일 주소 |
| 예약 대상 | 회의 날짜 및 시간 |
| 모임 기간 | 예약된 회의의 기간 |
| 라우팅 유형 | 이 담당자의 달력을 해결한 라우팅 |
| 페이지 URL | 방문자가 예약한 페이지 |
| 컨시어지 ID | 방문자가 참여한 컨시어지 |
| 개인 ID | [!DNL Marketo]명의 개인 레코드 |

>[!TIP]
>
>`Meeting Status`에서 스마트 목록을 만들면 `Started`이지만 `Scheduled`은(는) 아닙니다. 모임을 예약하기 시작하고 중단한 모든 사람을 찾을 수 있습니다. 이는 준비된 육성 또는 재타겟팅 대상입니다.

### 컨시어지에서 라이브 채팅 사용 {#engage-with-live-chat}

라이브 채팅이 종료된 후 기록됩니다.

| 속성 | 설명 |
| --- | --- |
| 대화 상태 | 채팅을 의도적으로 닫았다면 `Ended`, 방문자가 사이트를 나갔고 채팅 시간이 초과되었다면 `Dropped` |
| 통지된 에이전트 | 이 채팅에 대한 알림을 받은 모든 에이전트의 이메일 주소 |
| 대화 점수 | 0:3 등급으로 대표자가 대화를 진행했습니다. [대화 점수](chat-inbox.md#conversation-score)를 참조하세요. |
| 페이지 URL | 라이브 채팅이 시작된 페이지 |
| 컨시어지 ID | 방문자가 참여한 컨시어지 |
| 세션 ID | 라이브 채팅 세션 식별자 |
| 시작 시간 | 채팅이 시작된 시기 |

>[!TIP]
>
>대화 점수는 방문자와 실제로 대화한 사람이 설정했으므로 여기에서 가장 높은 값의 속성입니다. 잠재 고객 점수 책정, 재타겟팅, 개인화 및 판매 및 CRM에 대한 핸드오프에 사용합니다.

## Smart Campaign에서 컨시어지 데이터 사용 {#smart-campaign}

스마트 캠페인의 **[!UICONTROL 스마트 목록]**&#x200B;에서 `concierge`을(를) 검색하여 사용 가능한 모든 항목을 확인하세요.

![Brand Concierge 활동에 사용할 수 있는 컨시어지 트리거 및 필터를 보여 주는 Marketo 스마트 목록](../assets/sales-handoff-marketo-3.png){width="800" zoomable="yes"}

| 카테고리 | 사용 가능한 항목 |
| --- | --- |
| **[!UICONTROL 트리거]** | 컨시어지, 컨시어지에서 라이브 채팅, 컨시어지에서 회의 일정 |
| **[!UICONTROL 필터]** > 활동 기록 | 컨시어지, 컨시어지에서 라이브 채팅, 컨시어지에서 회의 예약 |
| **[!UICONTROL 필터]** > 비활성 필터 | 컨시어지 미참여, 컨시어지 내 라이브 채팅 미참여, 컨시어지 내 미팅 미참여 |

트리거 또는 필터를 캔버스로 드래그한 다음 **[!UICONTROL 제한 추가]**&#x200B;를 선택하여 범위를 좁힙니다.

### 제한 {#constraints}

| 트리거 또는 필터링 | 제한 |
| --- | --- |
| Concierge 참여 | 컨시어지 이름, 페이지 URL, 생성 시간, 기간, 활동 날짜 |
| 컨시어지에서 예약된 회의 | 컨시어지명, 영업 담당자 이름, 회의 상태, 예정, 회의 기간, 라우팅 유형, 페이지 URL, 활동 날짜 |
| Concierge에서 라이브 채팅 참여 | 컨시어지명, 영업 담당자 이름, 대화 상태, 대화 점수, 시작 시간, 수락 시간, 종료 시간, 종료자, 기간, 논의 주제, 페이지 URL, 언어, 활동 날짜 |

## 다음 단계 {#next}

[모임 및 실시간 채팅 모니터링](monitor.md)에서 모임 및 채팅이 수행되는 방식을 검토하세요.
