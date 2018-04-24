---
title: 'Idiasymbol:: Get_type | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_type method
ms.assetid: 1c6a4176-dd4e-4c22-8b8f-0e559fc078ba
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 414c66b000a7cd81783ec963d78105792d6b816b
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasymbolgettype"></a>IDiaSymbol::get_type
이 기호에 대 한 형식을 나타내는 기호를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_type (   
   IDiaSymbol** pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 이 기호의 형식을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 의미는 속성은 해당 기호를 사용할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 를 기호는 형식을 확인 하려면이 메서드를 호출 하 고 결과 검사 해야 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 개체입니다. 에 형식이 없는 기호에 대 한 수 있다는 것을 참고 합니다. 예를 들어 구조의 이름에는 형식이 없습니다 되지만 자식 기호를 가질 수 있습니다 (사용 하 여는 [idiasymbol:: Findchildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md) 이러한 자식도 검사 하는 메서드).  
  
## <a name="example"></a>예제  
  
```C++  
IDiaSymbol*         pType;  
CComPtr<IDiaSymbol> pBaseType;  
if (SUCCEEDED(pType->get_type( &pBaseType ))) {  
    BasicType btBaseType;  
    if (SUCCEEDED(pBaseType->get_baseType((DWORD *)&btBaseType))) {  
        // Do something with basic type.  
    }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Idiasymbol:: Get_basetype](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)