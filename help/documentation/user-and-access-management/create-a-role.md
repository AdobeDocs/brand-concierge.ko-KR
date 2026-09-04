---
title: Brand Concierge 권한으로 역할 만들기
description: 역할을 만들고 Brand Concierge에 액세스하는 데 필요한 권한을 부여하는 방법을 알아봅니다.
source-git-commit: 60835c7971d86341194d773f9cf487c4cb6f171a
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 1%

---


# Brand Concierge 권한으로 역할 만들기

Adobe Experience Platform 권한에 역할을 만들어 사용자에게 Brand Concierge에 대한 액세스 권한을 부여합니다.

>[!PREREQUISITES]
>
>- 역할 및 권한을 관리하는 데 필요한 관리자 권한이 있어야 합니다.
>- 먼저 사용자를 Adobe Experience Platform 조직에 추가해야 합니다. 자세한 내용은 [조직에 사용자 추가](./add-a-user-to-the-org.md)를 참조하십시오.

## 역할 만들기

1. `experienceplatform.adobe.com`에 로그인합니다.

1. 왼쪽 탐색에서 **사용 권한**(으)로 스크롤하여 선택합니다.
1. **역할**(으)로 이동하여 기존 역할을 보고 **새 역할 만들기**&#x200B;를 선택합니다.
1. `Brand Concierge Access Users`과(와) 같은 역할 이름을 입력하고 설명을 추가하고 만들기를 확인합니다.
1. 새 역할을 열고 권한을 할당합니다.

   1. **Brand Concierge**&#x200B;에 대한 권한 목록을 검색합니다.
   1. **Brand Concierge 관리**&#x200B;를 선택합니다.

   현재 **Brand Concierge 관리**&#x200B;는 사용 가능한 유일한 Brand Concierge 권한입니다. 세분화된 권한 계층은 아직 사용할 수 없습니다.

1. 역할이 액세스할 수 있는 샌드박스 또는 샌드박스를 선택합니다.

   조직에는 격리된 작업 공간인 여러 샌드박스가 포함될 수 있습니다. 이 역할에 적합한 샌드박스만 선택합니다.

1. **저장**&#x200B;을 선택합니다.

## 다음 단계

역할이 만들어지면 사용자를 역할에 추가합니다. 자세한 내용은 [Brand Concierge 역할에 사용자 추가](./add-a-user-to-the-role.md)를 참조하십시오.
