---
title: "BP_PASSCOUNT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_PASSCOUNT"
helpviewer_keywords: 
  - "BP_PASSCOUNT 구조"
ms.assetid: 791ac175-b897-4c70-873e-240da7e0ac89
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# BP_PASSCOUNT
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

조건부 중단점에 발생 하는 횟수 및 조건에 설명 합니다.  
  
## 구문  
  
```cpp#  
typedef struct _BP_PASSCOUNT {   
   DWORD              dwPassCount;  
   BP_PASSCOUNT_STYLE stylePassCount;  
} BP_PASSCOUNT;  
```  
  
```c#  
public struct BP_PASSCOUNT {   
   public uint dwPassCount;  
   public uint stylePassCount;  
};  
```  
  
## Members  
 `dwPassCount`  
 이 발생 하기 전에 중단점이 위에 통과 횟수입니다.  
  
 `stylePassCount`  
 값은 [BP\_PASSCOUNT\_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md) 전달할 수 중단점의 스타일을 지정 하는 열거형입니다.  
  
## 설명  
 이 구조체의 멤버인는 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 구조체입니다.  
  
 이 구조는 매개 변수로 전달 되는[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md) 및[SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md) 방법입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)   
 [BP\_PASSCOUNT\_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md)