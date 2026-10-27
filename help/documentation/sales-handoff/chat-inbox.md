---
title: 채팅 받은 편지함
description: 영업 담당자가 Adobe Marketo Qualifier 채팅 받은 편지함에서 Brand Concierge 라이브 채팅을 받고, 처리하고, 점수를 매기고, 끝내는 방법을 알아봅니다.
role: User
level: Beginner
product_v2:
  - id: b6ee73fe-bdc6-47d9-99a2-80194514dd40
    internal-label: Brand Concierge
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 4751ce408fb2aa6d1affae4dd7a5d81ca43ffc8a
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 1%
---
# 받은 채팅 {#chat-inbox}

방문자가 누군가에게 대화를 요청하면 채팅이 [!DNL Adobe Marketo Qualifier]의 **[!UICONTROL 채팅 받은 편지함]**&#x200B;에 도착합니다. 이 페이지는 라이브 채팅에 대한 담당자의 보기입니다. 메시지가 도착하면 표시되는 내용, 상황에 맞는 내용, 창을 닫기 전에 수행해야 하는 작업 등이 있습니다.

열려면 **[!UICONTROL 활동]** 아래의 왼쪽 패널에서 **[!UICONTROL 채팅 받은 편지함]**&#x200B;을 선택하세요.

## 채팅 수신 {#receive}

받은 편지함의 오른쪽 상단에 상태가 표시됩니다. **[!UICONTROL 사용 가능]**&#x200B;은(는) 지금 채팅을 받을 수 있음을 의미합니다. 실시간 채팅 사용 가능 시간에 따라 자격이 있는지 여부가 결정됩니다. [실시간 채팅 사용 가능 여부 설정](representative-setup.md#chat-availability)을 참조하세요.

채팅이 사용자에게 도달하는 방식은 **[!UICONTROL Live 채팅]** 통합에 설정된 라우팅 유형에 따라 다릅니다.

* 라운드 로빈을 사용하면 모든 적격 대표자에게 동시에 통지되며 수락하는 첫 번째 담당자가 대화를 수락합니다.
* 직접 상담원을 고용하면, 채팅은 항상 지정된 대리인에게 온다.
* 사용자 지정 라우팅을 사용하면 방문자가 일치하는 가장 높은 우선 순위 규칙에 할당된 담당자에게 채팅이 이동합니다.

두 개의 탭으로 대화 내용을 구성할 수 있습니다.

* **[!UICONTROL 활성]** — 현재 진행 중인 대화입니다.
* **[!UICONTROL 모두]** - 종료된 대화를 포함하여 모든 대화.

## 대화 시작 {#pick-up}

당신은 절대로 추위를 타지 않아요. 받은 편지함은 사용자가 이미 컨시어지에 알려 준 모든 것을 제공합니다.

![방문자 대화 요약 및 논의된 주제가 있는 채팅 받은 편지함 및 프로필 세부 정보 패널](../assets/sales-handoff-inbox-1.png){width="800" zoomable="yes"}

| 표시되는 항목 | 제공하는 이점 |
| --- | --- |
| **[!UICONTROL 방문자 대화 요약]** | 방문자가 컨시어지와 나눈 대화의 **[!UICONTROL 요약]** 및 **[!UICONTROL 토론 항목]** |
| 대화 대본 | 라이브 채팅이 시작된 지점 위로 컨시어지와 전체 교환 |
| **[!UICONTROL 양식 세부 정보]** | 이메일, 제품 관심사, 회사 등 가입하기 전에 방문자가 사전 채팅 양식에 입력한 항목 |

대본은 두 개의 시스템 줄 `Live chat session has been initiated` 및 `Agent <name> has joined the chat`(으)로 전달 내용을 표시하므로 대화의 어느 부분이 컨시어지이고 어느 부분이 귀하인지 언제든지 알 수 있습니다.

메시지 상자에 입력하고 회신하려면 **[!UICONTROL 보내기]**&#x200B;를 선택하세요.

![대리인과 방문자 간 실시간 채팅 진행 중](../assets/sales-handoff-inbox-2.png){width="800" zoomable="yes"}

## 대화에 점수 매기기 {#conversation-score}

채팅을 종료하기 전에 방문자가 얼마나 자격이 있는지 평가하십시오. 점수는 방문자와 실제로 대화한 담당자인 사용자가 설정하므로 다운스트림에서 신뢰할 수 있습니다.

**[!UICONTROL 프로필 세부 정보]** 패널의 **[!UICONTROL 대화 점수]**&#x200B;에서 등급을 선택하십시오. 대시는 점수가 없음을 의미하며, 불꽃 아이콘은 대화 속도를 가장 낮은 것부터 가장 높은 것으로 지정합니다.

![점수가 잠재 고객 레코드에 0, 1, 2, 3으로 저장되어 있음을 설명하는 대화 점수 도구 설명](../assets/sales-handoff-inbox-4.png){width="600" zoomable="yes"}

| 선택 | 저장된 값 | 의미 |
| --- | --- | --- |
| 대시 | 0 | 최소 정규화 |
| 하나의 불꽃 | 1 | 다소 적격 |
| 두 불꽃 | 2 | 적격 |
| 세가지 불꽃 | 3 | 가장 적격 |

>[!IMPORTANT]
>
>채점은 필수입니다. 채점을 하지 않고 채팅을 닫으려고 하면 오류 `Please score the conversation before you close the chat`이(가) 표시되고 채팅이 열려 있습니다. 채점을 하면 확인이 나타나고 채팅을 닫을 수 있습니다.

![대화 점수가 저장되었는지 확인](../assets/sales-handoff-inbox-3.png){width="800" zoomable="yes"}

점수는 [!DNL Marketo Engage]의 **[!UICONTROL Engage in Concierge]** 활동에 기록되며, 여기서 필터 및 트리거에 대한 제약 조건으로 사용할 수 있습니다. 이를 사용하여 리타겟팅, 리드 점수, 개인화 및 CRM 핸드오프를 유도합니다. [Marketo Engage의 Brand Concierge 데이터](marketo-activities.md)를 참조하세요.

## 채팅 종료 {#end-chat}

대화를 닫으려면 **[!UICONTROL 채팅 종료]**&#x200B;를 선택하세요. 방문자는 자신의 측면에서 종료할 수도 있으며 먼저 확인하라는 메시지가 표시됩니다.

채팅이 닫히면 채팅 대화 상태가 다음 두 값 중 하나로 기록됩니다.

* **종료** — 사용자나 방문자가 의도적으로 대화를 닫았습니다.
* **드롭됨** — 방문자가 사이트를 나갔고 대화 시간이 비활성화되어 시간 초과되었습니다.

>[!NOTE]
>
>라이브 채팅 대화는 30일 동안 유지됩니다.

## 다음 단계 {#next}

이 모든 내용이 [Marketo Engage의 Brand Concierge 데이터](marketo-activities.md)에서 마케팅 데이터베이스에 다시 쓰는 내용을 확인합니다.
