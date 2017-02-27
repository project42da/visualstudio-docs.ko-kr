---
title: "IDiaDataSource::loadDataFromIStream | Microsoft Docs"
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
  - "IDiaDataSource::loadDataFromIStream 메서드"
ms.assetid: 8fe33eea-1457-4b8c-ae19-f1ede5578483
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaDataSource::loadDataFromIStream
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

인\-메모리 데이터 스트림을 통해 액세스할 프로그램 데이터베이스 \(.pdb\) 파일에 저장 된 디버그 데이터를 준비 합니다.  
  
## 구문  
  
```cpp#  
HRESULT loadDataFromIStream (   
   IStream* pIStream  
);  
```  
  
#### 매개 변수  
 pIStream  
 \[in\] <xref:IStream> 를 사용 하는 데이터 스트림을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  다음 표에서 가능한 반환 값을이 메서드에 대 한 표시 됩니다.  
  
|값|설명|  
|-------|--------|  
|E\_PDB\_FORMAT|파일은 구식 형식에 액세스 하려고 했습니다.|  
|E\_INVALIDARG|Invalidparameter입니다.|  
|E\_UNEXPECTED|데이터 원본이 이미 준비가 되었습니다.|  
  
## 설명  
 이 메서드는 메모리를 가져와야 하는 실행 파일에 대 한 디버그 데이터 있습니다는 <xref:IStream> 개체입니다.  
  
 유효성 검사 없이.pdb 파일을 로드 하려면 사용 하는 [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) 메서드.  
  
 .Pdb 파일 특정 조건에 대해 유효성 검사를 사용 하 여 [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) 메서드.  
  
 \(콜백 메커니즘을 통해\) 액세스할 수 있는 데이터 로드 프로세스를 사용 하 여 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.  
  
## 참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)