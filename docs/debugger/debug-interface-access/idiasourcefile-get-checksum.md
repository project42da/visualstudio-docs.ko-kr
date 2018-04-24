---
title: 'Idiasourcefile:: Get_checksum | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_checksum method
ms.assetid: aad63a7e-4e22-44e4-8a5b-81b5174ced1e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 002ad16d94467c135e08ef0040fd7ffd51462719
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasourcefilegetchecksum"></a>IDiaSourceFile::get_checksum
체크섬 바이트 수를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_checksum (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cbData`  
 [in] 데이터 버퍼의 바이트의 크기입니다.  
  
 `pcbData`  
 [out] 체크섬 바이트 수를 반환합니다. 이 매개 변수 여야 `NULL`합니다.  
  
 `data`  
 [out에서] 체크섬 바이트도 채워진 버퍼입니다. 이 매개 변수가 `NULL`, 다음 `pcbData` 필요한 바이트 수를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 를 체크섬 바이트를 생성 하는 데 사용 된 체크섬 알고리즘의 형식을 확인 하려면 호출는 [idiasourcefile:: Get_checksumtype](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md) 메서드.  
  
 체크섬 변경 소스 파일 체크섬 바이트에서 변경 사항을 반영 하므로 일반적으로 소스 파일의 이미지에서 만들어집니다. 체크섬 바이트 일치 하지 않으면 파일 것으로 간주 해야 파일의 로드 된 이미지에서 생성 된 체크섬 손상 되었거나 임의로 변경 합니다.  
  
 일반적인 체크섬 크기가 32 바이트 이상 아니지만 체크섬의 최대 크기를 가정 하지 않습니다. 설정의 `data` 매개 변수를 `NULL` 체크섬을 검색 하는 데 필요한 바이트 수를 얻을 수 있습니다. 그런 다음 적절 한 크기의 버퍼를 할당 하 고 새 버퍼와 한 번 더이 메서드를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get_checksumType](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)