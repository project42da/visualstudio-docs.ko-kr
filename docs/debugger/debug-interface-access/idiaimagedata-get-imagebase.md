---
title: 'Idiaimagedata:: Get_imagebase | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaImageData::get_imageBase method
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9cd7cb16a4f6a6a629102eafbc212e4b2fff0f00
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaimagedatagetimagebase"></a>IDiaImageData::get_imageBase
여기서는 이미지의 기준이 되는 메모리 위치를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_imageBase (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 제안 된 이미지 기준 값을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이미지 기본 충돌로 인해 이미지 될 수 있습니다 수 기준 주소를 다시 자동으로 사용 되지 않은 메모리 위치에 로드 될 때 합니다. 이 메서드는 컴파일 타임에 모듈에 저장 된 기본 힌트 (권장된 메모리 위치)를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)