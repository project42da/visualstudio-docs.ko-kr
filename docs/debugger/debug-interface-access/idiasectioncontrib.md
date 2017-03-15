---
title: "IDiaSectionContrib | Microsoft Docs"
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
  - "IDiaSectionContrib 인터페이스"
ms.assetid: 371d40f6-ca0e-4d7e-9210-64d3768996c6
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# IDiaSectionContrib
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

섹션에 대 한 기여를 설명 하는 데이터를 검색, 이미지를 메모리의 연속 블록은 컴파일 대상으로, 멤버입니다.  
  
## 구문  
  
```  
IDiaSectionContrib : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaSectionContrib`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaSectionContrib::get\_compiland](../../debugger/debug-interface-access/idiasectioncontrib-get-compiland.md)|이 섹션에서는 멤버 컴파일 심볼에 대 한 참조를 검색 합니다.|  
|[IDiaSectionContrib::get\_addressSection](../../debugger/debug-interface-access/idiasectioncontrib-get-addresssection.md)|기여의 주소 구역 부분을 검색합니다.|  
|[IDiaSectionContrib::get\_addressOffset](../../debugger/debug-interface-access/idiasectioncontrib-get-addressoffset.md)|오프셋된 부분의 기여도 주소를 검색합니다.|  
|[IDiaSectionContrib::get\_relativeVirtualAddress](../../debugger/debug-interface-access/idiasectioncontrib-get-relativevirtualaddress.md)|이미지 상대 가상 주소 \(RVA\) 기여도 검색합니다.|  
|[IDiaSectionContrib::get\_virtualAddress](../../debugger/debug-interface-access/idiasectioncontrib-get-virtualaddress.md)|기여도 가상 주소 \(VA\)을 검색합니다.|  
|[IDiaSectionContrib::get\_length](../../debugger/debug-interface-access/idiasectioncontrib-get-length.md)|섹션에 대 한 바이트 수를 검색합니다.|  
|[IDiaSectionContrib::get\_notPaged](../../debugger/debug-interface-access/idiasectioncontrib-get-notpaged.md)|메모리 부족 섹션 페이징할 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_nopad](../../debugger/debug-interface-access/idiasectioncontrib-get-nopad.md)|섹션 다음 메모리 경계를 채울 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_code](../../debugger/debug-interface-access/idiasectioncontrib-get-code.md)|섹션에 실행 코드가 포함 되어 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_code16bit](../../debugger/debug-interface-access/idiasectioncontrib-get-code16bit.md)|16 비트 코드 섹션이 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_initializedData](../../debugger/debug-interface-access/idiasectioncontrib-get-initializeddata.md)|섹션에 초기화 된 데이터가 포함 되어 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_uninitializedData](../../debugger/debug-interface-access/idiasectioncontrib-get-uninitializeddata.md)|섹션에 초기화 되지 않은 데이터가 포함 되어 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_informational](../../debugger/debug-interface-access/idiasectioncontrib-get-informational.md)|섹션 설명 또는 유사한 정보가 포함 되어 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_remove](../../debugger/debug-interface-access/idiasectioncontrib-get-remove.md)|섹션에 메모리에 이미지 부분 전에 제거할지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_comdat](../../debugger/debug-interface-access/idiasectioncontrib-get-comdat.md)|섹션 COMDAT 레코드 인지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_discardable](../../debugger/debug-interface-access/idiasectioncontrib-get-discardable.md)|섹션을 삭제할 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_notCached](../../debugger/debug-interface-access/idiasectioncontrib-get-notcached.md)|섹션을 캐시할 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_share](../../debugger/debug-interface-access/idiasectioncontrib-get-share.md)|메모리에 섹션 공유 될 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_execute](../../debugger/debug-interface-access/idiasectioncontrib-get-execute.md)|섹션 코드와 실행 파일 인지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_read](../../debugger/debug-interface-access/idiasectioncontrib-get-read.md)|섹션을 읽을 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_write](../../debugger/debug-interface-access/idiasectioncontrib-get-write.md)|섹션을 쓸 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSectionContrib::get\_dataCrc](../../debugger/debug-interface-access/idiasectioncontrib-get-datacrc.md)|순환 중복 검사 \(CRC\) 섹션에서 데이터를 검색합니다.|  
|[IDiaSectionContrib::get\_relocationsCrc](../../debugger/debug-interface-access/idiasectioncontrib-get-relocationscrc.md)|CRC 재배치 섹션에 대 한 정보를 검색합니다.|  
|[IDiaLineNumber::get\_compilandId](../../debugger/debug-interface-access/idialinenumber-get-compilandid.md)|컴파일 대상 식별자 절을 검색합니다.|  
  
## 설명  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 가져온는 [IDiaEnumSectionContribs::Item](../../debugger/debug-interface-access/idiaenumsectioncontribs-item.md) 및 [IDiaEnumSectionContribs::Next](../../debugger/debug-interface-access/idiaenumsectioncontribs-next.md) 방법입니다.  참조는 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md) 인터페이스를 가져오는 예제를 `IDiaSectionContrib` 인터페이스.  
  
## 예제  
 이 함수는 연결 된 기호가 함께 각 섹션의 주소를 보여 줍니다.  참조는 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md) 인터페이스를 볼 수는 어떻게 `IDiaSectionContrib` 인터페이스에서 얻은.  
  
```cpp#  
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
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)   
 [IDiaEnumSectionContribs::Item](../../debugger/debug-interface-access/idiaenumsectioncontribs-item.md)   
 [IDiaEnumSectionContribs::Next](../../debugger/debug-interface-access/idiaenumsectioncontribs-next.md)