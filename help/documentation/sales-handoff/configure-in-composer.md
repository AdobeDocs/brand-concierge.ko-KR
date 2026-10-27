---
title: 라이브 채팅 및 모임 예약 활성화
description: Composer에서 라이브 채팅 및 모임 예약 통합을 연결한 다음, 컨시어지가 언제 사람을 제공할 것인지 알 수 있도록 판매 스킬에 대한 Handoff를 활성화합니다.
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
source-git-commit: 4751ce408fb2aa6d1affae4dd7a5d81ca43ffc8a
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 0%
---
# 라이브 채팅 및 모임 예약 활성화 {#configure-in-composer}

Composer에는 두 가지 사항이 적용되어야 합니다. **[!UICONTROL 모임 예약]**&#x200B;과(와) **[!UICONTROL 라이브 채팅]** 통합을 통해 콘시어지가 가용성을 확인하고, 채팅을 시작하고, 슬롯을 예약할 수 있는 *기능*&#x200B;을 사용할 수 있습니다. **[!UICONTROL 판매에 전달]** 스킬은 해당 기능을 사용하도록 *시기*&#x200B;에 알려줍니다.

>[!NOTE]
>
>먼저 [Adobe Marketo Qualifier에서 담당자 설정](representative-setup.md)을 완료합니다. 통합은 연결된 캘린더 및 라이브 채팅 가용성을 확인하고 캘린더 없이 활성화되지 않습니다.

## 모임 예약 통합 연결 {#connect-meeting-booking}

1. 작성기에서 컨시어지를 열고 **[!UICONTROL 통합]** > **[!UICONTROL 통합 찾아보기]**&#x200B;를 선택합니다.

   **[!UICONTROL 모임 예약]** 및 **[!UICONTROL 실시간 채팅]**&#x200B;이 **[!UICONTROL 기본 제공 통합]**&#x200B;에 표시됩니다.

   ![Composer에서 기본 제공 통합 아래의 라이브 채팅 및 모임 예약 카드를 표시하는 통합 패널 찾아보기](../assets/sales-handoff-composer-1.png){width="800" zoomable="yes"}

1. **[!UICONTROL 모임 예약]**&#x200B;을 선택한 다음 **[!UICONTROL 구성]**&#x200B;을 선택합니다.

1. 이름과 설명을 입력합니다.

   `Meeting booking - US region` 또는 `Meeting booking - round robin`과(와) 같이 이 컨시어지에서 수행하는 작업의 통합 이름을 지정합니다. 두 개 이상을 연결할 수 있으므로 나중에 구분하는 방식으로 이름을 지정합니다.

1. 캘린더 연결 상태를 확인합니다.

   통합은 조직 내 최소 한 명 이상의 담당자가 달력을 연결했는지 확인합니다.

   * 캘린더가 없으면 회의 예약을 활성화하기 전에 하나 이상의 캘린더에 연결하라는 오류가 표시됩니다. [!DNL Adobe Marketo Qualifier]&#x200B;(으)로 돌아가서 [일정을 연결](representative-setup.md#connect)합니다.
   * 최소 한 명이라도 보유하고 있다면, 확인 결과에 담당자가 가능한 것으로 표시됩니다.

1. 라우팅 형식을 선택하십시오. **[!UICONTROL Round robin]**, **[!UICONTROL 직접 에이전트]** 또는 **[!UICONTROL 사용자 지정 라우팅]**.

   **[!UICONTROL 직접 에이전트]**&#x200B;을(를) 선택하는 경우 이 컨시어지를 통해 예약된 모든 모임을 받는 담당자를 선택하십시오. **[!UICONTROL 사용자 지정 라우팅]**&#x200B;을(를) 선택하면 [!DNL Adobe Marketo Qualifier]에서 만든 라우팅 규칙이 적용됩니다. 각 사용자의 동작 방법에 대해서는 [담당자에게 대화 라우팅](routing-rules.md)을 참조하십시오.

1. **[!UICONTROL 연결]**&#x200B;을 선택합니다.

## 라이브 채팅 통합 연결 {#connect-live-chat}

1. **[!UICONTROL 통합 찾아보기]**&#x200B;에서 **[!UICONTROL 라이브 채팅]**&#x200B;을 선택한 다음 **[!UICONTROL 구성]**&#x200B;을 선택합니다.

1. 이름과 설명을 입력하십시오(예: `Live chat - round robin`).

1. 라이브 채팅 사용 가능 상태를 확인합니다.

   통합은 최소 한 명 이상의 담당자가 라이브 채팅 가용성을 설정했는지 확인합니다.

   * 이 없는 경우 라이브 채팅 가용성을 설정한 담당자를 추가하라는 메시지가 표시됩니다. [!DNL Adobe Marketo Qualifier]&#x200B;(으)로 돌아가서 [실시간 채팅 사용 가능 여부 설정](representative-setup.md#chat-availability)을 완료합니다.
   * 최소 한 명이라도 보유하고 있다면, 확인 결과에 담당자가 가능한 것으로 표시됩니다.

