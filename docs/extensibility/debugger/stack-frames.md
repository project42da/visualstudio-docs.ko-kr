---
title: "스택 프레임 | Microsoft Docs"
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
  - "디버깅 하는 스택 프레임"
  - "디버깅 [디버깅 SDK], 스택 프레임"
  - "스택 프레임"
ms.assetid: b5e439d4-1e9d-4e13-9cad-bb8b136d4ca8
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 스택 프레임
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거 아키텍처 측면에서  **스택 프레임**:  
  
-   스레드의 실행 컨텍스트를 제공 하는 스택 추상화가입니다.  스레드는 항상 함수 내에서 실행 됩니다.  스택 프레임에는 지역 변수, 함수 및 인수 값입니다.  Visual Studio 디버깅 하려면 언어 또는 디버깅 중인 환경 스택 프레임을 지원 해야 합니다.  
  
-   수 있습니다 둘 다 식별 하 고 자체를 설명 하 고 관련된 스레드 돌아갈 수 있습니다.  스택 프레임을 현재 명령 포인터와는 관련된 설명서를 나타내는 코드 컨텍스트 및 식 평가 컨텍스트에 반환할 수도 있습니다.  
  
-   이름, 형식 및 값을 지역 변수 및 인수를 설명 하 고 다양 한 IDE 디버그 창에 표시 되는 속성이 있습니다.  
  
-   표시 되는 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) 일반적으로 디버그 엔진 \(DE\) 또는 가상 컴퓨터의 결과로 스레드를 실행 하 여 만든 인터페이스를 합니다.  
  
## 참고 항목  
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)