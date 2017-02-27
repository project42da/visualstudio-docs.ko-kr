---
title: "IDebugProcessQueryProperties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugProcessQueryProperties"
ms.assetid: ce29a248-81a0-42c0-99a7-1606e8c548ec
caps.latest.revision: 4
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 4
---
# IDebugProcessQueryProperties
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스를 구현 하는 확장 인터페이스입니다 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 구현 합니다.  이 구현 자가 디버깅 프로세스 환경에서 정보를 얻을 수 있습니다.  
  
## 구문  
  
```  
IDebugProcessQueryProperties: IUnknown  
```  
  
## 구현자 참고 사항  
 디버깅 프로세스의 실행 환경에 대 한 정보를 얻으려면이 인터페이스를 구현 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugProcessQueryProperties`.  
  
|메서드|설명|  
|---------|--------|  
|[QueryProperty](../../../extensibility/debugger/reference/idebugprocessqueryproperties-queryproperty.md)|속성 값을 쿼리 합니다.|  
|[QueryProperties](../../../extensibility/debugger/reference/idebugprocessqueryproperties-queryproperties.md)|속성 값을 쿼리 합니다.|  
  
## 설명  
 거의이 인터페이스를 구현 합니다.  
  
## 요구 사항  
 헤더: Portpriv.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)