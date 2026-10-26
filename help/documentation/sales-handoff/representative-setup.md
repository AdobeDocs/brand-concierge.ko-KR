---
title: Adobe Marketo Qualifier 담당자 설정
description: 담당자의 Outlook 또는 Google 캘린더를 연결하고 모임 확인 이메일을 설정하고 캘린더 및 라이브 채팅 사용 가능 여부를 정의하고 설정된 사용자를 검토합니다.
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
source-wordcount: '784'
ht-degree: 1%
---
# Adobe Marketo Qualifier 담당자 설정 {#representative-setup}

컨시어지가 모임 또는 실시간 채팅을 제공하려면 먼저 [!DNL Adobe Marketo Qualifier]에 적어도 한 명의 담당자를 설정해야 합니다. 각 담당자는 자신의 프로필에서 이 작업을 한 번 수행합니다.

순서는 관리자가 사용자를 추가한 다음 각 담당자가 달력을 연결하고 확인 이메일을 작성한 다음 회의 및 채팅에 사용할 수 있을 때를 선언하는 것입니다.

## 조직에 사용자 추가 {#add-users}

관리자가 각 영업 담당자를 [!DNL Adobe Admin Console]의 사용자로 추가하여 [!DNL Adobe Marketo Qualifier]에 대한 액세스 권한을 부여합니다. 일반 절차는 [조직에 사용자 추가](../user-and-access-management/add-a-user-to-the-org.md) 및 [역할에 사용자 추가](../user-and-access-management/add-a-user-to-the-role.md)를 참조하십시오.

나머지 단계는 대표자가 직접 완료합니다.

## 캘린더 연결 {#connect}

일정 연결을 통해 컨시어지에서 실제 가용성을 확인할 수 있습니다. 이 기능이 없으면 담당자는 모임 예약에 적합하지 않습니다.

