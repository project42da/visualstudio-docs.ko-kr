---
title: "CONSTRUCTOR_ENUM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CONSTRUCTOR_ENUM"
helpviewer_keywords: 
  - "CONSTRUCTOR_ENUM 열거형"
ms.assetid: 6d335b2c-66bc-460c-a4a6-4f3f1b697c2c
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# CONSTRUCTOR_ENUM
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

생성자의 다양 한 종류를 선택합니다.  
  
## 구문  
  
```cpp#  
typedef enum ConstructorMatchOptions {   
   crAll       = 0,  
   crNonStatic = 1,  
   crStatic    = 2  
} CONSTRUCTOR_ENUM;  
```  
  
```c#  
public enum ConstructorMatchOptions {   
   crAll       = 0,  
   crNonStatic = 1,  
   crStatic    = 2  
};  
```  
  
## Members  
 crAll  
 모든 생성자를 선택합니다.  
  
 crNonStatic  
 정적이 아닌 생성자가 선택 됩니다.  
  
 crStatic  
 정적 생성자를 선택합니다.  
  
## 설명  
 인수로 전달 되는 [EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md) 방법입니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)