---
title: "IDebugCustomAttributeQuery | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugCustomAttributeQuery 인터페이스"
ms.assetid: b804b619-70eb-4c38-80d9-c8b32b65ed3e
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDebugCustomAttributeQuery
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

메서드 또는 형식의 사용자 지정 특성에 대 한 쿼리를 나타냅니다.  
  
## 구문  
  
```  
IDebugCustomAttributeQuery : IUnknown  
```  
  
## 메서드  
 다음 방법이이 인터페이스를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery-getcustomattributebyname.md)|지정 된 이름 사용자 지정 특성을 검색 합니다.|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery-iscustomattributedefined.md)|결정에 지정 된 사용자 지정 특성을 정의 합니다.|  
  
## 요구 사항  
 헤더: Sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll