---
title: "IDebugStackFrame3 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugStackFrame3"
helpviewer_keywords: 
  - "IDebugStackFrame3 인터페이스"
ms.assetid: 39af2f57-0a01-42b8-b093-b7fbc61e2909
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugStackFrame3
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스를 확장 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 차단된 예외를 처리할 수 있습니다.  
  
## 구문  
  
```  
IDebugStackFrame3 : IDebugStackFrame2  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\)를 구현 하는 동일한 개체에서이 인터페이스는 구현에서 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 차단된 예외를 지 원하는 인터페이스.  
  
## 호출자에 대 한 참고 사항  
 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 `IDebugStackFrame2` 이 인터페이스를 가져올 수 있는 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 상속 된 메서드 외에 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md), `IDebugStackFrame3` 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)|예외는 일반 예외 처리 하기 전에 현재 스택 프레임에 대 한 처리합니다.|  
|[GetUnwindCodeContext](../../../extensibility/debugger/reference/idebugstackframe3-getunwindcodecontext.md)|스택 해제가 발생 한 경우에 코드 컨텍스트를 반환 합니다.|  
  
## 설명  
 차단된 예외는 일반 예외 처리 루틴은 실행된 시간에 따라 호출 되기 전에 디버거에서 예외 처리할 수 있는 의미 합니다.  기본적으로 예외를 가로채 가정 된 예외 처리기가 없는 경우에 런타임에 수행 됩니다.  
  
 [InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)유일한 예외는 코드가 혼합 모드 \(관리 되는 표현과 관리 되지 않는 코드\) 디버깅 하는 경우이 경우 예외는 마지막 기회가 콜백 하는 동안 가로챌 수 없습니다 이벤트 \(\) 모든 일반 예외 콜백 중 이라고 합니다.  DE를 구현 하지 않는 경우 `IDebugStackFrame3`, 나는 DE Idebugstackframe3에서 오류를 반환::`InterceptCurrentException` \(같은 `E_NOTIMPL`\), 디버거에서 예외를 정상적으로 처리 하 고 있습니다.  
  
 예외를 가로채 디버거 디버깅 중인 프로그램의 상태를 변경 하 고 다음 예외가 throw 된 지점에서 실행이 다시 시작 할을 수 있습니다.  
  
> [!NOTE]
>  차단된 예외 관리 코드에는 CLR \(공용 언어 런타임 아래에서\)를 실행 하는 프로그램, 허용 됩니다.  
  
 디버그 엔진은 예외를 가로채 "metricExceptions"를 설정 하 여 지원 하도록 값을 1로 런타임에 사용 하 여 지정은 `SetMetric` 함수입니다.  자세한 내용은 [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)를 참조하십시오.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)