---
title: "IDebugCodeContext2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCodeContext2"
helpviewer_keywords: 
  - "IDebugCodeContext2 인터페이스"
ms.assetid: 3670439e-2171-405d-9d77-dedb0f1cba93
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugCodeContext2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 코드의 시작 위치를 나타냅니다.  대부분의 런타임 아키텍처에 대 한 오늘날, 코드 컨텍스트 중에서 프로그램의 실행 스트림 주소로 생각할 수 있습니다.  
  
## 구문  
  
```  
IDebugCodeContext2 : IDebugMemoryContext2  
```  
  
## 구현자 참고 사항  
 디버그 엔진 문서 위치에 대 한 코드 명령 위치 관계를이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 많은 인터페이스의 메서드에 가장 일반적으로이 인터페이스를 반환 합니다 [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md).  또한 광범위 하 게 함께 사용은 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) 중단점 확인 정보에서와 함께 인터페이스.  
  
## 메서드에서 Vtable 순서  
 메서드 외에 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)|현재 코드 컨텍스트에 해당 문서 컨텍스트를 가져옵니다.|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugcodecontext2-getlanguageinfo.md)|이 코드 컨텍스트에 대 한 언어 정보를 가져옵니다.|  
  
## 설명  
 가장 큰 차이점은 `IDebugCodeContext2` 인터페이스와는 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 인터페이스 되는 `IDebugCodeContext2` 항상 명령 맞춤입니다.  따라서는 `IDebugCodeContext2` 명령의 시작 부분에 있지만 항상 가리키는 `IDebugMemoryContext2` 메모리 런타임 아키텍처에서 모든 바이트를 나타낼 수도 있습니다.  `IDebugCodeContext2`기본 저장소 크기 \(바이트 일반적 으로\)가 아니라 지침 증가 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [CanSetNextStatement](../../../extensibility/debugger/reference/idebugthread2-cansetnextstatement.md)   
 [SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)   
 [다음](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-next.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)