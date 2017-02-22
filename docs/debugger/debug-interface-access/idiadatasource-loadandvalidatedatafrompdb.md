---
title: "IDiaDataSource::loadAndValidateDataFromPdb | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "IDiaDataSource::loadAndValidateDataFromPdb 메서드"
ms.assetid: d66712dd-6c24-4192-919a-cce262066f0e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaDataSource::loadAndValidateDataFromPdb
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

열립니다 및 프로그램 데이터베이스 \(.pdb\) 파일에 제공 된 서명 정보가 일치 하는지 확인 하 고.pdb 파일에 디버그 데이터 원본으로 준비.  
  
## 구문  
  
```cpp#  
HRESULT loadAndValidateDataFromPdb (   
   LPCOLESTR pdbPath,  
   GUID*     pcsig70,  
   DWORD     sig,  
   DWORD     age  
);  
```  
  
#### 매개 변수  
 `pdbPath`  
 \[in\] .Pdb 파일의 경로입니다.  
  
 `pcsig70`  
 \[in\] 하 여.pdb 파일 서명을 확인 하는 GUID 서명입니다.  만.pdb 파일에 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 나중에 서명을 GUID를 사용 하 고 있습니다.  
  
 `sig`  
 \[in\] 하 여.pdb 파일 서명을 확인 하는 32 비트 서명입니다.  
  
 `age`  
 \[in\] 사용 기간 값을 확인 합니다.  나이 알려진된 시간 값을 반드시 일치 하지 않습니다,.pdb 파일 동기화는 해당.exe 파일을 확인 하는 데 사용 됩니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  다음 표에서 가능한 반환 값을이 메서드에 대 한 표시 됩니다.  
  
|값|설명|  
|-------|--------|  
|E\_PDB\_NOT\_FOUND|파일을 열 수 없습니다 또는 파일 형식이 잘못 되었습니다.|  
|E\_PDB\_FORMAT|파일은 구식 형식에 액세스 하려고 했습니다.|  
|E\_PDB\_INVALID\_SIG|서명이 일치 하지 않습니다.|  
|E\_PDB\_INVALID\_AGE|시대와 일치 하지 않습니다.|  
|E\_INVALIDARG|잘못 된 매개 변수입니다.|  
|E\_UNEXPECTED|데이터 원본이 이미 준비가 되었습니다.|  
  
## 설명  
 .Pdb 파일 서명과 보존 기간 값을 포함 합니다.  이러한 값은.pdb 파일과 일치 하는.exe 또는.dll 파일에 복제 됩니다.  이 메서드는 데이터 소스를 준비 하기 전에 이름이 지정 된.pdb 파일의 서명 및 나이 제공 되는 값과 일치 하는지 확인 합니다.  
  
 유효성 검사 없이.pdb 파일을 로드 하려면 사용 하는 [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) 메서드.  
  
 \(콜백 메커니즘을 통해\) 액세스할 수 있는 데이터 로드 프로세스를 사용 하 여 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.  
  
 .Pdb 파일을 메모리에서 직접 로드를 사용 하 여 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) 메서드.  
  
## 예제  
  
```cpp#  
IDiaDataSource* pSource;  // Previously created data source.  
DEFINE_GUID(expectedGUIDSignature,0x1234,0x5678,0x01,0x02,0x03,0x04,0x05,0x06,0x07,0x08);  
DWORD expectedFileSignature = 0x12345678;  
DWORD expectedAge           = 128;  
  
HRESULT hr;  
hr = pSource->loadAndValidateDataFromPdb( L"yprog.pdb",  
                                          &expectedGUIDSignature,  
                                          expectedFileSignature,  
                                          expectedAge);  
if (FAILED(hr))  
{  
    // Report an error  
}  
  
```  
  
## 참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)