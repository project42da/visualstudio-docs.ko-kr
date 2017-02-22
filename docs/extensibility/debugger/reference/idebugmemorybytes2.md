---
title: "IDebugMemoryBytes2 | Microsoft Docs"
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
  - "IDebugMemoryBytes2"
helpviewer_keywords: 
  - "IDebugMemoryBytes2 인터페이스"
ms.assetid: d7647575-0e06-4190-88f5-ca40b82209a4
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugMemoryBytes2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 메모리의 바이트를 나타냅니다.  
  
## 구문  
  
```  
IDebugMemoryBytes2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 메모리 \(바이트\)를 나타내는 데이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md)시스템 메모리에 액세스 하기 위해이 인터페이스를 반환 합니다.  [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md)및 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugreference2-getmemorybytes.md) 이 인터페이스에 액세스할 수 있는 개체의 바이트 수를 반환 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugMemoryBytes2`.  
  
|메서드|설명|  
|---------|--------|  
|[ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)|시퀀스에 지정 된 위치에서 시작 하 여 바이트를 읽습니다.|  
|[WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)|기록 `dwCount` 에서 시작 하 여 바이트, `pStartContext`.|  
|[GetSize](../../../extensibility/debugger/reference/idebugmemorybytes2-getsize.md)|이 인터페이스에 의해 표시 되는 메모리의 바이트에서 크기를 가져옵니다.|  
  
## 설명  
 속성에 대 한는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 배열을 나타내는 인터페이스 제공 된 `IDebugMemoryBytes2` 해당 배열 값에 액세스할 수 있는 인터페이스.  
  
 Visual Studio  **메모리 보기** 호출 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md) 를 검색 하는 `IDebugMemoryBytes2` 시스템 메모리에 액세스 하기 위한 인터페이스입니다.  액세스할 수 있는 주소를 가져올 메모리 보기에 있는 주소로 입력 한 식을 구문 분석 하 고 구문 분석 된 식을 사용 하 여 평가 하 고 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 얻을 수는 `IDebugProperty2` 인터페이스입니다.  호출을 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) 반환의 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 메모리 주소에 설명 합니다.  이 메모리 컨텍스트 다음 전달 된 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md) 및 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md).  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md)   
 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md)   
 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugreference2-getmemorybytes.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)