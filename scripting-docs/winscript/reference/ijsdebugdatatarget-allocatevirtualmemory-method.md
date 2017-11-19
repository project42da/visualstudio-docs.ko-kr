---
title: "Ijsdebugdatatarget:: Allocatevirtualmemory 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJsDebugDataTarget.AllocateVirtualMemory
apilocation: jscript9diag.dll
ms.assetid: 1d3a77b0-c1de-4a0c-a759-3e0c68fd96dd
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 65b29bbf9a3405bcfab779bd877f798a863538d5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugdatatargetallocatevirtualmemory-method"></a>IJsDebugDataTarget::AllocateVirtualMemory 메서드
예약 하거나 대상 프로세스의 가상 주소 공간 내에서 메모리 영역을 커밋합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AllocateVirtualMemory(  
   UINT64 address,  
   DWORD size,  
   DWORD allocationType,  
   DWORD pageProtection,  
   UINT64 *pAllocatedAddress  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `address`  
 [in] 여기서는 메모리 커밋 또는 예약 된 대상 프로세스 내 주소입니다. 일반적으로이 값은 0 인 경우 시스템 주소를 선택 합니다.  
  
 `size`  
 [in] 크기 (바이트)에 할당할 메모리의 영역입니다. 시스템은 자동으로 다음 페이지 경계에 맞게 반올림 됩니다.  
  
 `allocationType`  
 [in] 수행 하는 할당의 유형을 나타냅니다. 이 일반적으로 MEM_COMMIT &#124; MEM_RESERVE (0x3000)를 예약 하 고 한 번에 할당을 커밋합니다.  
  
 `pageProtection`  
 [in] 해당 지역에 대해 페이지를 할당할 수는 메모리 보호 합니다. 페이지 내용이 커밋될 경우에 메모리 보호 상수 (예를 들어 PAGE_READWRITE, PAGE_EXECUTE) 중 하나를 지정할 수 있습니다.  
  
 `pAllocatedAddress`  
 [out] 할당 된 페이지 영역의 기준 주소입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 MEM_RESET 사용 하지 않는 함수를 0으로 할당 된 메모리를 초기화 합니다. 자세한 내용은 VirtualAlloc Win32 API를 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)