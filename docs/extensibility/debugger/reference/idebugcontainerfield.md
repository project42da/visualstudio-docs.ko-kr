---
title: "IDebugContainerField | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugContainerField"
helpviewer_keywords: 
  - "IDebugContainerField 인터페이스"
ms.assetid: a8bbe061-c382-4fe9-a193-3f7d12216041
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugContainerField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 기호나 기타 기호 또는 형식에 대 한 컨테이너 형식을 나타냅니다.  
  
## 구문  
  
```  
IDebugContainerField : IDebugField  
```  
  
## 구현자 참고 사항  
 기호 공급자를 구현 하는 동일한 개체에서이 인터페이스는 구현에서 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스입니다.  이 인터페이스는 컨테이너를 나타내는 모든 인터페이스에 대 한 기본 클래스입니다.  
  
## 호출자에 대 한 참고 사항  
 많은 메서드가 많은 인터페이스에이 인터페이스를 반환합니다.  모든 컨테이너에 대 한 기본 클래스 이므로 보다 전문화 된 인터페이스 있습니다 얻은이 인터페이스를 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface).  Such interfaces include [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md), [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md), [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md), and [IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md).  
  
## 메서드에서 Vtable 순서  
 메서드 외에 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)|컨테이너의 필드에 대 한 열거자를 만듭니다.|  
  
## 설명  
 배열 \(변수에 대해 컨테이너\), \(컨테이너 메서드 및 변수에 대 한\) 클래스 및 메서드 \(컨테이너 매개 변수 및 지역 변수에 대 한\) 예의 컨테이너입니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)