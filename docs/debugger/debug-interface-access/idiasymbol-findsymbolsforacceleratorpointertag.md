---
title: IDiaSymbol::findSymbolsForAcceleratorPointerTag | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: fb66852c-c5f7-4140-b9fe-20cb4e51a9fe
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c39e6ac981cae6195023d63f008b1ee4b0013bbd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolfindsymbolsforacceleratorpointertag"></a>IDiaSymbol::findSymbolsForAcceleratorPointerTag
C + + AMP 스텁 함수에서 가속기 포인터 태그의 수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findSymbolsForAccleratorPointerTag (   
   DWORD             tagValue,  
   IDiaEnumSymbols** ppResult);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `tagValue`  
 [in] Pointee 기호 레코드를 발견 되는 포인터 태그 값입니다.  
  
 `ppResult`  
 [out] 에 대 한 포인터는 `IDiaEnumSymbols` 결과 사용 하 여 초기화 되는 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)