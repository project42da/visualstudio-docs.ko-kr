---
title: 쿼리는 합니다. Pdb 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- PDB files
- .pdb files, querying
ms.assetid: 8da07d1c-2712-45f9-8fbf-f34040408a8a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b2f4e6c153cb7f2729e95137c07198858dd4bfa7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="querying-the-pdb-file"></a>.Pdb 파일 쿼리
프로그램 데이터베이스 파일 (확장명.pdb)은 이진 파일 형식 및 컴파일 및 연결 된 프로젝트의 과정 동안 수집 된 기호 디버깅 정보 포함입니다. PDB 파일을 사용 하 여 C/c + + 프로그램을 컴파일할 때 만들 **/ZI** 또는 **/Zi** 또는 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], 또는 [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] 사용 하 여 프로그래밍의 **/debug** 옵션입니다. 개체 파일 디버깅 정보에 대 한.pdb 파일에 대 한 참조를 포함 합니다. Pdb 파일에 대 한 자세한 내용은 참조 하십시오. [PDB 파일](http://msdn.microsoft.com/en-us/1761c84e-8c2c-4632-9649-b5f99964ed3f)합니다. DIA 응용 프로그램을 다음과 같은 일반적인 단계를 사용 하 여 다양 한 기호, 개체 및 실행 가능 이미지의 데이터 요소에 대 한 자세한 정보를 얻을 수 있습니다.  
  
### <a name="to-query-the-pdb-file"></a>.Pdb 파일 쿼리  
  
1.  데이터 원본을 만들어 가져올는 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md) 인터페이스입니다.  
  
    ```C++  
    CComPtr<IDiaDataSource> pSource;  
    hr = CoCreateInstance( CLSID_DiaSource,  
                           NULL,  
                           CLSCTX_INPROC_SERVER,  
                           __uuidof( IDiaDataSource ),  
                          (void **) &pSource);  
  
    if (FAILED(hr))  
    {  
        Fatal("Could not CoCreate CLSID_DiaSource. Register msdia80.dll." );  
    }  
    ```  
  
2.  호출 [idiadatasource:: Loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) 또는 [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 디버깅 정보를 로드 합니다.  
  
    ```C++  
    wchar_t wszFilename[ _MAX_PATH ];  
    mbstowcs( wszFilename, szFilename, sizeof( wszFilename )/sizeof( wszFilename[0] ) );  
    if ( FAILED( pSource->loadDataFromPdb( wszFilename ) ) )  
    {  
        if ( FAILED( pSource->loadDataForExe( wszFilename, NULL, NULL ) ) )  
        {  
            Fatal( "loadDataFromPdb/Exe" );  
        }  
    }  
    ```  
  
3.  호출 [idiadatasource:: Opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md) 열려는 프로그램 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 디버깅 정보에 대 한 액세스 권한을 얻으려고 합니다.  
  
    ```C++  
    CComPtr<IDiaSession> psession;  
    if ( FAILED( pSource->openSession( &psession ) ) )   
    {  
        Fatal( "openSession" );  
    }  
    ```  
  
4.  메서드를 사용 하 여 `IDiaSession` 기호 데이터 원본에 대 한 쿼리입니다.  
  
    ```C++  
    CComPtr<IDiaSymbol> pglobal;  
    if ( FAILED( psession->get_globalScope( &pglobal) ) )  
    {  
        Fatal( "get_globalScope" );  
    }  
    ```  
  
5.  사용 하 여는 `IDiaEnum*` 디버그 정보를 열거 하 고 기호 또는 기타 요소를 검색할 인터페이스입니다.  
  
    ```C++  
    CComPtr<IDiaEnumTables> pTables;  
    if ( FAILED( psession->getEnumTables( &pTables ) ) )  
    {  
        Fatal( "getEnumTables" );  
    }  
    CComPtr< IDiaTable > pTable;  
    while ( SUCCEEDED( hr = pTables->Next( 1, &pTable, &celt ) ) && celt == 1 )  
    {  
         // Do something with each IDiaTable.  
    }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)