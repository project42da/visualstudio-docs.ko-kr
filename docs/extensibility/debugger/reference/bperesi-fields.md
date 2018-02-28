---
title: BPERESI_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BPERESI_FIELDS
helpviewer_keywords:
- BPERESI_FIELDS enumeration
ms.assetid: dd7dd89c-1043-46a1-a929-099cc039c344
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 36ac591940acaed2ac8b8f92c701580d9d45f94a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bperesifields"></a>BPERESI_FIELDS
중단점의 실패 한 확인에 대 한 검색할 정보를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD BPERESI_FIELDS;  
```  
  
```csharp  
public enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
```  
  
## <a name="members"></a>멤버  
 PERESI_BPRESLOCATION  
 초기화/사용 된 `bpResLocation` 의 (중단점 해상도 위치) 필드는 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) 구조입니다.  
  
 BPERESI_PROGRAM  
 초기화/사용 된 `pProgram` 필드는 `BP_ERROR_RESOLUTION_INFO` 구조입니다.  
  
 BPERESI_THREAD  
 초기화/사용 된 `pThread` 필드는 `BP_ERROR_RESOLUTION_INFO` 구조입니다.  
  
 BPERESI_MESSAGE  
 초기화/사용 된 `bstrMessage` 필드는 `BP_ERROR_RESOLUTION_INFO` 구조입니다.  
  
 BPERESI_TYPE  
 초기화/사용 된 `dwType` 의 (중단점 유형) 필드는 `BP_ERROR_RESOLUTION_INFO` 구조입니다.  
  
 BPERESI_ALLFIELDS  
 초기화/사용의 모든 필드는 `BP_ERROR_RESOLUTION_INFO` 구조입니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 매개 변수로 전달 되는 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md) 의 필드를 나타내도록 메서드를는 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) 구조를 초기화할 수는 있습니다.  
  
 이러한 값 필드를 나타내는 데 사용 된 `BP_ERROR_RESOLUTION_INFO` 구조는 사용 되지 않으며 유효한 해당 구조를 반환 하는 경우.  
  
 이러한 값에 비트와 함께 사용할 수 있습니다 `OR`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)