1. 라우팅 유형을 선택합니다.

   라이브 채팅은 모임 예약과 동일한 세 가지 라우팅 유형을 지원합니다. **[!UICONTROL 라운드 로빈]**&#x200B;을(를) 사용하면 모든 적격 담당자에게 한꺼번에 알림이 전송되며 첫 번째 수락자가 채팅을 수행합니다.

1. **[!UICONTROL 연결]**&#x200B;을 선택합니다.

## 영업 스킬에 대한 전달 활성화 {#activate-skill}

이제 통합이 연결되었지만 컨시어지는 언제 통합을 제공할지 알아야 합니다. 그게 바로 기술이야.

1. 작성기에서 **[!UICONTROL 스킬]** > **[!UICONTROL 스킬 찾아보기]**&#x200B;를 선택한 다음 **[!UICONTROL 판매에 전달]**&#x200B;을 선택합니다.

   세부 정보 패널에는 스킬 설명, 해당 **[!UICONTROL 다음의 경우 사용]** 조건, 권장 **[!UICONTROL 통합]** 및 **[!UICONTROL 스킬 지침]**&#x200B;이 표시됩니다.

   ![판매 스킬에 대한 전달 기능이 선택된 스킬 패널 찾아보기, 조건, 권장 통합 및 스킬 지침 사용 표시](../assets/sales-handoff-composer-2.png){width="800" zoomable="yes"}

1. **[!UICONTROL 수정]**&#x200B;을 선택합니다.

   ![편집 가능한 스킬 이름, 설명 및 조건일 때 사용을 사용하여 수정 모드에서 판매 스킬에 전달](../assets/sales-handoff-composer-3.png){width="800" zoomable="yes"}

1. 스킬 이름과 설명을 검토하고 원하는 경우 편집하십시오.

1. **[!UICONTROL 사용할 때]** 조건을 검토합니다.

   핸드오프를 트리거하는 의도입니다. 이 스킬은 기본 세트와 함께 제공됩니다.

   | 조건 | 트리거 켜기 |
   | --- | --- |
   | 컨설턴트 액세스 | 모임 예약 또는 예약, 라이브 채팅 시작 또는 회사 담당자 연결 요청 |
   | 판매 및 구매 | 가격 책정, 견적, 할인, 구매 지원 또는 엔터프라이즈 라이선스 |
   | 경쟁 제품 비교 | 경쟁업체 솔루션과 솔루션 비교, 차별화 또는 경쟁업체 플랫폼과의 마이그레이션 |
   | 체험판 및 POC 액세스 | 체험판 설정, 놀이터 액세스, 개념 증명 또는 파일럿 |
   | 계약 및 라이선스 변경 | 계약 갱신, 기간 연장 또는 계획 업그레이드 |
   | 조달 RFP 또는 RFI | 제출, 응답, 공급업체 설문지, 구매 양식 또는 규정 준수 문서 |
   | 데모 | 제품 데모 또는 연습 |

   **[!UICONTROL 조건 추가]**&#x200B;를 선택하여 자신의 의도를 추가하거나 귀하의 비즈니스에 적용되지 않는 조건을 삭제합니다.

1. 연결한 통합을 추가합니다.

   이 컨시어지에서 제공할 내용에 따라 **[!UICONTROL 라이브 채팅]**, **[!UICONTROL 모임 예약]** 또는 두 가지 모두를 추가하십시오.

1. **[!UICONTROL 스킬 지침]**&#x200B;을 검토합니다.

   지침은 선택한 조건 및 통합에서 생성되므로 대부분의 경우 편집이 필요하지 않습니다.

   어떤 옵션으로 연결되는지 더 세밀하게 제어하려면 일반 언어로 편집하십시오. 예를 들어, 가격 책정 질문에 대한 실시간 채팅을 제공하고, 데모 요청에 대한 회의를 제공하고, 조달 질문에 대한 두 가지 모두를 제공하도록 컨시어지를 지시할 수 있습니다.

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

## 테스트 및 게시 {#test-and-publish}

미리 보기를 열고 컨시어지에 데모 요청과 같이 **[!UICONTROL Use when]** 조건 중 하나와 일치하는 항목을 요청하십시오. 컨시어지는 전문가와 연결하고, 채팅 옵션, 회의 옵션 또는 두 옵션을 모두 표시하며, 실제 가용성을 제공할 수 있도록 제공해야 합니다.

동작이 적절하면 컨시어지를 게시하여 사이트에서 핸드오프를 라이브로 만듭니다.

## 다음 단계 {#next}

이제 담당자들이 채팅을 받을 수 있습니다. [채팅 받은 편지함](chat-inbox.md)을 참조하세요.
