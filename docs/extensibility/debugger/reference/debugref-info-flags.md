---
title: "DEBUGREF_INFO_FLAGS | Microsoft Docs"
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
  - "DEBUGREF_INFO_FLAGS"
helpviewer_keywords: 
  - "DEBUGREF_INFO_FLAGS 열거형"
ms.assetid: 1b043327-302a-4f6d-b51d-f94f9d7c7f9d
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# DEBUGREF_INFO_FLAGS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 참조 개체에 대 한 검색할 정보를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
typedef DWORD DEBUGREF_INFO_FLAGS;  
```  
  
```c#  
public enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
```  
  
## Members  
 DEBUGREF\_INFO\_NAME  
 초기화\/사용의 `bstrName` 구조체의 필드입니다.  
  
 DEBUGREF\_INFO\_TYPE  
 초기화\/사용의 `bstrType` 구조체의 필드입니다.  
  
 DEBUGREF\_INFO\_VALUE  
 초기화\/사용의 `bstrValue` 구조체의 필드입니다.  
  
 DEBUGREF\_INFO\_ATTRIB  
 초기화\/사용의 `dwAttrib` 구조체의 필드입니다.  
  
 DEBUGREF\_INFO\_REFTYPE  
 초기화\/사용의 `dwRefType` 구조체의 필드입니다.  
  
 DEBUGREF\_INFO\_REF  
 초기화\/사용의 `pReference` 구조체의 필드입니다.  
  
 DEBUGREF\_INFO\_VALUE\_AUTOEXPAND  
 사용 가능한 경우이 형식의 개체에 대 한 자동 확장 값을 값 필드에.  
  
 DEBUGREF\_INFO\_NONE  
 플래그가 설정 되어 있는지 나타냅니다.  
  
 DEBUGREF\_INFO\_ALL  
 마스크는 플래그를 나타냅니다.  
  
## 설명  
 이러한 플래그를 전달의 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) 및 [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md) 필드를 표시 하는 메서드는 [DEBUG\_REFERENCE\_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) 구조에 있는 초기화.  
  
 사용 되는 `dwFields` 의 멤버는 `DEBUG_REFERENCE_INFO` 구조 구조 반환 될 때 필드 사용 되는 및 잘못 된 것을 나타냅니다.  
  
 이 값이 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DEBUG\_REFERENCE\_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)   
 [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)