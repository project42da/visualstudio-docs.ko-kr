---
title: 'Idiadatasource:: Opensession | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaDataSource::openSession method
ms.assetid: a3319ed0-3979-483b-9852-c0af96852c48
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 72fa36bd077a08484c225e1349134929e541d074
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiadatasourceopensession"></a>IDiaDataSource::openSession
기호를 쿼리 하기 위한 세션을 엽니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT openSession (   
   IDiaSession** ppSession  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 ppSession  
 [out] 반환 된 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 세션 열기를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 다음 표에서이 메서드에 대 한 가능한 반환 값을 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|E_UNEXPECTED|[IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md) 개체가 기호의 원본과 이전에 초기화 되지 않았습니다.|  
|E_INVALIDARG|잘못 된 `ppSession` 매개 변수입니다.|  
|E_OUTOFMEMORY|세션을 열고 메모리가 부족 합니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 엽니다는 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 데이터 원본에 대 한 개체입니다.  
  
 `IDiaSession`개체는 데이터 소스에 쿼리를 구현합니다. 세션을 각 집합 디버그 기호에 대 한 주소 공간을 관리합니다. 데이터 원본 기호에 의해 설명 하는.exe 또는.dll 파일은 여러 주소에 활성 범위 (예를 들어 여러 프로세스가 있으므로 로드) 한 다음 각 주소 범위에 대 한 세션을 사용 해야 합니다.  
  
## <a name="example"></a>예제  
  
```C++  
IDiaSession* pSession;  
HRESULT hr = pSource->openSession( &pSession );  
if (FAILED(hr))  
{  
   // report error  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [개요](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [.Pdb 파일 쿼리](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)