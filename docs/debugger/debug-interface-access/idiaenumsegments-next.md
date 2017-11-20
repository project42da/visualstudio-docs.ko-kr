---
title: 'Idiaenumsegments:: Next | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSegments::Next method
ms.assetid: 53f61874-d821-47ab-a1f5-27e982804a6a
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 210976ad2cbe44d4f94758c9c1fe9d2216e7f44c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumsegmentsnext"></a>IDiaEnumSegments::Next
열거형 시퀀스에 있는 세그먼트의 지정된 된 수를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Next (   
   ULONG         celt,   
   IDiaSegment** rgelt,  
   ULONG*        pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 celt  
 [in] 검색할 열거자에서 세그먼트의 수입니다.  
  
 rgelt  
 [out] 원하는 입력할 수 있는 배열을 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) 세그먼트를 나타내는 개체입니다.  
  
 pceltFetched  
 [out] 인출 된 열거자에 세그먼트의 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우 더 많은 세그먼트가 있습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)