---
title: "종료 및 분리 | Microsoft Docs"
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
  - "프로그램 종료 이벤트"
  - "프로그램에서 분리 되는 디버그 엔진"
ms.assetid: 268c1e51-6363-45d1-964c-1ab99bdfa4f9
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# 종료 및 분리
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 정상 종료를 설명합니다.  
  
## 토론  
 이후에  [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 또는  [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) 인터페이스 계속 없음 중단점, 예외, 런타임 오류 디버깅 중인 프로그램 디버깅으로 응용 프로그램에 무한 루프가 완료 될 때까지 실행 될 경우.  정상 종료입니다.  
  
 보내야 합니다는  [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) 정상 종료를 구현할 수 있습니다.  이것을 구현 하려면 필요는  [IDebugProgramDestroyEvent2::GetExitCode](../../extensibility/debugger/reference/idebugprogramdestroyevent2-getexitcode.md) 메서드.  
  
## 참고 항목  
 [사용자 지정 디버그 엔진 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)