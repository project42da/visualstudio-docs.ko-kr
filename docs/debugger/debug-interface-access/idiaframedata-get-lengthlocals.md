---
title: 'Idiaframedata:: Get_lengthlocals | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaFrameData::get_lengthLocals method
ms.assetid: 51fe15c3-4cd6-4a06-8a41-a56502209762
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9548bc86eba94ddb7f857deb4cd066e400d5bfb8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaframedatagetlengthlocals"></a>IDiaFrameData::get_lengthLocals
지역 변수를 스택에 푸시한의 바이트 수를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_lengthLocals (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 지역 변수의 바이트 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드에서 반환 된 값은 대개 프로그램 문자열의 해석에 사용 됩니다 (참조는 [idiaframedata:: Get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md) 프로그램 문자열의 정의 대 한 메서드).  
  
## <a name="see-also"></a>참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaFrameData::get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md)