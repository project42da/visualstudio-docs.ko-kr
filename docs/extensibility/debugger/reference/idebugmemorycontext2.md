---
title: "IDebugMemoryContext2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugMemoryContext2"
helpviewer_keywords: 
  - "IDebugMemoryContext2 인터페이스"
ms.assetid: 3a544c8b-11dc-46bb-8549-261e4ac5bbc4
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugMemoryContext2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버깅 되는 프로그램을 실행 하는 컴퓨터의 주소 공간에서 위치를 나타냅니다.  
  
## 구문  
  
```  
IDebugMemoryContext2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 메모리에 있는 주소를 표현 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출을 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) 또는 [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md) 이 인터페이스를 반환 합니다.  또한 호출 하려면 [Add](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md) 및 [빼기](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md) 적절 한 산술 연산을 적용 한 후이 인터페이스의 새 복사본을 반환 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugMemoryContext2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetName](../../../extensibility/debugger/reference/idebugmemorycontext2-getname.md)|이 컨텍스트에서 사용자가 표시할 수 있는 이름을 가져옵니다.|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)|이 컨텍스트를 설명 하는 정보를 가져옵니다.|  
|[Add](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md)|새 컨텍스트를 작성 하는 현재 컨텍스트 주소에 지정 된 값을 추가 합니다.|  
|[빼기](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md)|새 컨텍스트를 작성 하는 현재 컨텍스트 주소에서 지정 된 값을 뺍니다.|  
|[비교](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)|비교 하는 방식으로 두 가지 컨텍스트에서 지정 된 플래그를 비교 합니다.|  
  
## 설명  
 Visual Studio  **메모리** 창 호출 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) 얻을 수 있는 `IDebugMemoryContext2` 메모리 주소를 사용 하 여 계산된 된 식을 포함 하는 인터페이스입니다.  이 여기서 다음 전달 된 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md) 및 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md) 읽기 또는 쓰기 주소를 지정 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)   
 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)   
 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)