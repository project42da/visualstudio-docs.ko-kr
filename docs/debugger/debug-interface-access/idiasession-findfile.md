---
title: 'Idiasession:: Findfile | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSession::findFile method
ms.assetid: a215dc21-b316-40d7-9923-55bfa014976b
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ef230d1b82992f769011e0cb1d9d4ff11145b82d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasessionfindfile"></a>IDiaSession::findFile
컴파일 대상와 이름으로 소스 파일을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findFile (   
   IDiaSymbol*           pCompiland,  
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumSourceFiles** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCompiland`  
 [in] [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) compiland 검색에 사용할 컨텍스트를 나타내는 개체입니다. 이 매개 변수를 설정 `NULL` 모든 컴파일 대상에 소스 파일을 찾을 수 있습니다.  
  
 `name`  
 [in] 검색할 원본 파일의 이름을 지정 합니다. 이 매개 변수를 설정 `NULL` 에 모든 소스 파일을 검색할 수 있습니다.  
  
 `option`  
 [in] 이름 검색에 적용 된 비교 옵션을 지정 합니다. 값의 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md) 열거형 따로 또는 함께 사용할 수 있습니다.  
  
 `ppResult`  
 [out] 반환 된 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md) 소스 파일의 목록을 포함 하는 개체를 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="example"></a>예제  
  
```C++  
IDiaEnumSourceFiles* pEnum;  
pSession->findFile( NULL, L"sourcefile.cpp", nsFNameExt, &pEnum );  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md)