1. [Adobe Experience Cloud](https://experience.adobe.com/){target="_blank"}에 로그인하고 **[!UICONTROL Adobe Marketo Qualifier]**&#x200B;을(를) 선택합니다.

   ![Adobe Marketo Qualifier 카드가 있는 Adobe Experience Cloud 홈 페이지](../assets/meetings-connect-1.png){width="800" zoomable="yes"}

1. 왼쪽 패널의 **[!UICONTROL 구성]**&#x200B;에서 **[!UICONTROL 프로필 설정]**&#x200B;을 선택한 다음 **[!UICONTROL 달력 구성]** 탭을 엽니다.

1. 연결할 일정을 선택하십시오. [!DNL Microsoft Outlook] 또는 [!DNL Google Calendar].

   ![Outlook 및 Google 일정 연결 옵션을 표시하는 일정 구성 탭](../assets/meetings-connect-2.png){width="600" zoomable="yes"}

1. 기존 계정으로 로그인하거나 새 계정을 추가한 다음 요청된 권한을 부여합니다.

   ![일정 연결 중에 표시되는 Microsoft 계정 선택기](../assets/meetings-connect-3.png){width="600" zoomable="yes"}

1. 방문자가 귀하와의 회의를 예약할 때 전송되는 확인 이메일을 검토합니다.

   기본 제목 줄과 본문이 설정되어 있습니다. 둘 중 하나를 편집하고 초대에 [!DNL Microsoft Teams] 모임 링크를 포함할지 여부를 선택합니다.

   ![제목 줄과 본문이 편집 가능한 모임 확인 전자 메일 설정](../assets/meetings-connect-4.png){width="600" zoomable="yes"}

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

## 일정 가용성 설정 {#calendar-availability}

캘린더에 연결하면 *사용 중*&#x200B;일 때 [!DNL Adobe Marketo Qualifier]에 표시됩니다. 일정 가용성은 사용자가 *기꺼이*&#x200B;하여 모임을 가질 때 이를 알려줍니다. 둘 다 적용됩니다.

1. **[!UICONTROL 프로필 설정]**&#x200B;에서 **[!UICONTROL 일정 가용성]** 탭을 엽니다.

   ![가용성이 설정되기 전의 일정 가용성 탭](../assets/meetings-availability-1.png){width="600" zoomable="yes"}

1. 모임 규칙을 설정합니다.

   | 설정 | 제어 항목 |
   | --- | --- |
   | 모임 기간 | 예약된 회의 실행 시간 및 따라서 제공된 각 슬롯의 길이 |
   | 버퍼 시간 | 한 회의 종료와 다음 회의 시작 사이에 적용된 간격 |
   | 최소 알림 | 방문자가 예약해야 하는 사전 기간. 예를 들어 방문자가 10분 후에 시작하는 슬롯을 예약하지 못하도록 4시간을 설정합니다 |
   | 시간대 | 가용 시간이 표시되는 표준 시간대입니다. 방문자는 항상 자신의 시간대로 변환된 슬롯을 봅니다. |

1. 각 요일에 사용 가능한 시간을 설정합니다.

   하루는 오전 8:00~오후 5:00과 같은 하나의 연속 블록이거나 오전 8:00~오후 12:00, 오후 2:00~오후 5:00과 같은 여러 블록일 수 있습니다. 해당 날짜에 회의를 하지 않으려면 하루를 비워 둡니다.

   >[!NOTE]
   >
   >하루에 다른 시간 블록을 추가하려면 더하기 기호(![더하기 기호 아이콘](../assets/icon-plus-sign.png))를 선택하세요.

   ![주중 시간과 분할 시간 범위가 구성된 일정 사용 가능 탭](../assets/meetings-availability-2.png){width="600" zoomable="yes"}

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

### 슬롯을 예약할 수 있는 방법 {#slot-logic}

시간 슬롯은 다음 세 가지 검사를 모두 통과해야 방문자에게 제공됩니다.

1. 여기에서 설정한 사용 가능한 시간 내에 해당합니다.
1. 연결된 캘린더의 이벤트에서 이미 사용하고 있지 않습니다. 기존 오전 9시 모임은 오전 9시 슬롯을 제거합니다.
1. 귀사의 최소 통지 및 버퍼 시간을 만족합니다.

## 라이브 채팅 가용성 설정 {#chat-availability}

라이브 채팅 가용성은 일정 가용성과 별개입니다. 담당자는 채팅에 참여할 수 있지만 모임은 가질 수 없거나 그 반대입니다.

1. **[!UICONTROL 프로필 설정]**&#x200B;에서 **[!UICONTROL 실시간 채팅 가용성]** 탭을 엽니다.

1. 시간대를 설정한 다음 라이브 채팅을 받을 요일과 시간을 설정합니다. 주말도 포함되어 있습니다.

   ![일 및 시간이 구성된 실시간 채팅 사용 가능 탭](../assets/meetings-availability-3.png){width="600" zoomable="yes"}

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

>[!NOTE]
>
>사용 가능 시간을 사용하면 채팅에 *적격*&#x200B;할 수 있습니다. 채팅 받은 편지함의 라이브 상태에 따라 지금 바로 받을 수 있는지 여부가 결정됩니다. [채팅 받은 편지함](chat-inbox.md)을 참조하세요.

## 설정된 사용자 검토 {#manage-members}

**관리자만.** **[!UICONTROL 관리]**&#x200B;에서 **[!UICONTROL 구성원 관리]**&#x200B;를 선택하여 한 곳에서 모든 대리인의 상태(일정 연결 사용자, 실시간 채팅 사용 가능 여부 설정 사용자, 일정 연결 끊기 사용자)를 확인합니다.

Composer에서 통합을 활성화하기 전에 이 옵션을 사용하십시오. 연결된 캘린더 없이 여기에 나타나는 대표는 모임 예약에 적합하지 않으며 라이브 채팅 사용 가능 여부가 없는 대표는 라이브 채팅에 적합하지 않습니다.

![대표자와 일정 및 실시간 채팅 설정 상태를 나열하는 구성원 관리 페이지](../assets/manage-members-1.png){width="800" zoomable="yes"}

## 다음 단계 {#next}

최소 한 명 이상의 담당자를 설정한 상태에서 방문자가 담당자와 일치하는 방식을 결정합니다. [담당자에게 대화 라우팅](routing-rules.md)을 참조하세요.
