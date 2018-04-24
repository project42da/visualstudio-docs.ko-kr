---
title: 'Idiaaddressmap:: Put_addressmapenabled | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_addressMapEnabled method
ms.assetid: 0f205337-4e59-4383-8059-7b1d207d6dcd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cb640a46825d720c5305a408fa716c6e3bed66c4
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaaddressmapputaddressmapenabled"></a>IDiaAddressMap::put_addressMapEnabled
기호 주소 변환에 매핑된 주소를 사용할지 여부를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT put_addressMapEnabled (   
   BOOL NewVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 NewVal  
 [in] 로 설정 `TRUE` 기호, 변환을 사용 하도록 설정 또는 `FALSE` 를 사용 하지 않도록 설정 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 경우에 따라 실행 이후 프로세서 실행 파일을 업데이트합니다. DIA 기호 새 레이아웃의 번역을 지원 하기 위한 메커니즘을 포함 합니다.  
  
 PDB 파일이 로드 되는 파일에 저장 된 매핑된 주소 활성화 됩니다. 그러나 클라이언트 응용 프로그램을 호출 하 여 매핑된 자체 주소를 제공 해야 할 수도 때 시기가 [idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) 메서드. 경우는 `set_addressMap` 메서드를 성공적으로, 클라이언트 응용 프로그램 호출 해야 합니다는 `put_addressMapEnabled` 메서드는 `NewVal` 의 매개 변수 `TRUE` 매핑된 해당 주소를 사용할 수 있도록 합니다.  
  
 호출 하 여 매핑된 주소를 사용 하도록 설정의 현재 상태를 검색할 수는 [idiaaddressmap:: Get_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)