---
title: "DOCCONTEXT_COMPARE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DOCCONTEXT_COMPARE"
helpviewer_keywords: 
  - "DOCCONTEXT_COMPARE 열거형"
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# DOCCONTEXT_COMPARE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

두 문서 컨텍스트 비교 하는 조건을 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
typedef DWORD DOCCONTEXT_COMPARE;  
```  
  
```c#  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
```  
  
## Members  
 DOCCONTEXT\_EQUAL  
 해당 대상 문서의 컨텍스트에 목록에서 첫 번째 문서 컨텍스트를 찾습니다.  
  
 DOCCONTEXT\_LESS\_THAN  
 대상 문서의 상황에 맞는 보다 작은 목록에서 첫 번째 문서 컨텍스트를 찾습니다.  
  
 DOCCONTEXT\_GREATER\_THAN  
 대상 문서의 컨텍스트 보다 큰 목록에서 첫 번째 문서 컨텍스트를 찾습니다.  
  
 DOCCONTEXT\_SAME\_DOCUMENT  
 대상 문서 컨텍스트는 같은 문서에 있는 목록에서 첫 번째 문서 컨텍스트를 찾습니다.  
  
## 설명  
 인수로 전달 되는 [비교](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md) 방법입니다.  
  
 이 값 목록에서 첫 번째 문서 컨텍스트 찾기에 대 한 비교 조건을 지정 하는 데 사용 됩니다.  문서 컨텍스트 컨텍스트의 문서 목록을 통해에서 자신을 비교 하 나와 있는 `IDebugDocumentContext2::Compare` 메서드.  첫 번째 문서 컨텍스트를 비교 연산자 목록에서 `true` 다음이 반환 됩니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [비교](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)