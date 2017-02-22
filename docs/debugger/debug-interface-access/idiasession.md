---
title: "IDiaSession | Microsoft Docs"
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
  - "IDiaSession 인터페이스"
ms.assetid: 69dab9bf-2c68-4f70-9678-3b50fba3e6fa
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSession
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 기호에 대한 쿼리 컨텍스트를 제공합니다.  
  
## 구문  
  
```  
IDiaSession : IUnknown  
```  
  
## 메서드  
 다음 표에서는 `IDiaSession`의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaSession::get\_loadAddress](../../debugger/debug-interface-access/idiasession-get-loadaddress.md)|이 기호 저장소의 기호가 해당되는 실행 파일의 로드 주소를 검색합니다.  이는 `put_loadAddress` 메서드에 전달된 값과 동일합니다.|  
|[IDiaSession::put\_loadAddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)|이 기호 저장소의 기호를 해당하는 해당 실행 파일의 로드 주소를 설정합니다. **Note:**  `IDiaSession` 개체를 가져온 경우 이 개체를 사용하기 전에 이 메서드를 호출하는 것이 중요합니다.|  
|[IDiaSession::get\_globalScope](../../debugger/debug-interface-access/idiasession-get-globalscope.md)|전역 범위에 대한 참조를 검색합니다.|  
|[IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md)|기호 저장소에 포함 된 모든 테이블에 대한 열거자를 검색합니다.|  
|[IDiaSession::getSymbolsByAddr](../../debugger/debug-interface-access/idiasession-getsymbolsbyaddr.md)|정적 위치에서 모든 명명 된 기호에 대한 열거자를 검색합니다.|  
|[IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)|이름과 기호가 일치하는 모든 자식의 지정 부모 식별자를 검색합니다.|  
|[IDiaSession::findSymbolByAddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)|지정된 주소를 포함하거나 가장 가까운 지정된 기호 형식을 검색합니다.|  
|[IDiaSession::findSymbolByRVA](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)|지정된 상대 가상 주소\(RVA\)를 포함하거나 가장 가까운 지정된 기호 형식을 검색합니다.|  
|[IDiaSession::findSymbolByVA](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)|지정된 가상 주소\(VA\)를 포함하거나 가장 가까운 지정된 기호 형식을 검색합니다.|  
|[IDiaSession::findSymbolByToken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)|지정된 메타 데이터 토큰을 포함하는 기호를 검색합니다.|  
|[IDiaSession::symsAreEquiv](../../debugger/debug-interface-access/idiasession-symsareequiv.md)|두 기호가 동일한지 확인합니다.|  
|[IDiaSession::symbolById](../../debugger/debug-interface-access/idiasession-symbolbyid.md)|그 고유 식별자를 통해 기호를 검색합니다.|  
|[IDiaSession::findSymbolByRVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)|지정된 상대 가상 주소 및 오프셋을 포함하거나 가장 가까이 있는 지정된 기호 형식을 검색합니다.|  
|[IDiaSession::findSymbolByVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)|지정된 가상 주소 및 오프셋을 포함하거나 가장 가까운 지정된 기호 형식을 검색합니다.|  
|[IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)|컴파일과 이름으로 원본 파일을 검색합니다.|  
|[IDiaSession::findFileById](../../debugger/debug-interface-access/idiasession-findfilebyid.md)|원본 파일 식별자로 원본 파일을 검색합니다.|  
|[IDiaSession::findLines](../../debugger/debug-interface-access/idiasession-findlines.md)|지정된 컴파일 대상 및 원본 파일 식별자 내의 줄 번호를 검색합니다.|  
|[IDiaSession::findLinesByAddr](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)|지정된 주소가 포함 된 지정된 컴파일에서 줄을 검색합니다.|  
|[IDiaSession::findLinesByRVA](../../debugger/debug-interface-access/idiasession-findlinesbyrva.md)|지정된 상대 가상 주소가 포함 된 지정된 컴파일에서 줄을 검색합니다.|  
|[IDiaSession::findLinesByVA](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)|지정된 주소 범위에 포함된 줄의 줄 번호 정보를 찾습니다.|  
|[IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)|원본 파일 식별자 및 줄 번호로 지정된 컴파일에서 줄을 검색합니다.|  
|[IDiaSession::findInjectedSource](../../debugger/debug-interface-access/idiasession-findinjectedsource.md)|특성 공급자에 의해 기호 저장소에 배치된 소스나 컴파일 프로세스의 다른 구성 요소를 검색합니다.|  
|[IDiaSession::getEnumDebugStreams](../../debugger/debug-interface-access/idiasession-getenumdebugstreams.md)|디버그 데이터 스트림의 열거 시퀀스를 검색합니다.|  
|[IDiaSession::findInlineFramesByAddr](../../debugger/debug-interface-access/idiasession-findinlineframesbyaddr.md)|주어진된 주소에서 인라인 프레임을 통해 반복 하는 클라이언트를 허용 하는 열거형을 가져옵니다.|  
|[IDiaSession::findInlineFramesByRVA](../../debugger/debug-interface-access/idiasession-findinlineframesbyrva.md)|지정한 상대 가상 주소 \(RVA\)에서 인라인 프레임을 통해 반복 하는 클라이언트가 열거형을 검색 합니다.|  
|[IDiaSession::findInlineFramesByVA](../../debugger/debug-interface-access/idiasession-findinlineframesbyva.md)|인라인 프레임에 지정 된 가상 주소 \(VA\)을 통해 반복 하는 클라이언트를 허용 하는 열거형을 가져옵니다.|  
|[IDiaSession::findInlineeLines](../../debugger/debug-interface-access/idiasession-findinlineelines.md)|열거형을 직접 인라인을 하지 않은 모든 함수 또는 간접적으로 지정 된 부모 기호로 줄 번호 정보를 반복 하는 클라이언트 수를 검색 합니다.|  
|[IDiaSession::findInlineeLinesByAddr](../../debugger/debug-interface-access/idiasession-findinlineelinesbyaddr.md)|줄 번호 정보가 직접 인라인, 될 모든 함수 또는 지정한 부모 기호로 간접적으로 반복 하는 클라이언트를 허용 하 고 지정 된 주소 범위 내에 포함 된 열거형을 검색 합니다.|  
|[IDiaSession::findInlineeLinesByRVA](../../debugger/debug-interface-access/idiasession-findinlineelinesbyrva.md)|줄 번호 정보가 직접 인라인, 될 모든 함수 또는 지정한 부모 기호로 간접적으로 반복 하는 클라이언트를 허용 하 고 지정한 상대 가상 주소 내 \(RVA\)가 포함 된 열거형을 검색 합니다.|  
|[IDiaSession::findInlineeLinesByVA](../../debugger/debug-interface-access/idiasession-findinlineelinesbyva.md)|줄 번호 정보가 직접 인라인, 될 모든 함수 또는 지정한 부모 기호로 간접적으로 반복 하는 클라이언트를 허용 하 고 지정 된 가상 주소 \(VA\) 내에 포함 된 열거형을 검색 합니다.|  
|[IDiaSession::findInlineeLinesByLinenum](../../debugger/debug-interface-access/idiasession-findinlineelinesbylinenum.md)|열거형에는 줄 번호 정보를 직접 또는 간접적으로 지정 된 소스 파일 및 줄 번호를에서 인라인인 모든 함수를 반복 하는 클라이언트 수를 검색 합니다.|  
|[IDiaSession::findInlineesByName](../../debugger/debug-interface-access/idiasession-findinlineesbyname.md)|지정한 이름과 일치 하는 모든 인라인된 함수 줄 번호 정보를 통해 반복 하는 클라이언트가 열거형을 검색 합니다.|  
|[IDiaSession::findSymbolsForAcceleratorPointerTag](../../debugger/debug-interface-access/idiasession-findsymbolsforacceleratorpointertag.md)|열거형의 기호에 지정 된 태그 값을 해당 변수의 부모 가속기 스텁 함수를 반환 합니다.|  
|[IDiaSession::findSymbolsByRVAForAcceleratorPointerTag](../../debugger/debug-interface-access/idiasession-findsymbolsbyrvaforacceleratorpointertag.md)|해당 태그 값이 주어진 경우이 열거형에 포함 된 기호를 지정한 상대 가상 주소에 지정 된 부모 가속기 스텁 함수에서 반환 됩니다.|  
|[IDiaSession::findAcceleratorInlineesByName](../../debugger/debug-interface-access/idiasession-findacceleratorinlineesbyname.md)|기호를 지정한 인라인 함수 이름에 해당 하는 인라인 프레임의 열거형을 반환 합니다.|  
|[IDiaSession::findAcceleratorInlineesByLinenum](../../debugger/debug-interface-access/idiasession-findacceleratorinlineesbylinenum.md)|열거형의 기호에 해당 하는 인라인 프레임을 지정 된 소스 위치를 반환 합니다.|  
  
