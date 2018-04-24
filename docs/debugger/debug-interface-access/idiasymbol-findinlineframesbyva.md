---
title: IDiaSymbol::findInlineFramesByVA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 54295d3e-bbb6-4c10-ab9d-adcfc22b1f71
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e06f5d4a215db9fa57172ca0cc7646be697a20d7
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasymbolfindinlineframesbyva"></a>IDiaSymbol::findInlineFramesByVA
클라이언트가 지정된 된 가상 주소 (VA)에 있는 인라인 프레임의 모든 반복 하는 데 사용 하는 열거형을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findInlineFramesByVA (   
   ULONGLONG         va,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `va`  
 [in] VA.로 주소를 지정합니다.  
  
 `ppResult`  
 [out] 보유 한 `IDiaEnumSymbols` 검색 된 프레임의 목록을 포함 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)