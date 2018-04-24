---
title: IDiaSymbol::findChildrenExByVA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::findChildrenExByVA
ms.assetid: 29080009-36e4-4697-acd7-50f2e3e1bf1b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e1db325da7688c2c3dd8d2b87c301922d168c1ad
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasymbolfindchildrenexbyva"></a>IDiaSymbol::findChildrenExByVA
지정된 된 가상 주소에서 사용할 수 있는 기호 자식을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findChildrenExByVA (   
   enum SymTagEnum   symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   DWORD             address,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `symtag`  
 [in] 에 정의 된 대로 자식 노드를 검색할 수 기호 태그 지정의 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)합니다. 로 설정 `SymTagNull` 를 검색할 수 있는 모든 자식에 대 한 합니다.  
  
 `name`  
 [in] 검색할 하위 항목의 이름을 지정 합니다. 로 설정 `NULL` 를 검색할 수 있는 모든 자식에 대 한 합니다.  
  
 `compareFlags`  
 [in] 이름 일치에 적용할 비교 옵션을 지정 합니다. 값의 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md) 열거형 따로 또는 함께 사용할 수 있습니다.  
  
 `address`  
 [in] 가상 주소를 지정합니다.  
  
 `ppResult`  
 [out] 반환 된 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) 자식 기호 목록이 포함 된 개체를 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 기호의 자식이 하나 이상 발견 되었습니다 하거나 반환 하는 경우 `S_FALSE` 자식이 발견 되는 경우; 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 반환 되는 로컬 기호 라이브 범위 정보를 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia100.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession:: Findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md)