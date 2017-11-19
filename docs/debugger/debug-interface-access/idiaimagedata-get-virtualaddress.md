---
title: 'Idiaimagedata:: Get_virtualaddress | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaImageData::get_virtualAddress method
ms.assetid: 67ecdc8c-d342-4d0b-b02a-c6b88e22fd02
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 71c8dc85487e26a9d9bc576b5b71861c9352627d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaimagedatagetvirtualaddress"></a>IDiaImageData::get_virtualAddress
이미지의 가상 메모리 내의 위치를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_virtualAddress (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 이미지의 가상 주소를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)