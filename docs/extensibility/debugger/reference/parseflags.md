---
title: "PARSEFLAGS | Microsoft Docs"
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
  - "PARSEFLAGS"
helpviewer_keywords: 
  - "PARSEFLAGS 열거형"
ms.assetid: 47943f0a-54cb-4493-a62e-5dba97bd4c35
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# PARSEFLAGS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

식을 구문 분석 하는 방법을 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
typedef DWORD PARSEFLAGS;  
```  
  
```c#  
public enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
```  
  
## Members  
 PARSE\_EXPRESSION  
 식 문이 없음을 나타냅니다.  
  
 PARSE\_FUNCTION\_AS\_ADDRESS  
 식 수 구문 분석 및 나중에 평가 하는 주소입니다.  
  
 PARSE\_DESIGN\_TIME\_EXPR\_EVAL  
 디자인 타임에는 식 구문 분석 되는 나타냅니다 \(즉, 디자이너가 열려 있는 경우\).  
  
## 설명  
 매개 변수로 전달 되는 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 및 [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) 방법.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)   
 [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)