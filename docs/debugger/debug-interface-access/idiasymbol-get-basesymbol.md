---
title: IDiaSymbol::get_baseSymbol | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: cabb5a18-bda7-47e8-9e46-5f4718579fc9
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 531d9b07d29be963e8e346c8cf85dbe8977ff50d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetbasesymbol"></a>IDiaSymbol::get_baseSymbol
포인터 기반 기호를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_baseSymbol(   
   IDiaSymbol** pRetVal);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 포인터 기반 기호에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_baseSymbolId](../../debugger/debug-interface-access/idiasymbol-get-basesymbolid.md)