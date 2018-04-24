---
title: 'Idiaenumframedata:: Get_count | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::get_Count method
ms.assetid: 94374d27-e335-4e90-a442-233181ab8e58
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a15df11cbdc5cc13aa991e5a7704929e65e29875
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumframedatagetcount"></a>IDiaEnumFrameData::get_Count
프레임 데이터 요소의 수를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_Count (   
   LONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pRetVal  
 [out] 프레임 데이터 요소의 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaEnumFrameData::Item](../../debugger/debug-interface-access/idiaenumframedata-item.md)