## 설명  
 `IDiaSession` 개체를 만든 후 [IDiaSession::put\_loadAddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md) 메서드를 호출하는 것이 중요하며, `put_loadAddress` 메서드에 전달된 값은 액세스할 기호의 모든 VA\(가상 주소\) 속성에 대해 0이 아니어야 합니다.  모든 프로그램에서 디버깅 중인 실행 파일을 로드할 때 로드 주소가 제공됩니다.  예를 들어, Win32 함수인 `GetModuleInformation`을 호출하여 핸들을 실행 가능 상태로 지정하면서 실행 가능한 상태의 로드 주소를 검색할 수 있습니다.  
  
## 예제  
 이 예제에서는 `IDiaSession` 인터페이스를 획득하여 사용자 정의 유형 \(UDTs\)를 나열하고 있는 그 열거형을 사용하는 방법을 보여 줍니다.  
  
```cpp#  
CComPtr<IDiaDataSource> pSource;  
ComPtr<IDiaSession> psession;  
  
void InitializeDIA(const char *szFilename)  
{  
    HRESULT hr = CoCreateInstance( CLSID_DiaSource,  
                                   NULL,  
                                   CLSCTX_INPROC_SERVER,  
                                   __uuidof( IDiaDataSource ),  
                                  (void **) &pSource);  
    if (FAILED(hr))  
    {  
        Fatal("Could not CoCreate CLSID_DiaSource. Register msdia80.dll." );  
    }  
    wchar_t wszFilename[ _MAX_PATH ];  
    mbstowcs( wszFilename,  
              szFilename,  
              sizeof( wszFilename )/sizeof( wszFilename[0] ) );  
    if ( FAILED( pSource->loadDataFromPdb( wszFilename ) ) )  
    {  
        if ( FAILED( pSource->loadDataForExe( wszFilename, NULL, NULL ) ) )  
        {  
            Fatal( "loadDataFromPdb/Exe" );  
        }  
    }  
    if ( FAILED( pSource->openSession( &psession ) ) )  
    {  
        Fatal( "openSession" );  
    }  
}  
```  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [개요](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [Exe](../../debugger/debug-interface-access/exe.md)   
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)   
 [.Pdb 파일 쿼리](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)