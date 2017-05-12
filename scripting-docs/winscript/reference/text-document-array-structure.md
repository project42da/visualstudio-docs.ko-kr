---
title: "TEXT_DOCUMENT_ARRAY 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "TEXT_DOCUMENT_ARRAY 구조체"
ms.assetid: 47c08f23-981b-4105-9240-6dfffc6cb91b
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# TEXT_DOCUMENT_ARRAY 구조체
[IDebugDocumentText 인터페이스](../../winscript/reference/idebugdocumenttext-interface.md) 개체로 이루어진 배열입니다.  멤버는 Cotaskmemalloc에 할당 됩니다.  
  
## 구문  
  
```  
typedef struct tagTEXT_DOCUMENT_ARRAY  
{  
    DWORD dwCount;  
    [size_is(dwCount)] IDebugDocumentText **Members;  
} TEXT_DOCUMENT_ARRAY;  
  
```  
  
## Members  
 `dwCount`  
 문서 수입니다.  
  
 `Members`  
 문서 집합입니다.  
  
## 참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)