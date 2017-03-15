---
title: "IDebugModOpt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugModOpt 인터페이스"
ms.assetid: ebd525e3-d140-4071-9d8c-41871de4125e
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# IDebugModOpt
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 선택적 한정자를 나타냅니다.  
  
## 구문  
  
```  
IDebugModOpt : IUnknown  
```  
  
## 호출자에 대 한 참고 사항  
 가져온 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 클래스 또는 메서드를 나타내는 개체입니다.  
  
## 메서드  
 이 인터페이스에 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetModOpts](../../../extensibility/debugger/reference/idebugmodopt-getmodopts.md)|선택적 한정자의 목록을 검색합니다.|  
  
## 요구 사항  
 헤더: Sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll