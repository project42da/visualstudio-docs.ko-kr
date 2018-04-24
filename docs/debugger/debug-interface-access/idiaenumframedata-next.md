---
title: 'Idiaenumframedata:: Next | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::Next method
ms.assetid: 546e2e23-efb2-425a-96a1-808c67c519fb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6835cda6c8c2a5cb20135abf92a523a270b32c78
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumframedatanext"></a>IDiaEnumFrameData::Next
지정 된 개수의 열거 시퀀스에서 프레임 데이터 요소를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Next (   
   ULONG           celt,   
   IDiaFrameData** rgelt,  
   ULONG*          pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 celt  
 [in] 검색할 열거자에 표시 되는 프레임 데이터 요소의 수입니다.  
  
 rgelt  
 [out] 배열을 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 요청 된 프레임 데이터 요소를 사용 하 여 채울 개체입니다.  
  
 pceltFetched  
 [out] 인출 된 열거자에 프레임 데이터 요소의 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 레코드가 더 이상 없는 경우. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)