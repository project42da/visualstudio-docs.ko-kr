---
title: "FIELD_KIND_EX | Microsoft Docs"
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
  - "FIELD_KIND_EX 열거형"
ms.assetid: 922c3208-1e94-485f-b70a-3bc96affeff8
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# FIELD_KIND_EX
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

다른 종류의 필드를 열거 하는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체가 포함 될 수 있습니다.  이 열거형에 확장 되는 [FIELD\_KIND](../../../extensibility/debugger/reference/field-kind.md) 열거형입니다.  
  
## 구문  
  
```cpp#  
enum enum_FIELD_KIND_EX  
{  
   FIELD_KIND_EX_NONE = 0,  
   FIELD_TYPE_EX_METHODVAR = 0x1,  
   FIELD_TYPE_EX_CLASSVAR = 0x2  
} ;  
typedef DWORD FIELD_KIND_EX;  
```  
  
```c#  
public enum enum_FIELD_KIND_EX  
{  
   FIELD_KIND_EX_NONE = 0,  
   FIELD_TYPE_EX_METHODVAR = 0x1,  
   FIELD_TYPE_EX_CLASSVAR = 0x2  
};  
```  
  
## Members  
 FIELD\_KIND\_EX\_NONE  
 있는 확장 된 형식의 필드를 포함 하지 않고 있습니다.  
  
 FIELD\_TYPE\_EX\_METHODVAR  
 메서드 변수 필드를 포함합니다.  
  
 FIELD\_TYPE\_EX\_CLASSVAR  
 필드는 클래스 변수를 포함합니다.  
  
## 요구 사항  
 헤더: Sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetExtendedKind](../../../extensibility/debugger/reference/idebugextendedfield-getextendedkind.md)