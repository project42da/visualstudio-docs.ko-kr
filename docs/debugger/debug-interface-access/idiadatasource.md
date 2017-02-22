---
title: "IDiaDataSource | Microsoft Docs"
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
  - "IDiaDataSource 인터페이스"
ms.assetid: 6260ac76-4f9d-4144-ba22-32f8620b32c2
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaDataSource
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

시작 액세스의 디버깅 기호가 소스입니다.  
  
## 구문  
  
```  
IDiaDataSource : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaDataSource`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaDataSource::get\_lastError](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md)|마지막 로드 오류에 대 한 파일 이름을 검색합니다.|  
|[IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)|열 하 고 프로그램 데이터베이스 \(.pdb\) 파일에 디버그 데이터 원본으로 준비 합니다.|  
|[IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)|열리고 프로그램 데이터베이스 \(.pdb\) 파일에서 제공 된 서명 정보를 일치 하는지 확인 합니다. .pdb 파일을 디버그 데이터 원본으로 준비합니다.|  
|[IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)|열리고.exe\/.dll 파일과 관련 된 디버그 데이터를 준비 합니다.|  
|[IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)|인\-메모리 데이터 스트림을 통해 액세스할 프로그램 데이터베이스 \(.pdb\) 파일에 저장 된 디버그 데이터를 준비 합니다.|  
|[IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)|기호를 쿼리 하는 것에 대 한 세션을 엽니다.|  
  
## 설명  
 로드 메서드 중 하나를 호출 하 여 `IDiaDataSource` 인터페이스 기호가 소스를 엽니다.  성공적으로 호출 하는 [IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md) 메서드가 반환은 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 쿼리 데이터 원본에서 지 원하는 인터페이스.  Load 메서드가 파일 관련 오류를 반환 하는 경우 다음을 [IDiaDataSource::get\_lastError](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md) 메서드의 반환 값이 오류와 관련 된 파일 이름입니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 가져온는 `CoCreateInstance` 함수는 클래스 식별자를 `CLSID_DiaSource` 와의 인터페이스 ID `IID_IDiaDataSource`.  이 인터페이스를 받는 방법을 보여 줍니다.  
  
## 예제  
  
```cpp#  
  
      IDiaDataSource* pSource;  
HRESULT hr = CoCreateInstance(CLSID_DiaSource,  
                              NULL,  
                              CLSCTX_INPROC_SERVER,  
                              IID_IDiaDataSource,  
                              (void**) &pSource);  
if (FAILED(hr))  
{  
    // Report error and exit  
}  
```  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)