---
title: "IDebugDynamicField | Microsoft Docs"
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
  - "IDebugDynamicField"
helpviewer_keywords: 
  - "IDebugDynamicField 인터페이스"
ms.assetid: caffbd95-7596-4714-84b1-b964e89a78bb
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDynamicField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 형식을 변수를 나타냅니다.  
  
## 구문  
  
```  
IDebugDynamicField : IDebugField  
```  
  
## 구현자 참고 사항  
 이 인터페이스는 실행된 시간에 확인할 수 있는 모든 형식에 대 한 기본 클래스로 기호 공급자에 의해 구현 됩니다.  이 관리 되는 코드입니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스는 보다 전문화 된 인터페이스에서 파생 될 수 있는 기본 클래스를 나타냅니다.  
  
## 메서드에서 Vtable 순서  
 이 인터페이스에서 상속 된 것과 다른 메서드를 제공 하지 않습니다 `IDebugField`.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)