---
title: 'Idiaaddressmap:: Put_relativevirtualaddressenabled | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_relativeVirtualAddressEnabled method
ms.assetid: 767c078e-8ad7-4940-9e00-cae7704aadee
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dbbe2c2299a26834ac40c787aea5504ae7d0ed8a
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaaddressmapputrelativevirtualaddressenabled"></a>IDiaAddressMap::put_relativeVirtualAddressEnabled
계산 및 상대 가상 주소 (RVA)의 사용을 사용 하지 않도록 설정 하거나 설정 하려면 클라이언트가 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT put_relativeVirtualAddressEnabled (   
   BOOL NewVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 NewVal  
 [in] 로 설정 `TRUE` 를 활성화 하려면 또는 `FALSE` 를 사용 하지 않도록 설정 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 상대 가상 주소도 DIA 인터페이스 및 기본, 실행 파일의 이미지를 기준으로 설명 하는 디버그 개체에 대 한 주소를 검색할 수 있습니다.  
  
 Rva 사용 하는 처음에 세그먼트는 PDB 파일에서 로드 하는 경우에 활성화 됩니다. Rva 사용의 현재 상태를 가져오려면 호출는 [idiaaddressmap:: Get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) 메서드.  
  
 `put_relativeVirtualAddress` 메서드 호출 Rva를 성공적으로 호출 된 후 설정 하는 [idiaaddressmap:: Set_imageheaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) 메서드는 새 이미지 헤더를 설정 했습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap:: Get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)   
 [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)