---
title: 'Idiadatasource:: Loadandvalidatedatafrompdb | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadAndValidateDataFromPdb method
ms.assetid: d66712dd-6c24-4192-919a-cce262066f0e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2613ee54f9db7216480093fcf4ed65a7927b775c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idiadatasourceloadandvalidatedatafrompdb"></a>IDiaDataSource::loadAndValidateDataFromPdb
엽니다 및 프로그램 데이터베이스 (.pdb) 파일에 제공 된 서명 정보과 일치 하는지 확인 하 고 디버그 데이터 소스로.pdb 파일을 준비 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT loadAndValidateDataFromPdb (   
   LPCOLESTR pdbPath,  
   GUID*     pcsig70,  
   DWORD     sig,  
   DWORD     age  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdbPath`  
 [in] .Pdb 파일에 대 한 경로입니다.  
  
 `pcsig70`  
 [in] .pdb 파일 서명에 대 한 확인 하려면 GUID 서명입니다. 만.pdb 파일에 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 그리고 GUID 서명입니다.  
  
 `sig`  
 [in] 32 비트 서명은.pdb 파일 서명에 대 한 확인입니다.  
  
 `age`  
 [in] 확인 하려면 보존 기간 값입니다. 알려진된 시간 값이 있으면 나이 반드시 일치 하지 않습니다, 그리고 해당.exe 파일이 동기화 되지.pdb 파일 인지 확인 하려면 사용 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 다음 표에서이 메서드에 대 한 가능한 반환 값을 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|E_PDB_NOT_FOUND|파일을 열지 못했습니다 또는 파일 형식이 잘못 되었습니다.|  
|E_PDB_FORMAT|사용 되지 않는 형식으로 파일에 액세스 하려고 했습니다.|  
|E_PDB_INVALID_SIG|서명이 일치 하지 않습니다.|  
|E_PDB_INVALID_AGE|나이 일치 하지 않습니다.|  
|E_INVALIDARG|잘못된 매개 변수입니다.|  
|E_UNEXPECTED|데이터 원본이 이미 준비 합니다.|  
  
## <a name="remarks"></a>설명  
 .Pdb 파일 모두 서명 및 보존 기간 값을 포함합니다. 이러한 값은.pdb 파일을 일치 하는.exe 또는.dll 파일에 복제 됩니다. 데이터 소스를 준비 하기 전에이 메서드는 명명 된.pdb 파일의 서명 및 나이 제공 된 값과 일치 하는지 확인 합니다.  
  
 유효성 검사 없이.pdb 파일을 로드 하려면 사용 하 여는 [idiadatasource:: Loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) 메서드.  
  
 (콜백 메커니즘)을 통해 데이터 로드 프로세스에 대 한 액세스 권한을 사용 하 여는 [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.  
  
 사용 하 여 메모리에서 직접.pdb 파일을 로드 하려면는 [idiadatasource:: Loaddatafromistream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) 메서드.  
  
## <a name="example"></a>예제  
  
```C++  
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
  
## <a name="see-also"></a>참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiadatasource:: Loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)