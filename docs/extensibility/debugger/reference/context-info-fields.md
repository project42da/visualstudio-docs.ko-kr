---
title: "CONTEXT_INFO_FIELDS | Microsoft Docs"
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
  - "CONTEXT_INFO_FIELDS"
helpviewer_keywords: 
  - "CONTEXT_INFO_FIELDS 열거형"
ms.assetid: ef436bd3-738e-47e8-828c-8febce752439
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# CONTEXT_INFO_FIELDS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

검색할 메모리에 대 한 컨텍스트 정보를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_CONTEXT_INFO_FIELDS {   
   CIF_MODULEURL =       0x00000001,  
   CIF_FUNCTION =        0x00000002,  
   CIF_FUNCTIONOFFSET =  0x00000004,  
   CIF_ADDRESS =         0x00000008,  
   CIF_ADDRESSOFFSET =   0x00000010,  
   CIF_ADDRESSABSOLUTE = 0x00000020,  
   CIF_ALLFIELDS =       0x0000003f  
};  
typedef DWORD CONTEXT_INFO_FIELDS;  
```  
  
```c#  
public enum enum_CONTEXT_INFO_FIELDS {  
   CIF_MODULEURL =       0x00000001,  
   CIF_FUNCTION =        0x00000002,  
   CIF_FUNCTIONOFFSET =  0x00000004,  
   CIF_ADDRESS =         0x00000008,  
   CIF_ADDRESSOFFSET =   0x00000010,  
   CIF_ADDRESSABSOLUTE = 0x00000020,  
   CIF_ALLFIELDS =       0x0000003f  
};  
```  
  
## Members  
 CIF\_MODULEURL  
 초기화\/사용의 `bstrModuleUrl` 필드는 [CONTEXT\_INFO](../../../extensibility/debugger/reference/context-info.md) 구조입니다.  
  
 CIF\_FUNCTION  
 초기화\/사용의 `bstrFunction` 필드는 `CONTEXT_INFO` 구조입니다.  
  
 CIF\_FUNCTIONOFFSET  
 초기화\/사용의 `posFunctionOffset` 필드는 `CONTEXT_INFO` 구조입니다.  
  
 CIF\_ADDRESS  
 초기화\/사용의 `bstrAddress` 필드는 `CONTEXT_INFO` 구조입니다.  
  
 CIF\_ADDRESSOFFSET  
 초기화\/사용의 `bstrAddressOffset` 필드는 `CONTEXT_INFO` 구조입니다.  
  
 CIF\_ALLFIELDS  
 초기화\/사용의 모든 필드는 `CONTEXT_INFO` 구조입니다.  
  
## 설명  
 이러한 값을 매개 변수로 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) 필드의 나타내도록 메서드는 [CONTEXT\_INFO](../../../extensibility/debugger/reference/context-info.md) 구조에 있는 초기화 합니다.  
  
 이러한 플래그 필드를 나타내는 데도 사용 됩니다 있는 `CONTEXT_INFO` 구조는 유효 하 고 사용 하는 구조를 반환 하는 경우.  
  
 비트 OR로 이러한 값을 조합할 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CONTEXT\_INFO](../../../extensibility/debugger/reference/context-info.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)