---
title: "호출 스택 평가 | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK], 호출 스택 평가"
  - "호출 스택, 평가"
ms.assetid: 373d6b49-0459-4cce-816e-05745a44fe49
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# 호출 스택 평가
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

중단 모드에서 스택 프레임의 호출 스택 표시 하려면 반드시 구현 해야는 [EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 메서드가 있습니다.  
  
## 평가의 방법  
 간단한 디버그 엔진에 대해 \(DE\) 스택 프레임 하나만 있을 수 있습니다.  중단 모드에서 스택 프레임을 검사 하려면 다음 메서드를 구현 해야 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md).  
  
|메서드|설명|  
|---------|--------|  
|[GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|코드 컨텍스트를 스택 프레임을 가져옵니다.  현재 스택 프레임의 명령 포인터를 코드 컨텍스트를 나타냅니다.|  
|[GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|문서 컨텍스트를 스택 프레임을 가져옵니다.  문서 컨텍스트 스택 프레임에 대 한 소스 코드의 현재 위치를 나타냅니다.  에 프로그램이 중지 되었을 때 소스 코드를 보는 데 필요 합니다.|  
  
 이러한 방법을 여러 가지 컨텍스트 관련 인터페이스 및 메서드를 구현을 해야합니다.  반드시 구현 해야 하므로, 해당 [GetDocumentContext](../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md) 메서드 및 다음 메서드를 [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md).  
  
|메서드|설명|  
|---------|--------|  
|[GetStatementRange](../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|파일 범위를 문을 문서 컨텍스트를 가져옵니다.|  
  
 코드 컨텍스트 열거 하의 모든 메서드를 구현 해야 합니다 [IEnumDebugCodeContexts2](../../extensibility/debugger/reference/ienumdebugcodecontexts2.md).  
  
## 참고 항목  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)