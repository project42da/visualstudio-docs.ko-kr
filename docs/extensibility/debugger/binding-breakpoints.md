---
title: "바인딩 중단점 | Microsoft Docs"
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
  - "중단점, 바인딩"
ms.assetid: 70737387-c52f-4dae-8865-77d4b203bf25
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 바인딩 중단점
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자 중단점을 설정 하는 경우 아마도 f9 키를 눌러 IDE는 요청을 공식화 한 중단점을 만들려면 디버그 세션 알려줍니다.  
  
## 중단점 설정  
 중단점 설정 코드 또는 중단점에서 영향을 받는 데이터는 아직 사용할 수 없습니다 때문에 두 단계 프로세스입니다.  먼저 중단점에서 설명한 후 코드 또는 데이터를 사용할 수 있게 되 면 다음,이 해당 코드 또는 데이터에는 다음과 같이 연결 해야 합니다.  
  
1.  중단점 \(DEs\) 관련 디버깅 엔진에서 요청 된 고 대로 다음 중단점이 코드 또는 데이터에 바인딩됩니다.  
  
2.  중단점 요청 관련 모든 Des로 보내는 디버그 세션으로 전송 됩니다.  중단점을 처리 하도록 선택 된 DE 해당 하는 보류 중인 중단점을 만듭니다.  
  
3.  디버그 세션 보류 중단점을 수집 하 고이 디버그 패키지 \(Visual Studio 디버깅 구성\)에 다시 보냅니다.  
  
4.  디버그 패키지 디버그 세션을 보류 중단점이 코드 또는 데이터를 바인딩할 수 묻는 메시지가 나타납니다.  디버그 세션 관련 모든 Des에이 요청을 보냅니다.  
  
5.  DE 중단점을 바인딩할 수 있는 경우 중단점 이벤트를 디버그 세션에 바인딩된 전송 합니다.  그렇지 않으면 중단점 오류 이벤트 대신 보냅니다.  
  
## 보류 중단점  
 보류 중단점 여러 코드 위치를 바인딩할 수 있습니다.  예를 들어, 줄의 소스 코드를 c \+ \+ 템플릿 서식 파일에서 생성 된 모든 코드 시퀀스에 바인딩할 수 있습니다.  디버그 세션에서 중단점이 바인딩된 이벤트 중단점 이벤트를 보낼 때에 바인딩되는 코드 컨텍스트를 열거할 수 있습니다.  여러 중단점 이벤트 각 바인딩 요청에 대 한 바인딩되는 DE 보낼 수 있도록 자세한 코드 컨텍스트 나중에 바인딩할 수 있습니다.  그러나, DE는 bind 요청에 대해 하나의 중단점 오류 이벤트를 보내야 합니다.  
  
## 구현  
 프로그래밍 방식으로 디버그 패키지 디버그 세션 매니저 \(SDM\)를 호출 하 고 해당는 [IDebugBreakpointRequest2](../../extensibility/debugger/reference/idebugbreakpointrequest2.md) 인터페이스를 래핑하는 [BP\_REQUEST\_INFO](../../extensibility/debugger/reference/bp-request-info.md) 설정할 수 중단점을 설명 하는 구조입니다.  다양 한 형식의 중단점 하더라도 결국 코드 또는 데이터 컨텍스트를 해결 합니다.  
  
 호출 하 여이 호출을 각 관련 DE은 SDM 전달의 [CreatePendingBreakpoint](../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) 메서드.  중단점을 처리 하는 DE를 선택 하면 생성 하 고 반환 된 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) 인터페이스입니다.  SDM을 이러한 인터페이스를 수집 하 고 이러한 단일 디버그 패키지로 전달 `IDebugPendingBreakpoint2` 인터페이스입니다.  
  
 지금까지 이벤트가 생성 된.  
  
 그런 다음 디버그 패키지를 호출 하 여 보류 중단점을 코드 또는 데이터를 바인딩할 시도 [바인딩](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md), DE에서 구현 합니다.  
  
 중단점이 바인딩되는 경우는 DE 보냅니다 있는 [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) 디버그 패키지 이벤트 인터페이스입니다.  모든 코드 컨텍스트 \(또는 하나의 데이터 컨텍스트\)를 열거 하는이 인터페이스를 호출 하 여 중단점을 바인딩할 디버그 패키지 사용 [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md)를 하나 이상 반환 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) 인터페이스입니다.  [GetBreakpointResolution](../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md) 인터페이스 반환은 [IDebugBreakpointResolution2](../../extensibility/debugger/reference/idebugbreakpointresolution2.md) 인터페이스, 및 [GetResolutionInfo](../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) 반환는 [BP\_RESOLUTION\_INFO](../../extensibility/debugger/reference/bp-resolution-info.md) 코드 또는 데이터 컨텍스트를 포함 하는 공용 구조체입니다.  
  
 DE 중단점을 바인딩할 수 없으면 단일 보냅니다 [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) 디버그 패키지 이벤트 인터페이스입니다.  디버그 패키지를 호출 하 여 오류 유형 \(오류 또는 경고\) 및 정보 메시지가 검색 [GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md), 그 [GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) 및 [GetResolutionInfo](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md).  이 반환 된 [BP\_ERROR\_RESOLUTION\_INFO](../../extensibility/debugger/reference/bp-error-resolution-info.md) 오류 유형 및 메시지를 포함 하는 구조입니다.  
  
 중단점을 처리는 DE 바인딩할 수 없습니다 경우 형식의 오류가 반환 `BPET_TYPE_ERROR`.  오류 대화 상자를 표시 하 여 디버그 패키지를 응답 하 고 IDE에서 느낌표 문자 모양 내부 소스 코드 줄의 왼쪽에 있는 중단점 문자를 배치 합니다.  
  
 DE 바인딩할 수 있는 경우는 DE 중단점을 처리 하 고, 하지만 몇 가지 다른 바인딩할 수 없습니다 경고를 반환 합니다.  IDE에 질문 기호 안에 소스 코드 줄의 왼쪽에 있는 중단점 문자를 배치 하 여 응답 합니다.  
  
## 참고 항목  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)