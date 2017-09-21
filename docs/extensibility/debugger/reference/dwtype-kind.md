---
title: "dwTYPE_KIND | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "dwTYPE_KIND"
helpviewer_keywords: 
  - "dwTYPE_KIND 열거형"
ms.assetid: 6ff56b0f-c502-4e6c-9829-bfa05361b783
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# dwTYPE_KIND
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

형식을 해석 하는 방법을 지정 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체입니다.  
  
## 구문  
  
```cpp#  
enum enum_dwTYPE_KIND {  
   TYPE_KIND_METADATA = 0x0001,  
   TYPE_KIND_PDB      = 0x0002,  
   TYPE_KIND_BUILT    = 0x0003,  
};  
  
typedef DWORD dwTYPE_KIND;  
```  
  
```c#  
public enum enum_dwTYPE_KIND {  
   TYPE_KIND_METADATA = 0x0001,  
   TYPE_KIND_PDB      = 0x0002,  
   TYPE_KIND_BUILT    = 0x0003,  
};  
```  
  
#### 매개 변수  
 TYPE\_KIND\_METADATA  
 [TYPE\_INFO](../../../extensibility/debugger/reference/type-info.md) Union으로 해석 해야는 [METADATA\_TYPE](../../../extensibility/debugger/reference/metadata-type.md) 구조입니다.  
  
 TYPE\_KIND\_PDB  
 `TYPE_INFO` Union으로 해석 해야는 [PDB\_TYPE](../../../extensibility/debugger/reference/pdb-type.md) 구조입니다.  
  
 TYPE\_KIND\_BUILT  
 `TYPE_INFO` Union으로 해석 해야는 [BUILT\_TYPE](../../../extensibility/debugger/reference/built-type.md) 구조입니다.  
  
## 설명  
 이 열거형의 값을 표시를 `dwKind` 필드는 [TYPE\_INFO](../../../extensibility/debugger/reference/type-info.md) 구조와 해석 하는 방법을 결정 하는 데 사용 됩니다는 `type` 공용 구조체 멤버.  `TYPE_INFO` 구조를 호출 하 여 반환 되는 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md) 메서드.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [TYPE\_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)   
 [METADATA\_TYPE](../../../extensibility/debugger/reference/metadata-type.md)   
 [PDB\_TYPE](../../../extensibility/debugger/reference/pdb-type.md)   
 [BUILT\_TYPE](../../../extensibility/debugger/reference/built-type.md)