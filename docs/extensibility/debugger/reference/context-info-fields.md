---
title: CONTEXT_INFO_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CONTEXT_INFO_FIELDS
helpviewer_keywords:
- CONTEXT_INFO_FIELDS enumeration
ms.assetid: ef436bd3-738e-47e8-828c-8febce752439
caps.latest.revision: 13
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8f0316e8822706b26103f02eda1849568cf79994
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="contextinfofields"></a>CONTEXT_INFO_FIELDS
검색할 메모리 컨텍스트에 대 한 정보를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_CONTEXT_INFO_FIELDS {   
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
  
```csharp  
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
  
## <a name="members"></a>멤버  
 CIF_MODULEURL  
 초기화/사용 된 `bstrModuleUrl` 필드는 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) 구조입니다.  
  
 CIF_FUNCTION  
 초기화/사용 된 `bstrFunction` 필드는 `CONTEXT_INFO` 구조입니다.  
  
 CIF_FUNCTIONOFFSET  
 초기화/사용 된 `posFunctionOffset` 필드는 `CONTEXT_INFO` 구조입니다.  
  
 CIF_ADDRESS  
 초기화/사용 된 `bstrAddress` 필드는 `CONTEXT_INFO` 구조입니다.  
  
 CIF_ADDRESSOFFSET  
 초기화/사용 된 `bstrAddressOffset` 필드는 `CONTEXT_INFO` 구조입니다.  
  
 CIF_ALLFIELDS  
 초기화/사용의 모든 필드는 `CONTEXT_INFO` 구조입니다.  
  
## <a name="remarks"></a>설명  
 이러한 값은 매개 변수를 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) 의 필드를 나타내도록 메서드를는 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) 구조를 초기화할 수는 있습니다.  
  
 이러한 플래그의 필드를 나타내기 위해 사용도 `CONTEXT_INFO` 구조는 사용 되지 않으며 유효한 구조를 반환 하는 경우.  
  
 이러한 값 비트 OR 연산자와 함께 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)