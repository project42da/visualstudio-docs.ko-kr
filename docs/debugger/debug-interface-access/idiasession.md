---
title: IDiaSession | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSession interface
ms.assetid: 69dab9bf-2c68-4f70-9678-3b50fba3e6fa
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f3939ab86cd9f0948a2be44756b9ed94d143ecc8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasession"></a>IDiaSession
디버그 기호에 대 한 쿼리 컨텍스트를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDiaSession : IUnknown  
```  
  
## <a name="methods"></a>메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDiaSession`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaSession::get_loadAddress](../../debugger/debug-interface-access/idiasession-get-loadaddress.md)|이 기호 저장소의 기호에 해당 하는 실행 파일에 대 한 부하 주소를 검색 합니다. 이에 전달 된 것과 동일한 값은 `put_loadAddress` 메서드.|  
|[IDiaSession::put_loadAddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)|이 기호 저장소의 기호에 해당 하는 실행 파일에 대 한 부하 주소를 설정 합니다. **참고:** 를 가져오는 경우이 메서드를 호출 해야는 `IDiaSession` 개체 및 개체를 사용 하기 전에.|  
|[IDiaSession::get_globalScope](../../debugger/debug-interface-access/idiasession-get-globalscope.md)|전역 범위에 대 한 참조를 검색합니다.|  
|[IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md)|기호 저장소에 포함 된 모든 테이블에 대 한 열거자를 검색 합니다.|  
|[IDiaSession::getSymbolsByAddr](../../debugger/debug-interface-access/idiasession-getsymbolsbyaddr.md)|정적 위치에서 모든 명명 된 기호에 대 한 열거자를 검색합니다.|  
|[IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)|지정한 부모 식별자의 이름 및 기호 형식에 일치 하는 모든 자식을 검색 합니다.|  
|[IDiaSession::findSymbolByAddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)|포함 된 단어나 가장 가까운 지정된 된 주소에 지정 된 기호 형식을 검색 합니다.|  
|[IDiaSession::findSymbolByRVA](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)|포함 된 단어나 가장 가까운 지정 된 상대 가상 주소 (RVA)에 지정 된 기호 형식을 검색 합니다.|  
|[IDiaSession::findSymbolByVA](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)|포함 된 단어나 가장 가까운 지정된 된 가상 주소 (VA)에 지정 된 기호 형식을 검색 합니다.|  
|[IDiaSession::findSymbolByToken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)|지정 된 메타 데이터 토큰을 포함 하는 기호를 검색 합니다.|  
|[IDiaSession::symsAreEquiv](../../debugger/debug-interface-access/idiasession-symsareequiv.md)|두 개의 기호 동등한 인지를 확인 합니다.|  
|[IDiaSession::symbolById](../../debugger/debug-interface-access/idiasession-symbolbyid.md)|고유 식별자로 기호를 검색합니다.|  
|[IDiaSession::findSymbolByRVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)|포함 된 단어나 가장 가까운 지정 된 상대 가상 주소와 오프셋을 지정 된 기호 형식을 검색 합니다.|  
|[IDiaSession::findSymbolByVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)|포함 된 단어나 가장 가까운 지정 된 가상 주소 및 오프셋을 지정 된 기호 형식을 검색 합니다.|  
|[IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)|컴파일 대상와 이름으로 소스 파일을 검색합니다.|  
|[IDiaSession::findFileById](../../debugger/debug-interface-access/idiasession-findfilebyid.md)|소스 파일 식별자도 소스 파일을 검색합니다.|  
|[IDiaSession::findLines](../../debugger/debug-interface-access/idiasession-findlines.md)|지정 된 컴파일 대상 및 소스 파일 식별자 내의 줄 번호를 검색합니다.|  
|[IDiaSession::findLinesByAddr](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)|지정된 된 주소를 포함 하는 지정 된 컴파일 대상에 줄을 검색 합니다.|  
|[IDiaSession::findLinesByRVA](../../debugger/debug-interface-access/idiasession-findlinesbyrva.md)|지정 된 상대 가상 주소를 포함 하는 지정 된 컴파일 대상에 줄을 검색 합니다.|  
|[IDiaSession::findLinesByVA](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)|지정 된 주소 범위에 포함 된 선에 대 한 줄 번호 정보를 찾습니다.|  
|[IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)|소스 파일 및 줄 번호로 지정된 compiland에서 줄을 검색합니다.|  
|[IDiaSession::findInjectedSource](../../debugger/debug-interface-access/idiasession-findinjectedsource.md)|컴파일 프로세스의 다른 구성 요소 또는 특성 공급자가 기호 저장소에 배치 된 소스를 검색 합니다.|  
|[IDiaSession::getEnumDebugStreams](../../debugger/debug-interface-access/idiasession-getenumdebugstreams.md)|디버그 데이터 스트림 열거 된 시퀀스를 검색합니다.|  
|[IDiaSession::findInlineFramesByAddr](../../debugger/debug-interface-access/idiasession-findinlineframesbyaddr.md)|클라이언트가 지정된 된 주소에 있는 인라인 프레임의 모든 반복 하는 데 사용 하는 열거형을 검색 합니다.|  
|[IDiaSession::findInlineFramesByRVA](../../debugger/debug-interface-access/idiasession-findinlineframesbyrva.md)|클라이언트가 지정 된 상대 가상 주소 (RVA)에 있는 인라인 프레임의 모든 반복 하는 데 사용 하는 열거형을 검색 합니다.|  
|[IDiaSession::findInlineFramesByVA](../../debugger/debug-interface-access/idiasession-findinlineframesbyva.md)|클라이언트가 지정된 된 가상 주소 (VA)에 있는 인라인 프레임의 모든 반복 하는 데 사용 하는 열거형을 검색 합니다.|  
|[IDiaSession::findInlineeLines](../../debugger/debug-interface-access/idiasession-findinlineelines.md)|클라이언트가 모든 없는 함수를 인라인 처리, 직접 또는 간접적으로 지정 된 부모 기호는 줄 번호 정보를 반복 하는 데 사용 하는 열거형을 검색 합니다.|  
|[IDiaSession::findInlineeLinesByAddr](../../debugger/debug-interface-access/idiasession-findinlineelinesbyaddr.md)|클라이언트가 모든 없는 함수를 인라인 처리, 직접 또는 간접적으로 지정 된 부모 기호는 줄 번호 정보를 반복 하는 데 사용 하 고 지정된 된 주소 범위 내에 포함 하는 열거형을 검색 합니다.|  
|[IDiaSession::findInlineeLinesByRVA](../../debugger/debug-interface-access/idiasession-findinlineelinesbyrva.md)|클라이언트가 모든 없는 함수를 인라인 처리, 직접 또는 간접적으로 지정 된 부모 기호는 줄 번호 정보를 반복 하는 데 사용 하 고 지정 된 상대 가상 주소 (RVA) 내에 포함 하는 열거형을 검색 합니다.|  
|[IDiaSession::findInlineeLinesByVA](../../debugger/debug-interface-access/idiasession-findinlineelinesbyva.md)|클라이언트가 모든 없는 함수를 인라인 처리, 직접 또는 간접적으로 지정 된 부모 기호는 줄 번호 정보를 반복 하는 데 사용 하 고 지정된 된 가상 주소 (VA) 내에 포함 하는 열거형을 검색 합니다.|  
|[IDiaSession::findInlineeLinesByLinenum](../../debugger/debug-interface-access/idiasession-findinlineelinesbylinenum.md)|클라이언트가 없는 인라인 직접 또는 간접적으로 지정 된 소스 파일과 줄 번호에 모든 함수의 줄 번호 정보를 반복 하는 데 사용 하는 열거형을 검색 합니다.|  
|[IDiaSession::findInlineesByName](../../debugger/debug-interface-access/idiasession-findinlineesbyname.md)|클라이언트가 지정된 된 이름과 일치 하는 모든 인라인 함수의 줄 번호 정보를 반복 하는 데 사용 하는 열거형을 검색 합니다.|  
|[IDiaSession::findSymbolsForAcceleratorPointerTag](../../debugger/debug-interface-access/idiasession-findsymbolsforacceleratorpointertag.md)|부모 가속기 스텁 함수에에서 지정 된 태그 값에 해당 하는 변수에 대 한 기호의 열거형을 반환 합니다.|  
|[IDiaSession::findSymbolsByRVAForAcceleratorPointerTag](../../debugger/debug-interface-access/idiasession-findsymbolsbyrvaforacceleratorpointertag.md)|해당 태그 값이 지정,이 메서드를 지정 된 상대 가상 주소에서 지정 된 부모 가속기 스텁 함수에 포함 된 기호 열거형을 반환 합니다.|  
|[IDiaSession::findAcceleratorInlineesByName](../../debugger/debug-interface-access/idiasession-findacceleratorinlineesbyname.md)|지정 된 인라인 함수 이름에 해당 하는 인라인 프레임에 대 한 기호의 열거형을 반환 합니다.|  
|[IDiaSession::findAcceleratorInlineesByLinenum](../../debugger/debug-interface-access/idiasession-findacceleratorinlineesbylinenum.md)|지정한 원본 위치에 해당 하는 인라인 프레임에 대 한 기호의 열거형을 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 호출 해야는 [idiasession:: Put_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md) 만든 후 메서드는 `IDiaSession` 개체-에 전달 된 값과는 `put_loadAddress` 메서드가 0이 아닌 값 이어야 합니다.-기호가 됩니다의 가상 주소 VA 속성에 대 한 액세스할 수 있습니다. 부하 주소 프로그램 디버깅 중인 실행 파일을 로드에서 제공 됩니다. Win32 함수를 호출할 수는 예를 들어 `GetModuleInformation` 주소를 검색 부하는 실행 파일에 대 한 실행 파일에 대 한 핸들을 지정 합니다.  
  
## <a name="example"></a>예  
 가져오는 방법을 보여 주는이 예제는 `IDiaSession` DIA SDK의 일반 초기화의 일부로 인터페이스입니다.  
  
```C++  
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
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [개요](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [Exe](../../debugger/debug-interface-access/exe.md)   
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idiadatasource:: Opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [Idiasymbol:: Findchildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)   
 [.Pdb 파일 쿼리](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)