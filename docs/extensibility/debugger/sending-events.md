---
title: "이벤트 전송 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 이벤트 전송"
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# 이벤트 전송
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거가 디버그 엔진 \(DE\)와 통신 하기 위한 메커니즘에서 DCOM을 기반으로 하는 이벤트 모델입니다.  COM 개체로 보낸 이벤트 및 각 이벤트 다음을 지정 하는 매개 변수가 있습니다.  
  
-   이벤트는 호출 하는 DE.  
  
-   변경 내용에 대 한 설명을 합니다.  
  
-   프로세스, 프로그램 및 이벤트가 발생 하는 컨텍스트를 식별 하는 스레드 정보  프로세스를 DE에서 보낸 이벤트에 대 한 전송 되지 않습니다.  
  
-   이벤트 종류 이벤트 동기 인지 비동기 인지 여부를 나타냅니다.  
  
 이 메서드를 사용 하 여 모든 디버그 이벤트 전송 됩니다  [IDebugEventCallback2::Event](../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## 단원 내용  
 [이벤트 소스](../../extensibility/debugger/event-sources-visual-studio-sdk.md)  
 두 원본 이벤트의 설명: 디버그 엔진 \(DE\) 및 세션 매니저 \(SDM\)을 디버깅 합니다.  
  
 [지원 되는 이벤트 유형](../../extensibility/debugger/supported-event-types.md)  
 현재 지원 되는 이벤트 형식에 설명 합니다: 비동기 및 동기.  
  
 [이벤트 설명](../../extensibility/debugger/event-descriptions.md)  
 이벤트와 사용 하는 이유를 정의합니다.  
  
## 관련 단원  
 [사용자 지정 디버그 엔진을 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 인터프리터 또는 운영 체제를 디버깅 서비스를 제공 하는 DE 방법에 대해 설명 합니다.