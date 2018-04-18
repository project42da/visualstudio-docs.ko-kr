---
title: 'Idiastackwalkhelper:: Symbolforva | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper::symbolForVA method
ms.assetid: 8dd9455d-d44c-4dd6-a0aa-31131cbea2aa
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4eca0dd63e70d69c19ec79b5db4bc96d807fb68
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idiastackwalkhelpersymbolforva"></a>IDiaStackWalkHelper::symbolForVA
지정된 된 가상 주소를 포함 하는 기호를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT symbolForVA(   
   ULONGLONG     va,  
   IDiaSymbol**  ppSymbol  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `va`  
 [in] 요청 된 기호에 포함 되어 있는 가상 주소입니다. 기호 여야 합니다는 `SymTagFunctionType` (의 값은 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 열거형)입니다.  
  
 `ppSymbol`  
 [out] [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 지정된 된 주소에서 기호를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)