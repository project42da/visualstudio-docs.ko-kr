---
title: IDiaSession::findSymbolsByRVAForAcceleratorPointerTag | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a073cc45-0c7b-417e-b5fc-a3b08beccdbc
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ebeb2ae079845c55c1903afdbcef381a5b4d379c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasessionfindsymbolsbyrvaforacceleratorpointertag"></a>IDiaSession::findSymbolsByRVAForAcceleratorPointerTag
해당 태그 값이 지정,이 메서드를 지정 된 상대 가상 주소에서 지정 된 부모 가속기 스텁 함수에 포함 된 기호 열거형을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findSymbolsByRVAForAcceleratorPointerTag (   
   IDiaSymbol*           parent,  
   DWORD                 tagValue,  
   DWORD                 rva,  
   IDiaEnumSymbols**     ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `parent`  
 [in] `IDiaSymbol` 검색할 가속기 스텁 함수에 해당 하는 합니다.  
  
 `tagValue`  
 [in] 포인터 태그 값입니다.  
  
 `rva`  
 [in] 상대 가상 주소입니다.  
  
 `ppResult`  
 [out] 에 대 한 포인터는 `IDiaEnumSymbols` 결과 함께 초기화 된 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 경우에이 메서드는 `IDiaSymbol` 가속기 스텁 함수에 해당 하는 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)