---
title: "Ijsdebugdatatarget:: Readnullterminatedstring 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJsDebugDataTarget.ReadNullTerminatedString
apilocation: jscript9diag.dll
ms.assetid: 64683b39-6fc2-40c4-82ae-2a6f58d392d5
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 94cb90b8b44aa5dab13a2e916dec22ae950e77ef
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugdatatargetreadnullterminatedstring-method"></a>IJsDebugDataTarget::ReadNullTerminatedString 메서드
대상에서 지정한 개수의 문자를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ReadNullTerminatedString(  
   UINT64 address,  
   UINT16 characterSize,  
   UINT32 maxCharacters,  
   BSTR *pString  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `address`  
 [in] 읽을 수 주소입니다.  
  
 `characterSize`  
 [in] 문자열에 있는 각 문자의 크기  
  
 `maxCharacters`  
 [in] 읽을 문자 최대 수입니다. maxCharacters 적절 해야 합니다. 개 이상의 128MB의 메모리에 대 한 모든 요청이 실패 합니다.  문자열 maxCharacters 보다 클 경우 결과 문자열은 maxCharacters 후 잘립니다.  
  
 `pString`  
 [out] BSTR 대상에서 읽습니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 잘린 경우 S_FALSE를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)