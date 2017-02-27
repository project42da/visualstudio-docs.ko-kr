---
title: "IDebugExtendedField | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugExtendedField 인터페이스"
ms.assetid: b491499c-af57-47da-87d6-34b7398f6591
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# IDebugExtendedField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

관리 되는 코드 제네릭을 지원 하기 위해 사용할 수 있는 필드의 종류를 확장 합니다.  
  
## 구문  
  
```  
IDebugExtendedField : IDebugField  
```  
  
## 메서드  
 메서드 외에 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetExtendedKind](../../../extensibility/debugger/reference/idebugextendedfield-getextendedkind.md)|지정 된 확장 된 필드 종류를 검색합니다.|  
|[IsClosedType](../../../extensibility/debugger/reference/idebugextendedfield-isclosedtype.md)|닫힌된 형식 필드를 나타내는지 여부를 확인 합니다.|  
  
## 요구 사항  
 헤더: Sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll