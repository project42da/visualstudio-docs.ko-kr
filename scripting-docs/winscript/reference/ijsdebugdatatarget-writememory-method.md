---
title: "Ijsdebugdatatarget:: Writememory 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJsDebugDataTarget.WriteMemory
apilocation: jscript9diag.dll
ms.assetid: 0d3c04c3-9ef8-4842-a145-3d29bca75062
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ed562c1cbdd645da6cca87e45f272c25f8bc0d4b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugdatatargetwritememory-method"></a>IJsDebugDataTarget::WriteMemory 메서드
대상 프로세스의 메모리를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT WriteMemory(  
   UINT64 address,  
   const BYTE *pMemory,  
   DWORD size  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `address`  
 [in] 대상 프로세스의 메모리를 쓸 기본 주소입니다.  
  
 `pMemory`  
 [in] 지정된 된 프로세스의 주소 공간에 쓸 데이터입니다.  
  
 `size`  
 [in] 프로세스에 쓸 바이트 수입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 데이터 전송 발생 하기 전에 시스템 확인 하는 기본 주소와 지정된 된 크기의 메모리에 모든 데이터는 쓰기 액세스를 위해 액세스할 수 액세스할 수 없는 경우 함수 E_JsDEBUG_INVALID_MEMORY_ADDRESS 오류를 발생 시킵니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)