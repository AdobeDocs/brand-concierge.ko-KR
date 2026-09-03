---
title: 개발자 및 사용자 지정 안내서
description: Brand Concierge Web SDK 및 Web Client를 설치하고, 모양 및 콘텐츠를 사용자 지정하고, 클라이언트측 이벤트를 처리하고, 대화 데이터를 내보내는 방법에 대해 알아봅니다.
role: Developer,Admin
level: Experienced
toc: true
source-git-commit: 13db0491c987a08492820ac216e20feb87f30e44
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 4%

---


# 개발자 및 사용자 지정 안내서 {#developer-customization-guide}

이 안내서는 Brand Concierge 배포를 구현하거나 사용자 정의하는 개발자 및 기술 팀을 위한 것입니다. 웹 SDK 및 웹 클라이언트 설치, 모양 및 콘텐츠 사용자 지정, 콜백 함수를 통한 클라이언트측 이벤트 수신, 보고를 위한 대화 데이터 내보내기 등에 대해 설명합니다.

## 웹 SDK 및 웹 클라이언트 설치 {#installation}

### 사전 요구 사항 {#prerequisites}

* 조직은 Adobe Experience Platform(AEP) 고객입니다.
* 페이지는 Adobe Experience Platform 웹 SDK으로 계측됩니다.
* 페이지에 사용된 데이터 스트림 ID가 Brand Concierge에 대해 활성화됩니다.

### 1단계: 웹 SDK 삽입 {#inject-web-sdk}

페이지의 `<head>` 섹션에 다음 내용을 추가하십시오.

```html
<script>
  !(function (n, o) {
    o.forEach(function (o) {
      n[o] ||
        ((n.__alloyNS = n.__alloyNS || []).push(o),
        (n[o] = function () {
          var u = arguments;
          return new Promise(function (i, l) {
            n[o].q.push([i, l, u]);
          });
        }),
        (n[o].q = []));
    });
  })(window, ["alloy"]);
</script>
<script src="https://cdn1.adoberesources.net/alloy/2.31.1/alloy.min.js"></script>
```

### 2단계: 웹 클라이언트 삽입 {#inject-web-client}

`<head>` 섹션에 있는 웹 SDK 스크립트 뒤에 다음을 추가하십시오.

```html
<script src="https://experience.adobe.net/solutions/experience-platform-brand-concierge-web-agent/static-assets/main.js"></script>
```

### 3단계: 웹 SDK 구성 {#configure-web-sdk}

아래 자리 표시자 대신 조직의 고유 값으로 `alloy("configure", ...)`을(를) 호출하십시오.

```javascript
alloy("configure", {
  defaultConsent: "in",
  edgeDomain: "edge.adobedc.net",
  edgeBasePath: "ee",
  datastreamId: "YOUR_DATASTREAM_ID",
  orgId: "YOUR_IMS_ORG_ID",
  debugEnabled: true,
  idMigrationEnabled: false,
  thirdPartyCookiesEnabled: false,
  prehidingStyle: ".personalization-container { opacity: 0 !important }",
  onBeforeEventSend: (options) => {
    const x = options.xdm;
    const params = new URLSearchParams(window.location.search);
    const titleParam = params.get("title");
    if (titleParam) {
      x.web.webPageDetails.name = titleParam;
    } else {
      x.web.webPageDetails.name = "default-page";
    }
    return true;
  }
});
alloy("sendEvent", {});
```

| 필드 | 설명 |
|---|---|
| `datastreamId` | Brand Concierge에 대해 활성화된 이 페이지에 대해 구성된 데이터 스트림 ID입니다. |
| `orgId` | 컨시어지가 구성된 IMS 조직 ID. |
| `debugEnabled` | 통합이 확인되면 프로덕션에서 `false`(으)로 설정합니다. |
| `prehidingStyle` | 스타일이 지정되지 않은 콘텐츠가 번쩍이는 것을 방지하기 위해 개인화 콘텐츠가 로드되기 전에 적용된 CSS입니다. |
| `onBeforeEventSend` | XDM 페이로드가 전송되기 전에 이를 수정하기 위한 선택적 후크입니다. 일반적으로 페이지 이름 또는 컨텍스트를 설정하는 데 사용됩니다. |

