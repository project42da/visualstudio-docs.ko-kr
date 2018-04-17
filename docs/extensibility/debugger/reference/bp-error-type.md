---
title: BP_ERROR_TYPE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_ERROR_TYPE
helpviewer_keywords:
- BP_ERROR_TYPE enumeration
ms.assetid: c483eaab-db29-46de-bfdb-5c2a9a9cfb68
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 676ec19fec1406d85e6a7d9e66865b2794f72aa6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="bperrortype"></a>BP_ERROR_TYPE
중단점의 오류 유형을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_BP_ERROR_TYPE {   
   BPET_NONE            = 0x00000000,  
   BPET_TYPE_WARNING    = 0x00000001,  
   BPET_TYPE_ERROR      = 0x00000002,  
   BPET_SEV_HIGH        = 0x0F000000,  
   BPET_SEV_GENERAL     = 0x07000000,  
   BPET_SEV_LOW         = 0x01000000,  
   BPET_TYPE_MASK       = 0x0000ffff,  
   BPET_SEV_MASK        = 0xffff0000,  
   BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,  
   BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,  
   BPET_ALL             = 0xffffffff  
};  
typedef DWORD BP_ERROR_TYPE;  
```  
  
```csharp  
public enum enum_BP_ERROR_TYPE {   
   BPET_NONE            = 0x00000000,  
   BPET_TYPE_WARNING    = 0x00000001,  
   BPET_TYPE_ERROR      = 0x00000002,  
   BPET_SEV_HIGH        = 0x0F000000,  
   BPET_SEV_GENERAL     = 0x07000000,  
   BPET_SEV_LOW         = 0x01000000,  
   BPET_TYPE_MASK       = 0x0000ffff,  
   BPET_SEV_MASK        = 0xffff0000,  
   BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,  
   BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,  
   BPET_ALL             = 0xffffffff  
};  
```  
  
## <a name="members"></a>멤버  
 BPET_NONE  
 오류가 발생 하지 중단점을 지정합니다.  
  
 BPET_TYPE_WARNING  
 경고 스타일 중단점 오류를 지정합니다.  
  
 BPET_TYPE_ERROR  
 오류-스타일 중단점 오류를 지정 합니다.  
  
 BPET_SEV_HIGH  
 심각한 중단점 오류를 지정합니다.  
  
 BPET_SEV_GENERAL  
 심각도 보통 중단점 오류를 지정합니다.  
  
 BPET_SEV_LOW  
 낮은 심각도 중단점 오류를 지정합니다.  
  
 BPET_TYPE_MASK  
 마스크 스타일 중단점 오류를 지정합니다.  
  
 BPET_SEV_MASK  
 심각도 마스크 스타일 중단점 오류를 지정합니다.  
  
 BPET_GENERAL_WARNING  
 일반 경고 스타일 중단점 오류를 지정합니다.  
  
 BPET_GENERAL_ERROR  
 일반 오류 스타일 중단점 오류를 지정합니다.  
  
 BPET_ALL  
 모든 중단점 오류 유형을 지정합니다.  
  
## <a name="remarks"></a>설명  
 이러한 값에 비트와 함께 사용할 수 있습니다 `OR` 하는 데 사용 하 고는 `dwType` 의 멤버는 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) 구조입니다. 에 대 한 매개 변수로 전달 되는 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md) 메서드.  
  
 중단점 오류 유형 심각도 및 형식으로 구성 됩니다. 즉, 중단점 오류 형식이 일종 되지 않습니다 (예를 들어 `BPET_TYPE_ERROR`,) 나 심각도 (예를 들어 `BPET_SEV_GENERAL`) 단독으로 합니다. `BPET_GENERAL_WARNING` 및 `BPET_GENERAL_ERROR` 일반 경고 및 오류 중단점에 대 한 미리 정의 된 값을 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)