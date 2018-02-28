---
title: IDiaSymbol::findChildrenEx | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::findChildrenEx
ms.assetid: 6e045045-da8c-4338-9423-81a1ca20c405
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2eb4bc5492797280845120bd34ae4bbc89f4dd95
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolfindchildrenex"></a>IDiaSymbol::findChildrenEx
기호의 자식을 검색합니다. 반환 되는 로컬 기호에서 최적화 프로그램은 컴파일된 경우 라이브 범위 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findChildrenEx (   
   enum SymTagEnum   symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
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
  
 `ppResult`  
 [out] 반환 된 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) 자식 기호 목록이 포함 된 개체를 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 기호의 자식이 하나 이상 발견 되었습니다 하거나 반환 하는 경우 `S_FALSE` 자식이 발견 되는 경우; 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 확장 된 버전의 [idiasymbol:: Findchildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)합니다.  
  
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