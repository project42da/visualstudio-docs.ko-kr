---
title: "Ijsdebugdatatarget:: Freevirtualmemory 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJsDebugDataTarget.FreeVirtualMemory
apilocation: jscript9diag.dll
ms.assetid: ea54bad3-9ae3-436b-974d-70fc7fffefd6
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3b53d7f80227a1c4eb0ef0293093543c09c5a367
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugdatatargetfreevirtualmemory-method"></a>IJsDebugDataTarget::FreeVirtualMemory 메서드
해제 및/또는 대상 프로세스의 가상 주소 공간 내에서 메모리 영역 커밋  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FreeVirtualMemory(  
   UINT64 address,  
   DWORD size,  
   DWORD freeType  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `address`  
 [in] 메모리를 해제 하는 대상 프로세스 내의 주소입니다.  
  
 `size`  
 [in] 커밋 해제 하는 바이트 수입니다. 메모리 영역을 해제 하려면이 값이 0 이어야 합니다.  
  
 `freeType`  
 [in] 수행 가능한 작업 유형을 나타냅니다. 이 일반적으로 페이지의 지정된 된 지역 해제 MEM_RELEASE (0x8000). 작업 후의 페이지는 사용 가능한 상태입니다. MEM_DECOMMIT (0x4000) 해제 하지 않고 페이지를 커밋 해제를 대신 사용할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 자세한 내용은 VirtualFree Win32 API를 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)