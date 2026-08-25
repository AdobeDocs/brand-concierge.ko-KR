---
title: Brand Concierge 권한으로 역할 만들기
description: 역할을 만들고 Brand Concierge에 액세스하는 데 필요한 권한을 부여하는 방법을 알아봅니다.
source-git-commit: 591bd1600e586a0a4ce484dbff3f9fb97e24d43d
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 1%

---


# Brand Concierge 권한으로 역할 만들기

Adobe Experience Platform 권한에 역할을 만들어 사용자에게 Brand Concierge에 대한 액세스 권한을 부여합니다.

## 사전 요구 사항

* 역할 및 권한을 관리하는 데 필요한 관리자 권한이 있어야 합니다.
* 먼저 사용자를 Adobe Experience Platform 조직에 추가해야 합니다. 자세한 내용은 &#39;조직에 사용자 추가&#39;(LINK)를 참조하십시오.

## 역할 만들기

1. `experienceplatform.adobe.com`에 로그인합니다.

   >[!NOTE]
   >
   >이 절차를 게시하기 전에 엔지니어링으로 프로덕션 URL을 확인하십시오. 소스 레코딩에서는 비공식적이거나 잘못 기록된 URL을 사용했습니다.

2. 왼쪽 탐색에서 **사용 권한**(으)로 스크롤하여 선택합니다.
3. 기존 역할을 보려면 **역할**&#x200B;을 선택한 다음 **새 역할 만들기**&#x200B;를 선택하십시오.
4. `Brand Concierge Access Users`과(와) 같은 역할 이름을 입력하고 설명을 추가하고 만들기를 확인합니다.
5. 새 역할을 열고 권한을 할당합니다.

   1. **Brand Concierge**&#x200B;에 대한 권한 목록을 검색합니다.
   2. **Brand Concierge 관리**&#x200B;를 선택합니다.

   현재 **Brand Concierge 관리**&#x200B;만 사용 가능한 Brand Concierge 권한입니다. 세분화된 권한 계층은 현재 사용할 수 없습니다.

6. 역할이 액세스할 수 있는 샌드박스 또는 샌드박스를 선택합니다.

   조직에는 격리된 작업 공간인 여러 샌드박스가 포함될 수 있습니다. 이 역할에 적합한 샌드박스만 선택합니다.

7. **저장**&#x200B;을 선택합니다.

## 다음 단계

역할이 만들어지면 사용자를 역할에 추가합니다. 자세한 내용은 &#39;역할에 사용자 추가&#39;(LINK)를 참조하십시오.

## 관련 고려 사항

* 샌드박스를 만들고 관리하는 프로세스는 이 절차의 범위를 벗어납니다.
* 장기 역할 모델을 정의하기 전에 세분화된 Brand Concierge 권한을 추가로 계획할지 확인하십시오.
