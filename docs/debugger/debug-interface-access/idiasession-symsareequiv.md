---
title: 'Idiasession:: Symsareequiv | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symsAreEquiv method
ms.assetid: 9941d520-e203-46c0-83c3-b3a967f4fc59
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cc92a38305e7cc8c74b4ada0d560b314ed92da8f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasessionsymsareequiv"></a>IDiaSession::symsAreEquiv
두 개의 기호 동등한 인지를 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT symsAreEquiv (   
   IDiaSymbol* symbolA,  
   IDiaSymbol* symbolB  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `symbolA`  
 [in] 첫 번째 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 비교에 사용 되는 개체입니다.  
  
 `symbolB`  
 [in] 두 번째 `IDiaSymbol` 비교에 사용 되는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 기호 동등한 인 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE`, 기호는 서로 다릅니다. 그렇지 않은 경우 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)