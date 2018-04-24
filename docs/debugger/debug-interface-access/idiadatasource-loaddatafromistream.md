---
title: 'Idiadatasource:: Loaddatafromistream | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadDataFromIStream method
ms.assetid: 8fe33eea-1457-4b8c-ae19-f1ede5578483
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2421e25c51d005a069de316d1d465eca80a0432b
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiadatasourceloaddatafromistream"></a>IDiaDataSource::loadDataFromIStream
메모리 내 데이터 스트림을 통해 액세스 하는 프로그램 데이터베이스 (.pdb) 파일에 저장 된 디버그 데이터를 준비 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT loadDataFromIStream (   
   IStream* pIStream  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pIStream  
 [in] <xref:IStream> 사용 하도록 데이터 스트림을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 다음 표에서이 메서드에 대 한 가능한 반환 값을 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|E_PDB_FORMAT|사용 되지 않는 형식으로 파일에 액세스 하려고 했습니다.|  
|E_INVALIDARG|Invalidparameter입니다.|  
|E_UNEXPECTED|데이터 소스를 이미 준비 합니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드를 통해 메모리에서 가져올 실행 파일에 대 한 디버그 데이터를 사용 하면 프로그램 <xref:IStream> 개체입니다.  
  
 유효성 검사 없이.pdb 파일을 로드 하려면 사용 하 여는 [idiadatasource:: Loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) 메서드.  
  
 특정 조건에 대 한.pdb 파일의 유효성 검사를 사용 하 여는 [idiadatasource:: Loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) 메서드.  
  
 (콜백 메커니즘)을 통해 데이터 로드 프로세스에 대 한 액세스 권한을 사용 하 여는 [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiadatasource:: Loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)