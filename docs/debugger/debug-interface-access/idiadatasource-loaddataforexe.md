---
title: 'Idiadatasource:: Loaddataforexe | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaDataSource::loadDataForExe method
ms.assetid: d94a1068-f53f-44b5-b6fb-00dec361a7f2
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 30890b66baf10f5000a9244e85a36000ea26c181
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiadatasourceloaddataforexe"></a>IDiaDataSource::loadDataForExe
열리고.exe/.dll 파일과 관련 된 디버그 데이터를 준비 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT loadDataForExe (  
   LPCOLESTR executable,  
   LPCOLESTR searchPath,  
   IUnknown* pCallback  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 executable  
 [in] .Exe 또는.dll 파일 경로입니다.  
  
 searchPath  
 [in] 디버그 데이터를 검색 하려면 대체 경로입니다.  
  
 pCallback  
 [in] `IUnknown` 와 같은 디버그 콜백 인터페이스를 지 원하는 하는 개체에 대 한 인터페이스는 [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md), [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md), [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md), 및/또는 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 다음 표에서이 메서드에 대 한 가능한 오류 코드 중 일부를 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|E_PDB_NOT_FOUND|파일을 열지 못했습니다 또는 파일 형식이 잘못 되었습니다.|  
|E_PDB_FORMAT|사용 되지 않는 형식으로 파일에 액세스 하려고 했습니다.|  
|E_PDB_INVALID_SIG|서명이 일치 하지 않습니다.|  
|E_PDB_INVALID_AGE|나이 일치 하지 않습니다.|  
|E_INVALIDARG|잘못된 매개 변수입니다.|  
|E_UNEXPECTED|데이터 소스를 이미 준비 합니다.|  
  
## <a name="remarks"></a>설명  
 관련된 디버그 데이터 위치.exe/.dll 파일의 디버그 헤더 이름을 지정 합니다.  
  
 이 메서드를 검색 합니다 및 디버그 데이터를 준비 디버그 헤더를 읽습니다. 필요에 따라 검색의 진행률을 보고 및 콜백을 통해 제어할 수 있습니다. 예를 들어는 [idialoadcallback:: Notifydebugdir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md) 때 호출 되는 `IDiaDataSource::loadDataForExe` 메서드를 찾아서 디버그 디렉터리를 처리 합니다.  
  
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md) 및 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) 인터페이스를 통해 클라이언트 응용 프로그램 실행 파일에서 데이터를 읽기 위한 대체 메서드를 제공할 때 파일 파일 표준 파일 I/O 통해 직접 액세스할 수 없습니다.  
  
 유효성 검사 없이.pdb 파일을 로드 하려면 사용 하 여는 [idiadatasource:: Loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) 메서드.  
  
 특정 조건에 대 한.pdb 파일의 유효성 검사를 사용 하 여는 [idiadatasource:: Loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) 메서드.  
  
 사용 하 여 메모리에서 직접.pdb 파일을 로드 하려면는 [idiadatasource:: Loaddatafromistream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) 메서드.  
  
## <a name="example"></a>예제  
  
```C++  
class MyCallBack: public IDiaLoadCallback  
{  
...  
};  
MyCallBack callback;  
...  
HRESULT hr = pSource->loadDataForExe( L"myprog.exe", L".\debug", (IUnknown*)&callback);  
if (FAILED(hr))  
{  
    // Report error  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)   
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)   
 [Idialoadcallback:: Notifydebugdir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)   
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [Idiadatasource:: Loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [Idiadatasource:: Loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)