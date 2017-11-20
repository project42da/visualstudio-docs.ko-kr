---
title: 'Idiaenumsymbolsbyaddr:: Symbolbyrva | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSymbolsByAddr::symbolByRVA method
ms.assetid: f7828029-f2ee-4ccd-afac-785adc60a4c8
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 65671bee476e772d046c5a22e398ffdda0e600fd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumsymbolsbyaddrsymbolbyrva"></a>IDiaEnumSymbolsByAddr::symbolByRVA
상대 가상 주소 (RVA) 하 여 조회를 수행 하 여 열거자를 놓습니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT symbolByRVA (   
   DWORD**      relativeVirtualAddress,  
   IDiaSymbol** ppsymbol  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 relativeVirtualAddress  
 [in] 이미지의 시작 부분에 상대적인 주소입니다.  
  
 ppsymbol  
 [out] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 기호를 찾을 수를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 기호를 찾을 수 없는 경우. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)   
 [Idiaenumsymbolsbyaddr:: Symbolbyva](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyva.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)