---
title: 'Idiasession:: Getenumtables | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::getEnumTables method
ms.assetid: 66e0fba2-ca63-4e24-a46a-c99c7fb61dd1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7556999e1455dcfa0d79b131ee4661a77732990f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasessiongetenumtables"></a>IDiaSession::getEnumTables
기호 저장소에 포함 된 모든 테이블에 대 한 열거자를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT getEnumTables (   
   IDiaEnumTables** ppEnumTables  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppEnumTables`  
 [out] 반환 된 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md) 개체입니다. 이 인터페이스를 사용 하 여 기호 저장소의 테이블을 열거 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 제공 하는 일반 함수를 사용 하는 `getEnumTables` 특정 열거자 개체를 얻는 메서드를 합니다. 함수 캐스팅 될 수 있는 포인터는 원하는 인터페이스를 반환 하는 경우 열거자가 발견 되 면 그렇지 않으면 함수가 반환 `NULL`합니다.  
  
```C++  
IUnknown *GetTable(IDiaSession *pSession, REFIID iid)  
{  
    IUnknown *pUnknown = NULL;  
    if (pSession != NULL)  
    {  
        CComPtr<IDiaEnumTables> pEnumTables;  
        if (pSession->getEnumTables(&pEnumTables) == S_OK)  
        {  
             CComPtr<IDiaTable> pTable;  
             DWORD celt = 0;  
             while(pEnumTables->Next(1,&pTable,&celt) == S_OK &&  
                   celt == 1)  
             {  
                  if (pTable->QueryInterface(iid, (void **)pUnknown) == S_OK)  
                  {  
                       break;  
                  }  
                  pTable = NULL;  
             }  
        }  
    }  
    return(pUnknown);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)