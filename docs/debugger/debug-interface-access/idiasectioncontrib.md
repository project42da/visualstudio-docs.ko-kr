---
title: IDiaSectionContrib | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib interface
ms.assetid: 371d40f6-ca0e-4d7e-9210-64d3768996c6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 71172c6179d918a42d47099e7179878cbec5d3ab
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasectioncontrib"></a>IDiaSectionContrib
섹션 기여도 설명 하는 데이터를 검색, 즉, 연속 된 메모리 블록을 제공한 이미지에는 컴파일 대상입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDiaSectionContrib : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDiaSectionContrib`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaSectionContrib::get_compiland](../../debugger/debug-interface-access/idiasectioncontrib-get-compiland.md)|이 섹션에 관련 된 컴파일 대상 기호에 대 한 참조를 검색 합니다.|  
|[IDiaSectionContrib::get_addressSection](../../debugger/debug-interface-access/idiasectioncontrib-get-addresssection.md)|섹션에 대 한 부분이 차지 하는 주소를 검색합니다.|  
|[IDiaSectionContrib::get_addressOffset](../../debugger/debug-interface-access/idiasectioncontrib-get-addressoffset.md)|차지 하는 주소 오프셋된 부분을 검색합니다.|  
|[IDiaSectionContrib::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasectioncontrib-get-relativevirtualaddress.md)|이미지 상대 가상 주소 (RVA) 기여도 검색합니다.|  
|[IDiaSectionContrib::get_virtualAddress](../../debugger/debug-interface-access/idiasectioncontrib-get-virtualaddress.md)|가상 주소 VA 기여도 검색합니다.|  
|[IDiaSectionContrib::get_length](../../debugger/debug-interface-access/idiasectioncontrib-get-length.md)|섹션의 바이트 수를 검색합니다.|  
|[IDiaSectionContrib::get_notPaged](../../debugger/debug-interface-access/idiasectioncontrib-get-notpaged.md)|메모리 부족 섹션 호출 될 수 없습니다 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_nopad](../../debugger/debug-interface-access/idiasectioncontrib-get-nopad.md)|다음 메모리 경계 섹션 패딩 되지 해야 하는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_code](../../debugger/debug-interface-access/idiasectioncontrib-get-code.md)|실행 코드 섹션에 포함 되는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_code16bit](../../debugger/debug-interface-access/idiasectioncontrib-get-code16bit.md)|16 비트 코드 섹션에 포함 되는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_initializedData](../../debugger/debug-interface-access/idiasectioncontrib-get-initializeddata.md)|초기화 된 데이터 섹션에 포함 되는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_uninitializedData](../../debugger/debug-interface-access/idiasectioncontrib-get-uninitializeddata.md)|섹션에는 초기화 되지 않은 데이터를 포함 하는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_informational](../../debugger/debug-interface-access/idiasectioncontrib-get-informational.md)|섹션 메모 또는 비슷한 정보에 포함 되는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_remove](../../debugger/debug-interface-access/idiasectioncontrib-get-remove.md)|메모리 내 이미지의 일부 만들어지기 전에 섹션을 제거할지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_comdat](../../debugger/debug-interface-access/idiasectioncontrib-get-comdat.md)|섹션 COMDAT 레코드 인지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_discardable](../../debugger/debug-interface-access/idiasectioncontrib-get-discardable.md)|섹션을 무시할 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_notCached](../../debugger/debug-interface-access/idiasectioncontrib-get-notcached.md)|섹션 수 없는 캐시 하는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_share](../../debugger/debug-interface-access/idiasectioncontrib-get-share.md)|메모리의 섹션을 공유할 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_execute](../../debugger/debug-interface-access/idiasectioncontrib-get-execute.md)|섹션 코드와 실행 파일 인지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_read](../../debugger/debug-interface-access/idiasectioncontrib-get-read.md)|섹션을 읽을 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_write](../../debugger/debug-interface-access/idiasectioncontrib-get-write.md)|섹션을 쓸 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get_dataCrc](../../debugger/debug-interface-access/idiasectioncontrib-get-datacrc.md)|섹션에 있는 데이터의 순환 중복 검사 (CRC)를 검색합니다.|  
|[IDiaSectionContrib::get_relocationsCrc](../../debugger/debug-interface-access/idiasectioncontrib-get-relocationscrc.md)|재배치 정보 섹션에 대 한 CRC를 검색합니다.|  
|[IDiaLineNumber::get_compilandId](../../debugger/debug-interface-access/idialinenumber-get-compilandid.md)|섹션에 대 한 컴파일 대상 식별자를 검색합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 가져온는 [idiaenumsectioncontribs:: Item](../../debugger/debug-interface-access/idiaenumsectioncontribs-item.md) 및 [idiaenumsectioncontribs:: Next](../../debugger/debug-interface-access/idiaenumsectioncontribs-next.md) 메서드. 참조는 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md) 인터페이스 가져오기에 대 한 예제는 `IDiaSectionContrib` 인터페이스입니다.  
  
## <a name="example"></a>예제  
 이 기능은 연결 된 모든 기호 함께 각 섹션의 주소를 표시합니다. 참조는 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md) 인터페이스를 방법을 `IDiaSectionContrib` 인터페이스를 가져옵니다.  
  
```C++  
void PrintSectionContrib(IDiaSectionContrib* pSecContrib, IDiaSession* pSession)  
{  
    if (pSecContrib != NULL && pSession != NULL)  
    {  
        DWORD rva;  
        if ( pSecContrib->get_relativeVirtualAddress( &rva ) == S_OK )  
        {  
            printf( "\taddr: 0x%.8X", rva );  
            pSecContrib = NULL;  
            CComPtr<IDiaSymbol> pSym;  
            if ( psession->findSymbolByRVA( rva, SymTagNull, &pSym ) == S_OK )  
            {  
                CDiaBSTR name;  
                DWORD    tag;  
                pSym->get_symTag( &tag );  
                pSym->get_name( &name );  
                printf( "     symbol: %ws (%ws)\n",  
                        name != NULL ? name : L"",  
                        szTags[ tag ] );  
            }  
            else  
            {  
                printf( "<no symbol found?>\n" );  
            }  
        }  
        else  
        {  
            DWORD isect;  
            DWORD offset;  
            pSecContrib->get_addressSection( &isect );  
            pSecContrib->get_addressOffset( &offset );  
            printf( "\taddr: 0x%.4X:0x%.8X", isect, offset );  
            pSecContrib = NULL;  
            CComPtr<IDiaSymbol> pSym;  
            if ( SUCCEEDED( psession->findSymbolByAddr(  
                                              isect,  
                                              offset,  
                                              SymTagNull,  
                                              &pSym )  
                          )  
               )  
            {  
                CDiaBSTR name;  
                DWORD    tag;  
                pSym->get_symTag( &tag );  
                pSym->get_name( &name );  
                printf( "     symbol: %ws (%ws)\n",  
                    name != NULL ? name : L"",  
                    szTags[ tag ] );  
            }  
            else  
            {  
                printf( "<no symbol found?>\n" );  
            }  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)   
 [Idiaenumsectioncontribs:: Item](../../debugger/debug-interface-access/idiaenumsectioncontribs-item.md)   
 [IDiaEnumSectionContribs::Next](../../debugger/debug-interface-access/idiaenumsectioncontribs-next.md)