---
title: 'Idiasession:: Findlines | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLines method
ms.assetid: d6e84916-fd55-457e-b057-57f97b51fe73
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eb256778f2bf92827ff98c5cafbb77bfdcba6c12
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasessionfindlines"></a>IDiaSession::findLines
지정 된 컴파일 대상 및 소스 파일 식별자 내의 줄 번호를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findLines (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `compiland`  
 [in] [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 컴파일 대상을 나타내는 개체입니다. 이 인터페이스를 사용 하 여 줄 번호를 검색 하는 컨텍스트.  
  
 `file`  
 [in] [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 줄 번호에 대 한 검색 하려는 소스 파일을 나타내는 개체입니다.  
  
 `ppResult`  
 [out] 반환 된 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) 줄 번호의 목록을 포함 하는 개체를 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)