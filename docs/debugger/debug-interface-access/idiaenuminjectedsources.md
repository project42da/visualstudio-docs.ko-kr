---
title: "IDiaEnumInjectedSources | Microsoft Docs"
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
  - "IDiaEnumInjectedSources 인터페이스"
ms.assetid: f97e2392-22e1-48da-b7ce-ad94c8b684b0
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# IDiaEnumInjectedSources
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

데이터 원본에 포함 된 다양 한 삽입 한 소스를 열거 합니다.  
  
## 구문  
  
```  
IDiaEnumInjectedSources : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaEnumInjectedSources`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaEnumInjectedSources::get\_\_NewEnum](../../debugger/debug-interface-access/idiaenuminjectedsources-get-newenum.md)|검색은 [IEnumVARIANT Interface](http://msdn.microsoft.com/ko-kr/139e3c93-faef-4003-9079-e0e94494db3e) 이 열거자의 버전입니다.|  
|[IDiaEnumInjectedSources::get\_Count](../../debugger/debug-interface-access/idiaenuminjectedsources-get-count.md)|삽입 한 소스를 검색합니다.|  
|[IDiaEnumInjectedSources::Item](../../debugger/debug-interface-access/idiaenuminjectedsources-item.md)|주입 된 원본 방법으로 인덱스를 검색합니다.|  
|[IDiaEnumInjectedSources::Next](../../debugger/debug-interface-access/idiaenuminjectedsources-next.md)|삽입 한 원본 열거 시퀀스에서 지정 된 수를 검색합니다.|  
|[IDiaEnumInjectedSources::Skip](../../debugger/debug-interface-access/idiaenuminjectedsources-skip.md)|삽입 한 원본 열거 시퀀스에서 지정 된 수를 건너뜁니다.|  
|[IDiaEnumInjectedSources::Reset](../../debugger/debug-interface-access/idiaenuminjectedsources-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[IDiaEnumInjectedSources::Clone](../../debugger/debug-interface-access/idiaenuminjectedsources-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
  
## 설명  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 가져온는 [IDiaSession::findInjectedSource](../../debugger/debug-interface-access/idiasession-findinjectedsource.md) 메서드를 호출 하거나 특정 소스 파일의 이름으로는 [IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md) GUID와 메서드는 `IDiaEnumInjectedSources` 인터페이스.  
  
## 예제  
 가져오는 방법을 보여 주는이 예제 \(의 `GetEnumInjectedSources` 함수\) 사용 \(는 `DumpAllInjectedSources` 함수\)는 `IDiaEnumInjectedSources` 인터페이스입니다.  참조는 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md) 인터페이스의 구현에 대 한의 `PrintPropertyStorage` 함수.  있는 대체 출력에 대 한 참조를 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md) 인터페이스입니다.  
  
```cpp#  
  
IDiaEnumInjectedSources* GetEnumInjectedSources(IDiaSession *pSession)  
{  
    IDiaEnumInjectedSources* pUnknown    = NULL;  
    REFIID                   iid         = __uuidof(IDiaEnumInjectedSources);  
    IDiaEnumTables*          pEnumTables = NULL;  
    IDiaTable*               pTable      = NULL;  
    ULONG                    celt        = 0;  
  
    if (pSession->getEnumTables(&pEnumTables) != S_OK)  
    {  
        wprintf(L"ERROR - GetTable() getEnumTables\n");  
        return NULL;  
    }  
    while (pEnumTables->Next(1, &pTable, &celt) == S_OK && celt == 1)  
    {  
        // There is only one table that matches the given iid  
        HRESULT hr = pTable->QueryInterface(iid, (void**)&pUnknown);  
        pTable->Release();  
        if (hr == S_OK)  
        {  
            break;  
        }  
    }  
    pEnumTables->Release();  
    return pUnknown;  
}  
  
void DumpAllInjectedSources( IDiaSession* pSession)  
{  
    IDiaEnumInjectedSources* pEnumInjSources;  
  
    pEnumInjSources = GetEnumInjectedSources(pSession);  
    if (pEnumInjSources != NULL)  
    {  
        IDiaInjectedSource* pInjSource;  
        ULONG celt = 0;  
  
        while(pEnumInjSources->Next(1, &pInjSource, &celt) == S_OK &&  
              celt == 1)  
        {  
            IDiaPropertyStorage *pPropertyStorage;  
            if (pInjSource->QueryInterface(__uuidof(IDiaPropertyStorage),  
                                           (void **)&pPropertyStorage) == S_OK)  
            {  
                PrintPropertyStorage(pPropertyStorage);  
                pPropertyStorage->Release();  
            }  
            pInjSource->Release();  
        }  
        pEnumInjSources->Release();  
    }  
}  
```  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaSession::findInjectedSource](../../debugger/debug-interface-access/idiasession-findinjectedsource.md)   
 [IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md)   
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)   
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)