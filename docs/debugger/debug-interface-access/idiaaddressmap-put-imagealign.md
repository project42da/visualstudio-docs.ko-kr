---
title: 'Idiaaddressmap:: Put_imagealign | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_imageAlign method
ms.assetid: f9ce875d-c263-43e5-a534-f34c37f9866f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c40e2f325ac30eb109f72615e5cc74a5d30e5eba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idiaaddressmapputimagealign"></a>IDiaAddressMap::put_imageAlign
이미지 맞춤을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT put_imageAlign (   
   DWORD NewVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 NewVal  
 [in] 새 이미지 맞춤 실행 파일에 대 한 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이미지 (로드 된 실행 파일) 지정 된 메모리 한도에 따라 정렬 됩니다. 현재 시스템 아키텍처 및 시간 옵션을 컴파일 및 연결 하 여이 맞춤을 달라질 수 있습니다. 이미지 맞춤은 항상 바이트 경계에서입니다. 다음 이미지 맞춤 값이 유효한 지: 1, 2, 4, 8, 16, 32, and 64 바이트 경계입니다.  
  
 현재 이미지 맞춤을 호출 하 여 검색할 수는 [idiaaddressmap:: Get_imagealign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md) 메서드.  
  
> [!NOTE]
>  이 메서드를 호출할 수 있습니다 때 이미지가 이미 로드 되었습니다. `put_imageAlign` 새 맞춤은 필수 및 이미지를 이동 하거나 변경 하는 경우 메서드는 일반적으로 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)