---
title: 'Idiasymbol:: Get_symtag | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_symTag method
ms.assetid: 139a35bd-faeb-4878-be72-394dedfbb18f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 029dee2188f48d2f41368c965542670e5512f7e5
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasymbolgetsymtag"></a>IDiaSymbol::get_symTag
기호 형식 분류자를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_symTag (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 값을 반환 된 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 기호 형식 분류자를 지정 하는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 의미는 속성은 해당 기호를 사용할 수 없습니다.  
  
## <a name="example"></a>예제  
  
```C++  
IDiaSymbol* pType;  
DWORD       tag = 0;  
pType->get_symTag( &tag );  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)