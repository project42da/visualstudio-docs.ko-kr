---
title: "IDiaDataSource::loadDataForExe | Microsoft Docs"
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
  - "IDiaDataSource::loadDataForExe 메서드"
ms.assetid: d94a1068-f53f-44b5-b6fb-00dec361a7f2
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaDataSource::loadDataForExe
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

열리고.exe\/.dll 파일과 관련 된 디버그 데이터를 준비 합니다.  
  
## 구문  
  
```cpp#  
HRESULT loadDataForExe (  
   LPCOLESTR executable,  
   LPCOLESTR searchPath,  
   IUnknown* pCallback  
);  
```  
  
#### 매개 변수  
 executable  
 \[in\] .Exe 또는.dll 파일의 경로입니다.  
  
 searchPath  
 \[in\] 대체 경로 사용 하 여 디버그 데이터를 검색 합니다.  
  
 pCallback  
 \[in\] `IUnknown` 같은 디버그 콜백 인터페이스를 지 원하는 개체에 대 한 인터페이스는 [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md), [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md), the [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md), 및\/또는 해당 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) 인터페이스.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  다음 표는 가능한 오류 코드에 대해이 메서드 중 일부를 보여 줍니다.  
  
|값|설명|  
|-------|--------|  
|E\_PDB\_NOT\_FOUND|파일을 열 수 없습니다 또는 파일 형식이 잘못 되었습니다.|  
|E\_PDB\_FORMAT|파일은 구식 형식에 액세스 하려고 했습니다.|  
|E\_PDB\_INVALID\_SIG|서명이 일치 하지 않습니다.|  
|E\_PDB\_INVALID\_AGE|시대와 일치 하지 않습니다.|  
|E\_INVALIDARG|잘못 된 매개 변수입니다.|  
|E\_UNEXPECTED|데이터 원본이 이미 준비가 되었습니다.|  
  
## 설명  
 연관 된 디버그 데이터 위치 디버그 헤더.exe\/.dll 파일의 이름을 지정 합니다.  
  
 이 방법을 디버그 헤더 및 다음 검색 읽고 디버그 데이터를 준비 합니다.  검색의 진행 상태를 보고 하 고 콜백을 통해 제어할 수 있습니다, 필요에 따라.  예를 들어,는 [IDiaLoadCallback::NotifyDebugDir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md) 때 호출 되는 `IDiaDataSource::loadDataForExe` 메서드를 찾아 디버그 디렉터리를 처리 합니다.  
  
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md) 및 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) 인터페이스는 표준 파일 I\/O를 통해 직접 파일을 액세스할 수 없습니다 실행 파일에서 데이터 읽기에 대 한 대체 메서드를 제공 하는 클라이언트 응용 프로그램을 사용할 수 있습니다.  
  
 유효성 검사 없이.pdb 파일을 로드 하려면 사용 하는 [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) 메서드.  
  
 .Pdb 파일 특정 조건에 대해 유효성 검사를 사용 하 여 [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) 메서드.  
  
 .Pdb 파일을 메모리에서 직접 로드를 사용 하 여 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) 메서드.  
  
## 예제  
  
```cpp#  
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
  
## 참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)   
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)   
 [IDiaLoadCallback::NotifyDebugDir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)   
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)