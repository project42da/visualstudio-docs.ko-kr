---
title: 'Idiasectioncontrib:: Get_read | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSectionContrib::get_read method
ms.assetid: 68bfb35c-eabd-412a-bc8f-3094703b98c4
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6eca8a10c3b317064e84d2b0a9b6372a1d1f521d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasectioncontribgetread"></a>IDiaSectionContrib::get_read
섹션을 읽을 수 있는지 여부를 나타내는 플래그를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_read (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 반환 `TRUE` 섹션을 읽을 수 있습니다; 그렇지 않으면 반환 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)