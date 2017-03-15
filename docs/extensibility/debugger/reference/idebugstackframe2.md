---
title: "IDebugStackFrame2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugStackFrame2"
helpviewer_keywords: 
  - "IDebugStackFrame2 인터페이스"
ms.assetid: bd212a6a-dcc6-4756-a77a-e8dfda38b104
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# IDebugStackFrame2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스에 특정 스레드는 호출 스택에서 한 스택 프레임을 나타냅니다.  
  
## 구문  
  
```  
IDebugStackFrame2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 스택 프레임을 표시 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 를 검색 하는 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) 인터페이스입니다.  호출 [다음](../../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md) 를 검색 하는 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 포함 구조체는 `IDebugStackFrame2` 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugStackFrame2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|이 스택 프레임에 대 한 코드 컨텍스트를 가져옵니다.|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|이 스택 프레임의 문서 컨텍스트를 가져옵니다.|  
|[GetName](../../../extensibility/debugger/reference/idebugstackframe2-getname.md)|스택 프레임의 이름을 가져옵니다.|  
|[GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)|스택 프레임에 대 한 설명을 가져옵니다.|  
|[GetPhysicalStackRange](../../../extensibility/debugger/reference/idebugstackframe2-getphysicalstackrange.md)|스택 프레임과 연결 된 실제 주소는 컴퓨터에 종속 표현을 가져옵니다.|  
|[GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)|스레드 및 스택 프레임의 현재 컨텍스트 내에서 식 계산을 수행 하는 데 평가 컨텍스트를 가져옵니다.|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugstackframe2-getlanguageinfo.md)|스택 프레임과 연결 된 언어를 가져옵니다.|  
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)|스택 프레임과 연결 된 속성에 대 한 설명을 가져옵니다.|  
|[EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)|열거자에 대 한 스택 프레임 속성을 만듭니다.|  
|[GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md)|스택 프레임과 연결 된 스레드를 가져옵니다.|  
  
## 설명  
 디버깅 중인 프로그램 \(하나는 사용자가 설정한 중단점 또는 예외 발생 한\)는 중단점에서 중지 된만 경우이 인터페이스를 가져옵니다.  이 인터페이스에서 식을 계산 하려면 식 컨텍스트를 얻을 수 있습니다, 레지스터 목록을 반환할 수 있습니다, 또는 호출 스택의 얻 및 검사 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)