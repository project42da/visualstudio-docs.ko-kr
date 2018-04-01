---
title: MACHINE_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MACHINE_INFO
helpviewer_keywords:
- MACHINE_INFO structure
ms.assetid: e7564ff2-00b5-4750-8fd5-dc1029a16912
caps.latest.revision: 10
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 12d0507d3ae6ba44c1c8eef1fc81aec04ae78a66
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="machineinfo"></a>MACHINE_INFO
특정 컴퓨터에 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct tagMACHINE_INFO {   
   MACHINE_INFO_FIELDS Fields;  
   BSTR                bstrName;  
   MACHINE_INFO_FLAGS  Flags;  
} MACHINE_INFO;  
```  
  
```csharp  
public struct MACHINE_INFO {   
   public uint   Fields;  
   public string bstrName;  
   public uint   Flags;  
};  
```  
  
## <a name="members"></a>멤버  
 `Fields`  
 플래그의 조합 된 [MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md) 초기화 되는 구조체의 필드를 지정 하는 열거형입니다.  
  
 `bstrName`  
 컴퓨터 이름입니다. 호출에 해당 [GetMachineName](../../../extensibility/debugger/reference/idebugcoreserver2-getmachinename.md)합니다.  
  
 `Flags`  
 플래그의 조합 된 [MACHINE_INFO_FLAGS](../../../extensibility/debugger/reference/machine-info-flags.md) 컴퓨터 특성을 설명 하는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 이 구조에 대 한 호출에서 반환 된 [GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md)   
 [GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)