### 4단계: 웹 클라이언트 초기화 {#initialize-web-client}

웹 SDK 구성 호출 후 부트스트랩 API를 호출하여 웹 클라이언트를 초기화합니다.

```javascript
window.adobe.concierge.bootstrap({
  instanceName: "alloy",
  stylingConfigurations: window.styleConfigurations,
  selector: "#brand-concierge-mount"
});
```

| 매개 변수 | 유형 | 필수 여부 | 설명 |
|---|---|---|---|
| `instanceName` | string | 예 | 웹 SDK 인스턴스 이름입니다. |
| `stylingConfigurations` | JSON 개체 | 예 | 웹 클라이언트 스타일 구성([시각적 및 콘텐츠 사용자 지정](#customization) 참조). |
| `selector` | string | 예 | 웹 클라이언트가 마운트하는 HTML 요소에 대한 CSS 선택기입니다. |
| `onEvent` | 함수 | 아니오 | 클라이언트측 이벤트에 대한 콜백([클라이언트측 이벤트 및 콜백 함수](#events) 참조). |

## 시각적 및 콘텐츠 사용자 지정 {#customization}

`bootstrap()`(으)로 전달된 `stylingConfigurations` 개체는 웹 클라이언트 전체에서 모양, 동작 및 텍스트를 제어합니다. 여러 영역으로 구성됩니다.

### 메타데이터 {#metadata}

```javascript
"metadata": {
  "brandName": "Your Brand",
  "version": "1.0.0",
  "language": "en-US",
  "namespace": "brand-concierge"
}
```

### 비헤이비어 {#behavior}

개별 채팅 기능의 기능 동작을 제어합니다.

```javascript
"behavior": {
  "input": {
    "enableVoiceInput": true
  },
  "chat": {
    "messageAlignment": "left",
    "messageWidth": "80%"
  },
  "privacyNotice": {
    "title": "Privacy Notice",
    "text": "By using this automated chatbot, you consent that any personal information you provide in the chat may be collected, used, analyzed, disclosed, and retained by Adobe and its service providers, in accordance with the Adobe Privacy Policy. Please do not enter any sensitive personal information (e.g., financial or health data)."
  },
  "disclaimer": {
    "attachWithInput": true
  },
  "chatTranscript": {
    "enabled": true,
    "maxSessions": 1,
    "maxMessagesPerSession": 20,
    "cleanupInterval": 24
  },
  "meetingForm": {
    "fieldsPerRow": 2,
    "title": { "text": "Schedule meeting", "alignment": "left" },
    "subtitle": { "text": "I'd be happy to help you schedule a meeting! Please fill out the form below, and we'll follow up with a calendar to confirm your day and time.", "alignment": "left" },
    "buttons": {
      "submit": { "text": "Schedule meeting", "alignment": "left" },
      "cancel": { "text": "Cancel", "alignment": "left" }
    }
  },
  "calendarWidget": {
    "title": { "text": "Book a meeting", "alignment": "left" },
    "subtitle": { "text": "Thanks! Here's a calendar where you can choose a time that works best for your schedule:", "alignment": "left" },
    "postTitle": { "text": "Once confirmed, you'll receive a calendar invite with all the details.", "alignment": "left" },
    "buttons": {
      "confirm": { "text": "Schedule a meeting", "alignment": "left" },
      "cancel": { "text": "Cancel", "alignment": "left" }
    }
  }
}
```

### 면책 조항 {#disclaimer}

```javascript
"disclaimer": {
  "text": "AI responses may be inaccurate or misleading. Be sure to double check answers and sources."
}
```

### 텍스트 문자열 {#text-strings}

`text` 개체를 통해 모든 사용자 대상 복사본을 재정의할 수 있습니다. 일반 키:

| 키 | 용도 |
|---|---|
| `welcome.heading` / `welcome.subheading` | 시작 화면 제목 및 하위 텍스트 |
| `input.placeholder` | 입력 필드 자리 표시자 텍스트 |
| `input.messageInput.aria` / `input.send.aria` / `input.mic.aria` | 입력 컨트롤의 접근성 레이블 |
| `error.network` / `error.general` | 방문자에게 표시되는 오류 메시지 |
| `loading.message` | 응답이 생성되는 동안 표시되는 텍스트 |
| `feedback.dialog.title.positive` / `.negative` | 피드백 대화 상자 제목 |
| `feedback.dialog.question.positive` / `.negative` | 피드백 대화 상자 프롬프트 텍스트 |
| `feedback.toast.success` | 피드백이 제출된 후 확인 알림 |
| `feedback.thumbsUp.aria` / `feedback.thumbsDown.aria` | 피드백 단추의 접근성 레이블 |

### 배열 {#arrays}

구성 가능한 콘텐츠 목록:

```javascript
"arrays": {
  "welcome.examples": [
    {
      "text": "I want to edit and enhance my photos",
      "image": "https://example.com/idea-1.png",
      "backgroundColor": "#66BFE7"
    }
  ],
  "feedback.positive.options": [
    "Helpful and relevant recommendations",
    "Clear and easy to understand",
    "Friendly and conversational tone",
    "Visually appealing presentation",
    "Other"
  ],
  "feedback.negative.options": [
    "Not helpful or relevant",
    "Confusing or unclear",
    "Too formal or robotic",
    "Poor visual presentation",
    "Other"
  ]
}
```

### 자산 {#assets}

```javascript
"assets": {
  "icons": {
    "company": "<svg>...</svg>"
  }
}
```

### 테마 {#theme}

색상, 글꼴 및 레이아웃을 제어하는 CSS 사용자 지정 속성:

```css
"theme": {
  "--color-primary": "#1473e6",
  "--color-primary-hover": "#0056b3",
  "--color-button-primary": "#3B63FB",
  "--color-accent": "#9085ED",
  "--color-button-submit": "#4759e6",
  "--color-button-submit-hover": "#3a4bce",
  "--color-message-user": "#1473e6",
  "--font-family": "'Adobe Clean', adobe-clean, 'Trebuchet MS', sans-serif",
  "--main-container-background": "linear-gradient(135deg, #66ccff, #cc99ff, #ffcc99, #ccff99)",
  "--submit-button-fill-color": "white",
  "--card-text-background": "var(--color-background)",
  "--card-text-border-radius": "var(--border-radius-card)",
  "--message-concierge-link-decoration": "underline",
  "--message-max-width": "100%"
}
```

## 클라이언트측 이벤트 및 콜백 함수 {#events}

이벤트 콜백 시스템을 사용하면 페이지에서 웹 클라이언트 라이프사이클 이벤트, 사용자 상호 작용, 응답, 피드백 및 오류를 실시간으로 관찰할 수 있으며, 이는 Adobe Analytics, Google Analytics 또는 기타 서드파티 시스템에 참여 데이터를 전송하는 데 유용합니다.

### 주요 특성 {#key-characteristics}

* **단일 콜백** — `onEvent` 함수 하나는 `event.eventType`으로 구분되는 모든 이벤트 형식을 수신합니다.
* **읽기 전용** — 이벤트 데이터는 복제된 스냅샷이므로 클라이언트의 동작을 수정하는 데 사용할 수 없습니다.
* **오류 격리** — 콜백 내에서 throw된 예외가 포착되고 기록되며 웹 클라이언트를 중단하지 않습니다.
* **`bootstrap()`**&#x200B;을(를) 통해 등록됨 — `onBeforeEventSend`과(와) 같은 방식으로 전달되었습니다.

### 빠른 시작 {#quick-start}

```javascript
window.adobe.concierge.bootstrap({
  instanceName: "my-instance",
  selector: "#brand-concierge-mount",
  stylingConfigurations: { /* ... */ },
  onEvent: (event) => {
    console.log(event.eventType, event.timestamp, event.data);
  }
});
```

### 이벤트 유형별 필터링 {#filtering}

```javascript
onEvent: (event) => {
  switch (event.eventType) {
    case "query:submitted":
      console.log("User query:", event.data.query);
      break;
    case "response:completed":
      console.log("Response received:", event.data.conversationId);
      break;
    case "card:clicked":
      console.log("Card clicked:", event.data.element.entity_info.productName);
      break;
    case "error:occurred":
      console.log("Error:", event.data.errorMessage);
      break;
  }
}
```

### 이벤트 유형 {#event-types}

| 이벤트 유형 | 값 | 카테고리 | 실행 시 |
|---|---|---|---|
| `WEBCLIENT_INITIALIZED` | `webclient:initialized` | 라이프사이클 | 클라이언트가 초기화(DOM 마운트, 콘텐츠 로드)를 완료합니다. |
| `QUERY_SUBMITTED` | `query:submitted` | 사용자 상호 작용 | 사용자가 메시지(입력 또는 제안) 제출 |
| `PROMPT_SUGGESTION_CLICKED` | `promptSuggestion:clicked` | 사용자 상호 작용 | 사용자가 즉석 제안 알약을 클릭합니다. |
| `CARD_CLICKED` | `card:clicked` | 사용자 상호 작용 | 사용자가 카드를 클릭합니다. |
| `HISTORY_CLEARED` | `history:cleared` | 사용자 상호 작용 | 사용자가 채팅 기록을 지웁니다. |
| `RESPONSE_STARTED` | `response:started` | 응답 | API에서 첫 번째 스트리밍 청크 도착 |
| `RESPONSE_COMPLETED` | `response:completed` | 응답 | 전체 응답이 수신되고 렌더링됩니다. |
| `CARDS_RENDERED` | `cards:rendered` | 응답 | 카드(단일 이미지 또는 캐러셀) 렌더링 완료 |
| `FEEDBACK_SUBMITTED` | `feedback:submitted` | 피드백 | 사용자가 피드백 양식(세부 정보가 있는 엄지 손가락 위/아래)을 제출함 |
| `ERROR_OCCURRED` | `error:occurred` | 오류 | 오류가 발생합니다(네트워크, API 또는 런타임). |

### 라이프사이클 이벤트 {#lifecycle-events}

클라이언트가 완전히 초기화된 후 `webclient:initialized`이(가) 실행됩니다. 콘텐츠 로드, CSS 주입, DOM에서 렌더링된 채팅 UI.

```json
{
  "eventType": "webclient:initialized",
  "timestamp": 1741638123789,
  "data": {
    "instanceName": "my-instance"
  }
}
```

### 사용자 상호 작용 이벤트 {#user-interaction-events}

`query:submitted`은(는) 사용자가 입력한 메시지를 프롬프트 제안 또는 위젯 옵션에서 제출하면 실행됩니다.

```json
{
  "eventType": "query:submitted",
  "timestamp": 1741638124000,
  "data": {
    "query": "What photo editing tools do you offer?"
  }
}
```

`promptSuggestion:clicked`은(는) 사용자가 프롬프트 제안 알약을 클릭할 때 실행됩니다. 후속 `query:submitted` 이벤트에서 *이전*&#x200B;에 실행됩니다.

```json
{
  "eventType": "promptSuggestion:clicked",
  "timestamp": 1741638124100,
  "data": {
    "suggestion": "Tell me more about Photoshop"
  }
}
```

`card:clicked`은(는) 사용자가 카드를 클릭할 때 실행됩니다.

```json
{
  "eventType": "card:clicked",
  "timestamp": 1741638124200,
  "data": {
    "element": {
      "entity_info": {
        "productName": "Adobe Photoshop",
        "productDescription": "Photo editing software",
        "productPageURL": "https://www.adobe.com/products/photoshop.html",
        "productImageURL": "https://example.com/photoshop.png"
      }
    }
  }
}
```

`history:cleared`은(는) 사용자가 [채팅 기록 지우기] 단추를 클릭할 때 실행됩니다.

```json
{
  "eventType": "history:cleared",
  "timestamp": 1741638124400,
  "data": {}
}
```

### 응답 이벤트 {#response-events}

`response:started`은(는) API에서 첫 번째 스트리밍 청크가 도착할 때 실행됩니다.

```json
{
  "eventType": "response:started",
  "timestamp": 1741638125000,
  "data": {
    "conversationId": "conv-abc-123",
    "interactionId": "int-xyz-456"
  }
}
```

`response:completed`은(는) 전체 응답을 받으면 실행됩니다.

```json
{
  "eventType": "response:completed",
  "timestamp": 1741638126000,
  "data": {
    "conversationId": "conv-abc-123",
    "interactionId": "int-xyz-456"
  }
}
```

카드가 DOM에서 렌더링된 후 `cards:rendered`이(가) 실행됩니다. 이 변수는 `response:completed`과(와) 별도로 실행되며 사용된 표시 모드를 나타냅니다.

```json
{
  "eventType": "cards:rendered",
  "timestamp": 1741638126100,
  "data": {
    "element": [
      { "entity_info": { "productName": "Adobe Photoshop" } },
      { "entity_info": { "productName": "Adobe Illustrator" } }
    ],
    "displayMode": "carousel"
  }
}
```

### 피드백 이벤트 {#feedback-events}

`feedback:submitted`은(는) 사용자가 피드백 양식을 완료하고 제출할 때(엄지 손가락을 위/아래로 올린 후) 실행됩니다.

```json
{
  "eventType": "feedback:submitted",
  "timestamp": 1741638127000,
  "data": {
    "conversationId": "conv-abc-123",
    "interactionId": "int-xyz-456",
    "feedbackType": "negative",
    "selectedOptions": ["Incorrect information", "Not relevant"],
    "notes": "The response did not address my question about pricing."
  }
}
```

### 오류 이벤트 {#error-events}

`error:occurred`은(는) 클라이언트에서 네트워크, API 또는 런타임 오류가 발생할 때 실행됩니다.

```json
{
  "eventType": "error:occurred",
  "timestamp": 1741638128000,
  "data": {
    "errorMessage": "Something went wrong. Please try again."
  }
}
```

### 이벤트 오브젝트 구조 {#event-object-structure}

모든 이벤트는 동일한 최상위 셰이프를 공유합니다.

```typescript
interface BrandConciergeEvent {
  eventType: string;  // e.g. "query:submitted"
  timestamp: number;  // Unix epoch, milliseconds
  data: object;       // Event-specific payload
}
```

### 데이터 유형 참조: 요소(제품 카드) {#element-reference}

```typescript
interface Element {
  id?: string;
  type?: string;
  entity_info: {
    productName: string;
    productDescription: string;
    description: string;
    productPageURL: string;
    details: string;
    backgroundColor: string;
    learningResource: string;
    productImageURL: string;
    logo: string;
    variants?: Record<string, ElementVariant>;
    primary: ElementAction;
    secondary: ElementAction;
  };
}

interface ElementAction {
  label: string;
  url: string;
}
```

### 모범 사례 {#best-practices}

* **분석 및 모니터링에 사용합니다.** 참여, 쿼리 패턴 및 제품 관심 사항을 추적하고, `error:occurred`을(를) 오류 추적 서비스로 전달하고, 전환 분석을 위해 카드 클릭을 추적합니다.
* **콜백을 빠르게 유지하세요.** 기본 스레드에서 동기적으로 실행되므로 네트워크 호출을 차단하지 마십시오.

```javascript
// Good — fire and forget
onEvent: (event) => {
  navigator.sendBeacon("/analytics", JSON.stringify(event));
}

// Avoid — blocking network call
onEvent: async (event) => {
  await fetch("/analytics", { body: JSON.stringify(event) });
}
```

* **상태 컴퓨터에 대해 엄격한 이벤트 순서를 사용하지 마십시오**. 이벤트가 논리 시퀀스에서 실행되지만 순서를 가정하는 대신 `conversationId` 및 `interactionId`을(를) 사용하여 관련 이벤트를 상호 연결합니다.
* **콜백 내의 오류를 처리합니다.** 클라이언트가 콜백 오류를 격리하고 기록하지만 콜백 내의 처리되지 않은 오류는 여전히 분석 데이터를 잃을 수 있습니다.

```javascript
onEvent: (event) => {
  try {
    myAnalytics.track(event);
  } catch (e) {
    console.warn("Analytics tracking failed", e);
  }
}
```

## AEP 쿼리 서비스를 사용하여 대화 내보내기 {#export-conversations}

Brand Concierge은 대화 데이터(프롬프트, 응답 및 피드백)를 Adobe Experience Platform(AEP) 데이터 세트에 기록합니다. SQL(쿼리 서비스)로 직접 쿼리하여 사용자 지정 보고서를 작성할 수 있습니다.

### 데이터 세트 및 테이블 이름 찾기 {#find-dataset}

1. Adobe Experience Platform을 엽니다.

1. **[!UICONTROL 데이터 세트]**(으)로 이동합니다.

1. Brand Concierge 관련 데이터 세트를 나열하려면 `cja_brand_concierge`을(를) 검색합니다.

1. 필요한 데이터 세트를 엽니다(예: 응답이 다른 흐름과 비교하여 둘 이상 있는 경우).

1. 데이터 집합 세부 사항 보기에서 쿼리 서비스에 사용되는 **[!UICONTROL 테이블 이름]**&#x200B;을(를) 찾고 샘플 또는 미리 보기 데이터를 검사하여 열(프롬프트, 응답, 피드백, 타임스탬프 등)을 확인합니다.

>[!NOTE]
>
>테이블 이름은 각 데이터 세트에 연결되며 환경 및 샌드박스별로 다릅니다. 샌드박스 또는 배포가 여러 개인 경우 올바른 샌드박스에서 이 단계를 반복하여 데이터가 작성된 테이블 이름을 일치시킵니다.

### 예제 쿼리 {#example-query}

```sql
SELECT *
FROM cja_brand_concierge_responses_dataset_5f5105bd_1c38_4ebc_8505_bd
WHERE timestamp >= TIMESTAMP '2026-03-16 00:00:00'
  AND timestamp <= NOW()
ORDER BY timestamp ASC;
```

>[!IMPORTANT]
>
>위의 표 이름은 단지 그림일 뿐입니다. 하드 코딩하지 마십시오. 먼저 AEP에서 데이터 세트의 실제 테이블 이름을 확인하고([데이터 세트 및 테이블 이름 찾기](#find-dataset) 참조), 보고 요구 사항에 맞게 시간 필터, 정렬 순서 또는 기타 절을 조정하십시오. 데이터 세트와 동일한 샌드박스를 사용하여 조직의 쿼리 서비스 워크플로우(UI, API 또는 연결된 클라이언트)에서 쿼리를 실행합니다.

### 쿼리 서비스 UI에서 쿼리 실행 {#run-query-ui}

보고를 위해 수동 데이터 가져오기가 필요한 경우 쿼리 서비스 UI를 통해 결과를 직접 실행하고 다운로드할 수 있습니다.

1. Adobe Experience Platform에서 **[!UICONTROL 쿼리]**(으)로 이동합니다.

1. 편집기에 쿼리를 입력하고 **[!UICONTROL 쿼리 실행]**&#x200B;을 클릭합니다.

1. 쿼리가 완료되면 편집기 아래의 **[!UICONTROL 결과]** 탭에 결과가 표시됩니다. 여기에서 결과를 다운로드할 수 있습니다.

### 추가 읽기 {#further-reading}

* [쿼리 서비스 API 설명서](https://experienceleague.adobe.com/ko/docs/experience-platform/query/home){target="_blank"} — 이 안내서와 별도로 시간이 지남에 따라 변경되는 쿼리 서비스 동작, 제한, 인증 및 API 경로에 대한 Adobe의 공식 참조입니다.
