---
title: "BP_LOCATION_CODE_STRING | Microsoft Docs"
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
  - "BP_LOCATION_CODE_STRING"
helpviewer_keywords: 
  - "BP_LOCATION_CODE_STRING 구조"
ms.assetid: a4cd71c6-5052-45fe-907b-ebc6ca1df2e4
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# BP_LOCATION_CODE_STRING
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

통합된 개발 환경 \(IDE\)에서 사용자가 입력할 수 있는 문자열 기반 코드 중단점을 설정 하는 데 사용 됩니다.  
  
## 구문  
  
```cpp#  
typedef struct _BP_LOCATION_CODE_STRING {   
   BSTR bstrContext;  
   BSTR bstrCodeExpr;  
} BP_LOCATION_CODE_STRING;  
```  
  
## Members  
 `bstrContext`  
 코드에서 중단점을, 일반적으로 메서드 또는 함수 이름은 호출 스택에 표시 되는 컨텍스트.  
  
 `bstrCodeExpr`  
 입력할 사용자 중단점 코드를 설명 하는 문자열입니다.  
  
## 설명  
 이 구조체의 멤버인는 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 구조체 합집합 일부로.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md)