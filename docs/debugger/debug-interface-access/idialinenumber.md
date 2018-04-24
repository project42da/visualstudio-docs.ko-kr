---
title: IDiaLineNumber | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber interface
ms.assetid: 1071f7d0-1f8c-4384-933f-c49c7eb930bd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 735b15f76d9cb679e6fda2327e4af0dc3d84c8a0
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idialinenumber"></a>IDiaLineNumber
원본 파일 줄 번호를 이미지 텍스트의 바이트 블록에서 매핑 프로세스를 설명 하는 정보를 액세스 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDiaLineNumber : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDiaLineNumber`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaLineNumber::get_compiland](../../debugger/debug-interface-access/idialinenumber-get-compiland.md)|이미지 텍스트의 바이트를 관련 된 컴파일 대상에 대 한 기호에 대 한 참조를 검색 합니다.|  
|[IDiaLineNumber::get_sourceFile](../../debugger/debug-interface-access/idialinenumber-get-sourcefile.md)|소스 파일 개체에 대 한 참조를 검색합니다.|  
|[IDiaLineNumber::get_lineNumber](../../debugger/debug-interface-access/idialinenumber-get-linenumber.md)|소스 파일의 줄 번호를 검색합니다.|  
|[IDiaLineNumber::get_lineNumberEnd](../../debugger/debug-interface-access/idialinenumber-get-linenumberend.md)|문이나 식이 끝나는 1부터 소스 줄 번호를 검색 합니다.|  
|[IDiaLineNumber::get_columnNumber](../../debugger/debug-interface-access/idialinenumber-get-columnnumber.md)|식 또는 문 시작 되는 열 번호를 검색 합니다.|  
|[IDiaLineNumber::get_columnNumberEnd](../../debugger/debug-interface-access/idialinenumber-get-columnnumberend.md)|식 또는 문에서 끝나는 열 번호를 검색 합니다.|  
|[IDiaLineNumber::get_addressSection](../../debugger/debug-interface-access/idialinenumber-get-addresssection.md)|블록의 시작 위치 메모리 주소의 섹션 부분을 검색 합니다.|  
|[IDiaLineNumber::get_addressOffset](../../debugger/debug-interface-access/idialinenumber-get-addressoffset.md)|메모리 주소 블록의 시작 위치 오프셋된 부분을 검색 합니다.|  
|[IDiaLineNumber::get_relativeVirtualAddress](../../debugger/debug-interface-access/idialinenumber-get-relativevirtualaddress.md)|이미지 상대 가상 주소 (RVA) 블록을 검색합니다.|  
|[IDiaLineNumber::get_virtualAddress](../../debugger/debug-interface-access/idialinenumber-get-virtualaddress.md)|블록의 가상 주소 (VA)를 검색합니다.|  
|[IDiaLineNumber::get_length](../../debugger/debug-interface-access/idialinenumber-get-length.md)|블록의 바이트 수를 검색합니다.|  
|[IDiaLineNumber::get_sourceFileId](../../debugger/debug-interface-access/idialinenumber-get-sourcefileid.md)|이 줄을 제공 하는 원본 파일에 대 한 고유한 소스 파일 식별자를 검색 합니다.|  
|[IDiaLineNumber::get_statement](../../debugger/debug-interface-access/idialinenumber-get-statement.md)|프로그램 소스에서 문의 시작이 줄 정보를 설명 한다는 사실을 나타내는 플래그를 검색 합니다.|  
|[IDiaLineNumber::get_compilandId](../../debugger/debug-interface-access/idialinenumber-get-compilandid.md)|이 줄을 영향을 주는 컴파일 대상에 대 한 고유 식별자를 검색 합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 가져올는 [idiaenumlinenumbers:: Item](../../debugger/debug-interface-access/idiaenumlinenumbers-item.md) 또는 [idiaenumlinenumbers:: Next](../../debugger/debug-interface-access/idiaenumlinenumbers-next.md) 메서드.  
  
## <a name="example"></a>예제  
 다음 함수는 함수에 사용 되는 줄 번호 표시 됩니다 (나타내는 `pSymbol`).  
  
```C++  
void dumpFunctionLines( IDiaSymbol* pSymbol, IDiaSession* pSession )  
{  
    ULONGLONG length = 0;  
    DWORD     isect  = 0;  
    DWORD     offset = 0;  
  
    pSymbol->get_addressSection( &isect );  
    pSymbol->get_addressOffset( &offset );  
    pSymbol->get_length( &length );  
    if ( isect != 0 && length > 0 )  
    {  
        CComPtr< IDiaEnumLineNumbers > pLines;  
        if ( SUCCEEDED( pSession->findLinesByAddr(  
                                      isect,  
                                      offset,  
                                      static_cast<DWORD>( length ),  
                                      &pLines)  
                      )  
           )  
        {  
            CComPtr< IDiaLineNumber > pLine;  
            DWORD celt      = 0;  
            bool  firstLine = true;  
  
            while ( SUCCEEDED( pLines->Next( 1, &pLine, &celt ) ) &&  
                    celt == 1 )  
            {  
                DWORD offset;  
                DWORD seg;  
                DWORD linenum;  
                CComPtr< IDiaSymbol >     pComp;  
                CComPtr< IDiaSourceFile > pSrc;  
  
                pLine->get_compiland( &pComp );  
                pLine->get_sourceFile( &pSrc );  
                pLine->get_addressSection( &seg );  
                pLine->get_addressOffset( &offset );  
                pLine->get_lineNumber( &linenum );  
                printf( "\tline %d at 0x%x:0x%x\n", linenum, seg, offset );  
                pLine = NULL;  
                if ( firstLine )  
                {  
                    // sanity check  
                    CComPtr< IDiaEnumLineNumbers > pLinesByLineNum;  
                    if ( SUCCEEDED( pSession->findLinesByLinenum(  
                                                  pComp,  
                                                  pSrc,  
                                                  linenum,  
                                                  0,  
                                                  &pLinesByLineNum)  
                                  )  
                       )  
                    {  
                        CComPtr< IDiaLineNumber > pLine;  
                        DWORD celt;  
                        while ( SUCCEEDED( pLinesByLineNum->Next( 1, &pLine, &celt ) ) &&  
                                celt == 1 )  
                        {  
                            DWORD offset;  
                            DWORD seg;  
                            DWORD linenum;  
  
                            pLine->get_addressSection( &seg );  
                            pLine->get_addressOffset( &offset );  
                            pLine->get_lineNumber( &linenum );  
                            printf( "\t\tfound line %d at 0x%x:0x%x\n", linenum, seg, offset );  
                            pLine = NULL;  
                       }  
                    }  
                    firstLine = false;  
                }  
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
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [Idiaenumlinenumbers:: Item](../../debugger/debug-interface-access/idiaenumlinenumbers-item.md)   
 [IDiaEnumLineNumbers::Next](../../debugger/debug-interface-access/idiaenumlinenumbers-next.md)