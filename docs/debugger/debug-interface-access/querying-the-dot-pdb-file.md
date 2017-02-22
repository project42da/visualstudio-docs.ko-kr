---
title: ".Pdb 파일 쿼리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "PDB 파일"
  - ".pdb 파일, 쿼리"
ms.assetid: 8da07d1c-2712-45f9-8fbf-f34040408a8a
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# .Pdb 파일 쿼리
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로그램 데이터베이스 파일 \(확장명.pdb\) 종류와 수집 과정의 컴파일 및 프로젝트를 연결 하는 기호화 된 디버깅 정보를 포함 하는 이진 파일이입니다.  PDB 파일에는 C\/C\+\+ 프로그램을 컴파일할 때 생성 됩니다 **\/ZI** 또는 **\/Zi** 또는 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], 또는 [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] 와 프로그램의 **\/debug** 옵션.  개체 파일에 디버깅 정보를.pdb 파일에 대 한 참조를 포함 합니다.  Pdb 파일에 대 한 자세한 내용은 [PDB Files](http://msdn.microsoft.com/ko-kr/1761c84e-8c2c-4632-9649-b5f99964ed3f).  DIA 응용 프로그램 다음과 같은 일반적인 단계를 다양 한 기호, 개체 및 실행 파일 이미지 내의 데이터 요소에 대 한 자세한 정보를 얻을 수 있습니다.  
  
### .Pdb 파일을 쿼리.  
  
1.  작성 하 여 데이터 소스를 얻기를 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md) 인터페이스입니다.  
  
    ```cpp#  
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
  
2.  호출 [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) 또는 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 디버깅 정보를 로드할 수 있습니다.  
  
    ```cpp#  
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
  
3.  호출 [IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md) 열 수는 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 디버깅 정보에 액세스할 수 있습니다.  
  
    ```cpp#  
    CComPtr<IDiaSession> psession;  
    if ( FAILED( pSource->openSession( &psession ) ) )   
    {  
        Fatal( "openSession" );  
    }  
    ```  
  
4.  메서드를 사용 하 여 `IDiaSession` 기호를 데이터 원본에 대해 쿼리 합니다.  
  
    ```cpp#  
    CComPtr<IDiaSymbol> pglobal;  
    if ( FAILED( psession->get_globalScope( &pglobal) ) )  
    {  
        Fatal( "get_globalScope" );  
    }  
    ```  
  
5.  사용은 `IDiaEnum*` 열거 하 고 검사할 기호 또는 기타 요소에 인터페이스 정보를 디버그 합니다.  
  
    ```cpp#  
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
  
## 참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)