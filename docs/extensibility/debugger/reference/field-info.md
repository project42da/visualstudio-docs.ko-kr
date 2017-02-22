---
title: "FIELD_INFO | Microsoft Docs"
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
  - "FIELD_INFO"
helpviewer_keywords: 
  - "FIELD_INFO 구조"
ms.assetid: bfafef6d-0c83-43d7-a779-1f0d24b166a1
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# FIELD_INFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 구조는 지역 변수, 매개 변수 또는 다른 필드에 설명합니다.  
  
## 구문  
  
```cpp#  
typedef struct _tagFieldInfo {   
   FIELD_INFO_FIELDS dwFields;  
   BSTR              bstrFullName;  
   BSTR              bstrName;  
   BSTR              bstrType;  
   FIELD_MODIFIERS   dwModifiers;  
} FIELD_INFO;  
```  
  
```c#  
public struct FIELD_INFO {  
   public uint   dwFields;  
   public string bstrFullName;  
   public string bstrName;  
   public string bstrType;  
   public uint   dwModifiers;  
};  
```  
  
## Members  
 dwFields  
 플래그의 조합에서 [FIELD\_INFO\_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md) 멤버에 채워져 지정 하는 열거형입니다.  
  
 bstrFullName  
 필드의 전체 이름입니다.  
  
 bstrName  
 약식 이름 필드입니다.  
  
 bstrType  
 필드의 형식입니다.  
  
 dwModifiers  
 플래그의 조합에서 [FIELD\_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md) 필드를 설명 하는 열거형입니다.  
  
## 설명  
 이 구조체에 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) 메서드는 입력 위치에 있습니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [FIELD\_INFO\_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md)   
 [FIELD\_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)