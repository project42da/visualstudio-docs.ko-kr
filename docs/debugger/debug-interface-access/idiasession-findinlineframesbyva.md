---
title: IDiaSession::findInlineFramesByVA | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: df9e68f6-e0a4-4cf6-b11d-61c40351e0cd
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1f9ef4aa471ca4bf12e2d609f7b0dcd6129b644a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasessionfindinlineframesbyva"></a>IDiaSession::findInlineFramesByVA
클라이언트가 지정된 된 가상 주소 (VA)에 있는 인라인 프레임의 모든 반복 하는 데 사용 하는 열거형을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findInlineFramesByVA (   
   IDiaSymbol*       parent,   ULONGLONG         va,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `parent`  
 [in] `IDiaSymbol` 부모를 나타내는 개체입니다.  
  
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