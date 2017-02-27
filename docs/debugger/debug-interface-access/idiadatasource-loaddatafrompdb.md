---
title: "IDiaDataSource::loadDataFromPdb | Microsoft Docs"
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
  - "IDiaDataSource::loadDataFromPdb 메서드"
ms.assetid: 02159073-8144-47f8-a0b0-aa0edcb92b5b
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaDataSource::loadDataFromPdb
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

열 하 고 프로그램 데이터베이스 \(.pdb\) 파일에 디버그 데이터 원본으로 준비 합니다.  
  
## 구문  
  
```cpp#  
HRESULT loadDataFromPdb (  
   LPCOLESTR pdbPath  
);  
```  
  
#### 매개 변수  
 pdbPath  
 \[in\] .Pdb 파일의 경로입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  다음 표에서 가능한 반환 값을이 메서드에 대 한 표시 됩니다.  
  
|값|설명|  
|-------|--------|  
|E\_PDB\_NOT\_FOUND|파일을 열 수 없습니다 또는 파일에 잘못 된 형식이 있는지 확인 했습니다.|  
|E\_PDB\_FORMAT|파일은 구식 형식에 액세스 하려고 했습니다.|  
|E\_INVALIDARG|잘못 된 매개 변수입니다.|  
|E\_UNEXPECTED|데이터 원본이 이미 준비가 되었습니다.|  
  
## 설명  
 이 메서드는 디버그 데이터.pdb 파일을 직접 로드합니다.  
  
 .Pdb 파일 특정 조건에 대해 유효성 검사를 사용 하 여 [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) 메서드.  
  
 \(콜백 메커니즘을 통해\) 액세스할 수 있는 데이터 로드 프로세스를 사용 하 여 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.  
  
 .Pdb 파일을 메모리에서 직접 로드를 사용 하 여 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) 메서드.  
  
## 예제  
  
```cpp#  
HRESULT hr = pSource->loadDataFromPdb( L"myprog.pdb" );  
if (FAILED(hr))  
{  
    // report error  
}  
```  
  
## 참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)