---
title: IDiaSession::findAcceleratorInlineesByLinenum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 386c87aa-f7b2-4d38-9dd6-fffba9ff01f0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de8c5e7b5c039e43a5e513c72b270342a705b8b2
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasessionfindacceleratorinlineesbylinenum"></a>IDiaSession::findAcceleratorInlineesByLinenum
지정한 원본 위치에 해당 하는 인라인 프레임에 대 한 기호의 열거형을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findAcceleratorInlineeLinesByName (   
   IDiaSymbol*           parent,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 colnum,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `parent`  
 [in] `IDiaSymbol` 검색 하는 가속기 스텁 함수에 해당 하는 합니다.  
  
 `file`  
 [in] `IDiaSourceFile` 원본 위치입니다.  
  
 `linenum`  
 [in] 원본 위치의 줄 번호입니다.  
  
 `colnum`  
 [in] 원본 위치의 열 번호입니다.  
  
 `ppResult`  
 [out] 에 대 한 포인터는 `IDiaEnumLineNumbers` 결과 함께 초기화 된 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)