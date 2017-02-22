---
title: "MODULE_FLAGS | Microsoft Docs"
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
  - "MODULE_FLAGS"
helpviewer_keywords: 
  - "MODULE_FLAGS 열거형"
ms.assetid: 0e555b42-b846-4dbb-812e-8e3d11c85b2d
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# MODULE_FLAGS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

모듈을 설명 하는 데 사용 합니다.  
  
## 구문  
  
```cpp#  
enum enum_MODULE_FLAGS {   
   MODULE_FLAG_NONE        = 0x0000,  
   MODULE_FLAG_SYSTEM      = 0x0001,  
   MODULE_FLAG_SYMBOLS     = 0x0002,  
   MODULE_FLAG_64BIT       = 0x0004,  
   MODULE_FLAG_OPTIMIZED   = 0x0008,  
   MODULE_FLAG_UNOPTIMIZED = 0x0010  
};  
typedef DWORD MODULE_FLAGS;  
```  
  
```c#  
public enum enum_MODULE_FLAGS {   
   MODULE_FLAG_NONE        = 0x0000,  
   MODULE_FLAG_SYSTEM      = 0x0001,  
   MODULE_FLAG_SYMBOLS     = 0x0002,  
   MODULE_FLAG_64BIT       = 0x0004,  
   MODULE_FLAG_OPTIMIZED   = 0x0008,  
   MODULE_FLAG_UNOPTIMIZED = 0x0010  
};  
```  
  
## Members  
 MODULE\_FLAG\_NONE  
 없음 모듈을 지정합니다.  
  
 MODULE\_FLAG\_SYSTEM  
 시스템 모듈을 지정합니다.  
  
 MODULE\_FLAG\_SYMBOLS  
 기호 모듈을 지정 합니다.  
  
 MODULE\_FLAG\_64BIT  
 64 비트 모듈을 지정 합니다.  
  
 MODULE\_FLAG\_OPTIMIZED  
 최적화 된 모듈을 지정 합니다.  이 상태에 반영 되어 있는  **모듈** 창입니다.  
  
 MODULE\_FLAG\_UNOPTIMIZED  
 않은 최적화 된 모듈을 지정 합니다.  이 상태에 반영 되어 있는  **모듈** 창입니다.  기본 상태입니다.  
  
## 설명  
 사용 되는 `m_dwModuleFlags` 의 멤버는 [MODULE\_INFO](../../../extensibility/debugger/reference/module-info.md) 구조.  
  
 이러한 플래그의 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [MODULE\_INFO](../../../extensibility/debugger/reference/module-info.md)