---
title: 'Idiasession:: Symbolbyid | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symbolById method
ms.assetid: 062e4b5a-9c4d-4703-88da-ec13102c2b66
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 55e5e2815985aacd43603d24f1c6f4052b66c19c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasessionsymbolbyid"></a>IDiaSession::symbolById
고유 식별자로 기호를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT symbolById (   
   DWORD        id,  
   IDiaSymbol** ppSymbol  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `id`  
 [in] 고유 식별자입니다.  
  
 `ppSymbol`  
 [out] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 기호를 나타내는 개체를 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 지정된 된 식별자가 고유 하 게 만들 모든 기호 DIA SDK에서 내부적으로 사용 하는 고유 값입니다.  
  
 이 방법을 사용할 수, 예를 들어 다른 기호 형식을 나타내는 기호를 검색할 수 (예제 참조).  
  
## <a name="example"></a>예제  
 이 예제에서는 검색 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 다른 기호 형식을 나타내는입니다. 사용 하는 방법을 보여 주는이 예제는 `symbolById` 세션에서 메서드. 호출 하는 것 보다 간단한 방법은 [idiasymbol:: Get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md) 형식 기호를 직접 검색 하는 메서드입니다.  
  
```C++  
IDiaSymbol *GetSymbolType(IDiaSymbol *pSymbol, IDiaSession *pSession)  
{  
    IDiaSymbol *pTypeSymbol = NULL;  
    if (pSymbol != NULL && pSession != NULL)  
    {  
        DWORD symbolTypeId;  
        pSymbol->get_typeId(&symbolTypeId);  
        pSession->symbolById(symbolTypeId, &pTypeSymbol);  
    }  
    return(pTypeSymbol);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)