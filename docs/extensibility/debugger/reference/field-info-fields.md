---
title: "FIELD_INFO_FIELDS | Microsoft Docs"
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
  - "FIELD_INFO_FIELDS"
helpviewer_keywords: 
  - "FIELD_INFO_FIELDS 열거형"
ms.assetid: a69487d2-e701-4165-804a-8a011df9a3bd
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# FIELD_INFO_FIELDS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

검색에 대 한 정보를 지정 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체입니다.  
  
## 구문  
  
```cpp#  
enum enum_FIELD_INFO_FIELDS {   
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
typedef DWORD FIELD_INFO_FIELDS;  
```  
  
```c#  
public enum enum_FIELD_INFO_FIELDS {  
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
```  
  
## Members  
 FIF\_FULLNAME  
 초기화\/사용의 `bstrFullName` 필드에 [FIELD\_INFO](../../../extensibility/debugger/reference/field-info.md) 구조입니다.  
  
 FIF\_NAME  
 초기화\/사용의 `bstrName` 필드에 `FIELD_INFO` 구조입니다.  
  
 FIF\_TYPE  
 초기화\/사용의 `bstrType` 필드에 `FIELD_INFO` 구조입니다.  
  
 FIF\_MODIFIERS  
 초기화\/사용의 `bstrModifiers` 필드에 `FIELD_INFO` 구조입니다.  
  
## 설명  
 이러한 값 또한 인수로 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) 의 필드를 지정 하는 메서드는 [FIELD\_INFO](../../../extensibility/debugger/reference/field-info.md) 구조에 있는 초기화.  
  
 이러한 값에도 사용 됩니다의 `dwFields` 의 멤버는 `FIELD_INFO` 구조 필드 사용 되는 및 잘못 된 것을 나타냅니다.  
  
 이러한 플래그의 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD\_INFO](../../../extensibility/debugger/reference/field-info.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)