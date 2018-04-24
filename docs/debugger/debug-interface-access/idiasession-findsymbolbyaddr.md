---
title: 'Idiasession:: Findsymbolbyaddr | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findSymbolByAddr method
ms.assetid: c130abc5-4d0a-4d2d-8286-94fde36ddd4a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 06f3a19073c13415a2e1dd021911c391e63f87ae
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasessionfindsymbolbyaddr"></a>IDiaSession::findSymbolByAddr
포함 된 단어나 가장 가까운 지정된 된 주소에 지정 된 기호 형식을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findSymbolByAddr (   
   DWORD        isect,  
   DWORD        offset,  
   SymTagEnum   symtag,  
   IDiaSymbol** ppSymbol  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `isect`  
 [in] 섹션 구성 요소 주소를 지정 합니다.  
  
 `offset`  
 [in] 주소 오프셋된 구성 요소를 지정합니다.  
  
 `symtag`  
 [in] 찾을 기호 형식입니다. 값에서 가져옵니다는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 열거 합니다.  
  
 `ppSymbol`  
 [out] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 기호를 나타내는 개체를 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="example"></a>예제  
  
```C++  
IDiaSymbol* pFunc;  
pSession->findSymbolByAddr( isect, offset, SymTagFunction, &pFunc );  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)