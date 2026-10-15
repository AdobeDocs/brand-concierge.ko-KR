---
title: 쿼리 서비스 및 터미널을 사용하여 대화 내보내기
description: 자격 증명 및 개인 데이터에 대한 지침과 함께 Experience Platform 쿼리 서비스 및 터미널을 사용하여 Brand Concierge 대화를 CSV로 내보내는 방법에 대해 알아봅니다.
topic: Development
role: Developer
level: Experienced
doc-type: Tutorial
duration: 260
last-substantial-update: 2026-10-15
jira: KT-22874
source-git-commit: 0d9fa76d0fe3494daa7189ab9e9984a423ee1d6e
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%
---
# 쿼리 서비스 및 터미널을 사용하여 대화 내보내기

Adobe Experience Platform 쿼리 서비스 및 터미널을 사용하여 Adobe Brand Concierge 대화를 저장하고 내보내는 방법에 대해 알아봅니다. 이 비디오는 데이터 세트 테이블 이름을 찾고, PostgreSQL 명령줄 클라이언트를 구성하고, 날짜 범위에 대한 대화 데이터를 CSV 파일로 내보내는 방법을 보여 줍니다.

## 이 비디오는 누구의 것입니까?

* 명령줄 도구를 사용하여 Brand Concierge 대화 데이터를 내보내야 하는 개발자

## 비디오 콘텐츠

* Experience Platform에서 대화 데이터 세트를 찾고 해당 테이블 이름 복사
* Homebrew를 사용하여 PostgreSQL 클라이언트를 설치하고 명령줄 경로를 구성합니다.
* 쿼리 서비스 자격 증명 탭에서 PSQL 연결 명령을 복사합니다.
* 데이터 세트 및 날짜 범위를 선택한 다음 쿼리 결과를 로컬 CSV 파일로 내보냅니다
* 내보낸 결과를 확인하고 필요한 경우 만료된 자격 증명을 새로 고칩니다.

>[!VIDEO](https://video.tv.adobe.com/v/3504643)

>[!IMPORTANT]
>
> PSQL 연결 명령에는 라이브 암호가 포함되어 있습니다. 공유하거나 채팅, AI 에이전트 또는 이메일에 붙여넣지 마십시오. 암호가 만료된 후 인증이 실패하면 [쿼리 서비스 자격 증명] 탭에서 새 명령을 복사합니다.

>[!NOTE]
>
> 내보낸 대화에는 PII(개인 식별 정보)가 포함될 수 있습니다. CSV 파일을 저장할 때 조직의 데이터 처리 정책을 따르십시오.

설명서는 [Brand Concierge 도움말](../documentation/overview.md)을 참조하세요.

## 관련 자습서

* [Adobe CX Enterprise Coworker을 사용하여 대화 내보내기](exporting-conversations-using-adobe-cx-enterprise-coworker.md)
