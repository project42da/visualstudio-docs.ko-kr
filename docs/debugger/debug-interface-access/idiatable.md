---
title: IDiaTable | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaTable interface
ms.assetid: c99a2c44-7b72-4e3c-b963-25fe3df3a555
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8f596d2c51c5d5e543ed67212662c5096ea2e4eb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiatable"></a>IDiaTable
DIA 데이터 소스 테이블을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDiaTable : IEnumUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDiaTable`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaTable::get__NewEnum](../../debugger/debug-interface-access/idiatable-get-newenum.md)|검색 된 [IEnumVARIANT 인터페이스](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e) 이 열거자의 버전입니다.|  
|[IDiaTable::get_name](../../debugger/debug-interface-access/idiatable-get-name.md)|테이블의 이름을 검색합니다.|  
|[IDiaTable::get_Count](../../debugger/debug-interface-access/idiatable-get-count.md)|테이블의 항목 수를 검색합니다.|  
|[IDiaTable::Item](../../debugger/debug-interface-access/idiatable-item.md)|특정 항목 인덱스에 대 한 참조를 검색합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스를 구현 하는 `IEnumUnknown` 열거형 메서드에 Microsoft.VisualStudio.OLE.Interop 네임 스페이스에 있습니다. `IEnumUnknown` 열거형 인터페이스에 대 한 보다 테이블 내용을 반복 훨씬 더 효율적입니다.는 [idiatable:: Get_count](../../debugger/debug-interface-access/idiatable-get-count.md) 및 [idiatable:: Item](../../debugger/debug-interface-access/idiatable-item.md) 메서드.  
  
 해석은 `IUnknown` 인터페이스 중 하나에서 반환 된는 `IDiaTable::Item` 메서드 또는 `Next` 메서드 (Microsoft.VisualStudio.OLE.Interop 네임 스페이스)는 테이블의 유형에 따라 다릅니다. 예를 들어 경우는 `IDiaTable` 삽입 된 소스의 목록을 나타냅니다.이 인터페이스는 `IUnknown` 인터페이스에 대해 쿼리해야는 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md) 인터페이스 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 가져올는 [idiaenumtables:: Item](../../debugger/debug-interface-access/idiaenumtables-item.md) 또는 [idiaenumtables:: Next](../../debugger/debug-interface-access/idiaenumtables-next.md) 메서드.  
  
 와 다음 인터페이스는 구현에서 `IDiaTable` 인터페이스 (즉, 쿼리할 수 있습니다는 `IDiaTable` 다음 인터페이스 중 하나에 대 한 인터페이스):  
  
-   [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)  
  
-   [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)  
  
-   [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)  
  
-   [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)  
  
-   [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)  
  
-   [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)  
  
-   [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)  
  
## <a name="example"></a>예  
 첫 번째 함수 `ShowTableNames`, 세션에 모든 테이블의 이름을 표시 합니다. 두 번째 함수 `GetTable`, 지정된 된 인터페이스를 구현 하는 테이블에 대 한 테이블의 모든 검색 합니다. 세 번째 함수 `UseTable`를 사용 하는 방법을 보여 줍니다.는 `GetTable` 함수입니다.  
  
> [!NOTE]
>  `CDiaBSTR`래핑하는 클래스는 `BSTR` 인스턴스화 범위를 벗어나면 문자열이 해제를 자동으로 처리 하 고 있습니다.  
  
```C++  
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
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [Idiaenumtables:: Item](../../debugger/debug-interface-access/idiaenumtables-item.md)   
 [IDiaEnumTables::Next](../../debugger/debug-interface-access/idiaenumtables-next.md)