---
title: "IDebugTypeFieldBuilder | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugTypeFieldBuilder 인터페이스"
ms.assetid: 2dfed0be-6972-4bec-baec-f0b78df9ef97
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugTypeFieldBuilder
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

형식을 나타내는 필드를 만들 수 있는 기능을 나타냅니다.  
  
## 구문  
  
```  
IDebugTypeFieldBuilder : IUnknown  
```  
  
## 호출자에 대 한 참고 사항  
 기호 공급자 로부터이 인터페이스를 가져옵니다.  
  
## 메서드  
 다음 방법이이 인터페이스를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|[CreatePrimitive](../../../extensibility/debugger/reference/idebugtypefieldbuilder-createprimitive.md)|기본 형식을 나타내는 개체를 만듭니다.|  
|[CreatePointerToType](../../../extensibility/debugger/reference/idebugtypefieldbuilder-createpointertotype.md)|지정 된 형식에 대 한 포인터를 만듭니다.|  
  
## 요구 사항  
 헤더: Sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll