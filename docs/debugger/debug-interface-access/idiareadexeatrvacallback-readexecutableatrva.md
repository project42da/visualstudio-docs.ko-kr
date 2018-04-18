---
title: 'Idiareadexeatrvacallback:: Readexecutableatrva | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtRVACallback::ReadExecutableAtRVA method
ms.assetid: 3c1e965f-8f05-41a8-86d8-01830b2377c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d622397984e6c1b43d1e62852652680b6a6711fb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idiareadexeatrvacallbackreadexecutableatrva"></a>IDiaReadExeAtRVACallback::ReadExecutableAtRVA
지정 된 수의 지정 된 상대 가상 주소 (RVA) 실행 파일에서 바이트를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT ReadExecutableAtRVA (   
   DWORD  relativeVirtualAddress,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `relativeVirtualAddress`  
 [in] 읽기를 시작할 실행 파일에 RVA입니다.  
  
 `cbData`  
 [in] 읽을 바이트 수입니다.  
  
 `pcbData`  
 [out] 읽은 바이트 수를 반환 합니다.  
  
 `data[]`  
 [out에서] 파일에서 읽은 바이트를 사용 하 여 입력은 배열입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 DIA 지원 코드 상대 가상 주소를 사용 하 여 실행 파일에서 데이터 바이트를 로드 하 여 호출 됩니다. 지 원하는이 메서드는 [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)