---
title: 'Idiasession:: Findchildren | Microsoft Docs'
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
- IDiaSession::findChildren method
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0cae2dd492fd11ff4a5d707ba95c571711358358
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasessionfindchildren"></a>IDiaSession::findChildren
지정한 부모 식별자의 이름 및 기호 형식에 일치 하는 모든 자식을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findChildren (   
   IDiaSymbol*       parent,  
   SymTagEnum        symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `parent`  
 [in] [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 부모를 나타내는 개체입니다. 이 부모 기호 함수, 모듈 또는 블록에 있으면 어휘 자식을에서 반환 됩니다 `ppResult`합니다. 부모 기호 형식이 면 클래스 자식은 반환 됩니다. 이 매개 변수가 `NULL`, 다음 `symtag` 으로 설정 되어 있어야 `SymTagExe` 또는 `SymTagNull`, 전역 범위 (.exe 파일)를 반환 하는 합니다.  
  
 `symtag`  
 [in] 검색할 자식의 기호 태그를 지정 합니다. 값에서 가져옵니다는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 열거 합니다. 로 설정 `SymTagNull` 를 모든 자식 요소를 검색 합니다.  
  
 `name`  
 [in] 검색할 하위 항목의 이름을 지정 합니다. 로 설정 `NULL` 를 검색할 수 있는 모든 자식에 대 한 합니다.  
  
 `compareFlags`  
 [in] 이름 일치에 적용할 비교 옵션을 지정 합니다. 값의 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md) 열거형 따로 또는 함께 사용할 수 있습니다.  
  
 `ppResult`  
 [out] 반환 된 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) 자식 기호 목록이 포함 된 개체를 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="example"></a>예  
 다음 예제에는 함수의 로컬 변수를 찾는 방법을 보여 줍니다 `pFunc` 해당 일치 하는 이름 `szVarName`합니다.  
  
```C++  
IDiaEnumSymbols* pEnum;  
pSession->findChildren( pFunc, SymTagData, szVarName, nsCaseSensitive, &pEnum );  
```  
  
## <a name="see-also"></a>참고 항목  
 [개요](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)