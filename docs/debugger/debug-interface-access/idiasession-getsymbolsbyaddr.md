---
title: 'Idiasession:: Getsymbolsbyaddr | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSession::getSymbolsByAddr method
ms.assetid: eafcc757-b488-487d-a063-ad3703ff42e8
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa3467ad1129ea7f64444bfff0c8762c117cea1a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasessiongetsymbolsbyaddr"></a>IDiaSession::getSymbolsByAddr
해당 주소 순서로 기호를 발견 하는 열거자를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT getSymbolsByAddr(   
   IDiaEnumSymbolsByAddr** ppEnumbyAddr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppEnumbyAddr`  
 [out] 반환 된 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md) 개체입니다. 이 인터페이스를 사용 하 여 메모리 위치에 따라 기호 저장소에 대 한 기호를 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)