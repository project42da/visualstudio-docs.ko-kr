---
title: 'Idiastackframe:: Get_localsbase | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackFrame::get_localsBase method
ms.assetid: eb0bd73e-d92d-468e-a0b1-fbc279919f54
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 69d9cd6f1e589f40b5f64bcc37e38291302cffce
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackframegetlocalsbase"></a>IDiaStackFrame::get_localsBase
지역 변수는 프레임에 대 한 기본 주소를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_localsBase (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 지역 변수의 기본 주소를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 속성이 지원 되지 않는 경우. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)