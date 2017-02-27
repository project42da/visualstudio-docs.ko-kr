---
title: "IDebugAddress | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugAddress"
helpviewer_keywords: 
  - "IDebugAddress 인터페이스"
ms.assetid: bc709ff7-4966-4f36-9af2-690efe2cea1d
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugAddress
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 항목의 주소를 나타냅니다.  기호 처리기에 의해 반환 됩니다.  
  
## 구문  
  
```  
IDebugAddress : IUnknown  
```  
  
## 구현자 참고 사항  
 이 인터페이스는 개체의 주소를 나타내는 기호 공급자를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 많은 메서드가 많은 인터페이스에이 인터페이스를 반환합니다.  
  
## 메서드에서 Vtable 순서  
 이 인터페이스에 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)|검색은 [DEBUG\_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 개체의 위치를 설명 하는 구조입니다.|  
  
## 설명  
 이 인터페이스는 개체 및 특정 범위 \(예를 들어, 함수, 메서드 또는 클래스\)에서 멤버 위치를 나타내는 기호 공급자를 반환 합니다.  이 인터페이스에서 반환 하 고 기호 공급자 및 식의 다양 한 방법으로 전달 된 계산기.  일반적으로 기호 공급자가이 인터페이스의 내용을 해석 하는 데 필요한 유일한 항목입니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [DEBUG\_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)