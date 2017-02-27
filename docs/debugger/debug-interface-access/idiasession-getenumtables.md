---
title: "IDiaSession::getEnumTables | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaSession::getEnumTables 메서드"
ms.assetid: 66e0fba2-ca63-4e24-a46a-c99c7fb61dd1
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSession::getEnumTables
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호 저장소에 포함 된 모든 테이블에 대 한 열거자를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT getEnumTables (   
   IDiaEnumTables** ppEnumTables  
);  
```  
  
#### 매개 변수  
 `ppEnumTables`  
 \[out\] 반환 된 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md) 개체입니다.  이 인터페이스를 사용 하 여 테이블에 있는 기호 저장소를 열거 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
 이 예제에서는 사용 하는 일반 함수를 표시 합니다.의 `getEnumTables` 메서드가 특정 열거자 개체를 얻어야 합니다.  열거자가 있으면 함수가 원하는 인터페이스에 캐스팅 될 수에 대 한 포인터를 반환 합니다. 그렇지 않으면 함수가 반환 `NULL`.  
  
```cpp#  
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
  
## 참고 항목  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)