---
title: "IDiaTable | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaTable 인터페이스"
ms.assetid: c99a2c44-7b72-4e3c-b963-25fe3df3a555
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaTable
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

DIA 데이터 소스 테이블을 열거합니다.  
  
## 구문  
  
```  
IDiaTable : IEnumUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaTable`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaTable::get\_\_NewEnum](../../debugger/debug-interface-access/idiatable-get-newenum.md)|검색은 [IEnumVARIANT Interface](http://msdn.microsoft.com/ko-kr/139e3c93-faef-4003-9079-e0e94494db3e) 이 열거자의 버전입니다.|  
|[IDiaTable::get\_name](../../debugger/debug-interface-access/idiatable-get-name.md)|테이블의 이름을 검색합니다.|  
|[IDiaTable::get\_Count](../../debugger/debug-interface-access/idiatable-get-count.md)|테이블에 있는 항목의 수를 검색합니다.|  
|[IDiaTable::Item](../../debugger/debug-interface-access/idiatable-item.md)|참조는 특정 항목 인덱스를 검색합니다.|  
  
## 설명  
 이 인터페이스를 구현에서 `IEnumUnknown` Microsoft.VisualStudio.OLE.Interop 네임 스페이스에서 열거 메서드.  `IEnumUnknown` 열거 인터페이스 테이블 내용 보다는 반복에 대 한 훨씬 더 효율적입니다 있는 [IDiaTable::get\_Count](../../debugger/debug-interface-access/idiatable-get-count.md) 및 [IDiaTable::Item](../../debugger/debug-interface-access/idiatable-item.md) 메서드.  
  
 해석이 `IUnknown` 인터페이스 반환에서 `IDiaTable::Item` 메서드 또는 `Next` 메서드 \(Microsoft.VisualStudio.OLE.Interop 네임 스페이스\)에 테이블 형식에 따라 달라.  예를 들어, 경우는 `IDiaTable` 인터페이스를 삽입 한 원본 목록을 나타냅니다의 `IUnknown` 인터페이스를 쿼리 합니다는 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md) 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 얻을 [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md) 또는 [IDiaEnumTables::Next](../../debugger/debug-interface-access/idiaenumtables-next.md) 방법입니다.  
  
 다음 인터페이스 구현 되어 있는 `IDiaTable` 인터페이스 \(쿼리할 수 있습니다 즉,는 `IDiaTable` 인터페이스는 다음 인터페이스 중 하나에 대 한\):  
  
-   [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)  
  
-   [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)  
  
-   [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)  
  
-   [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)  
  
-   [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)  
  
-   [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)  
  
-   [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)  
  
## 예제  
 첫 번째 함수 `ShowTableNames`, 세션의 모든 테이블 이름을 표시 합니다.  두 번째 함수에서 `GetTable`, 모든 지정 된 인터페이스를 구현 하는 테이블에 대해 테이블을 검색 합니다.  세 번째 함수 `UseTable`를 사용 하는 방법을 보여 줍니다 있는 `GetTable` 함수.  
  
> [!NOTE]
>  `CDiaBSTR`래핑하는 클래스입니다 있는 `BSTR` 문자열 인스턴스화 범위를 벗어날 때 해제를 자동으로 처리 하 고 있습니다.  
  
```cpp#  
void ShowTableNames(IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumTables> pTables;  
    if ( FAILED( psession->getEnumTables( &pTables ) ) )  
    {  
        Fatal( "getEnumTables" );  
    }  
    CComPtr< IDiaTable > pTable;  
    while ( SUCCEEDED( hr = pTables->Next( 1, &pTable, &celt ) )  
            && celt == 1 )  
    {  
        CDiaBSTR bstrTableName;  
        if ( pTable->get_name( &bstrTableName ) != 0 )  
        {  
            Fatal( "get_name" );  
        }  
        printf( "Found table: %ws\n", bstrTableName );  
    }  
  
// Searches the list of all tables for a table that supports  
// the specified interface.  Use this function to obtain an  
// enumeration interface.  
HRESULT GetTable(IDiaSession* pSession,  
                 REFIID       iid,  
                 void**       ppUnk)  
{  
    CComPtr<IDiaEnumTables> pEnumTables;  
    HRESULT hResult;  
  
    if (FAILED(pSession->getEnumTables(&pEnumTables)))  
        Fatal("getEnumTables");  
  
    CComPtr<IDiaTable> pTable;  
    ULONG celt = 0;  
    while (SUCCEEDED(hResult = pEnumTables->Next(1, &pTable, &celt)) &&  
           celt == 1)  
    {  
        if (pTable->QueryInterface(iid, (void**)ppUnk) == S_OK)  
        {  
            return S_OK;  
        }  
        pTable = NULL;  
    }  
  
    if (FAILED(hResult))  
        Fatal("EnumTables->Next");  
  
    return E_FAIL;  
}  
  
// This function shows how to use the GetTable function.  
void UseTable(IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumSegments> pEnumSegments;  
    if (SUCCEEDED(GetTable(pSession, __uuidof(IDiaEnumSegments), &pEnumSegments)))  
    {  
        // Do something with pEnumSegments.  
    }  
}  
```  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)   
 [IDiaEnumTables::Next](../../debugger/debug-interface-access/idiaenumtables-next.md)