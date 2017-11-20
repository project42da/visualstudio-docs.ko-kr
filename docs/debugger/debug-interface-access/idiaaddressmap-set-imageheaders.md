---
title: 'Idiaaddressmap:: Set_imageheaders | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaAddressMap::set_imageHeaders method
ms.assetid: a46b9d0e-43e6-433f-b2c7-aa203981e4e4
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4ee1fc286b162ff7a0649c5cc651884b927b5857
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaaddressmapsetimageheaders"></a>IDiaAddressMap::set_imageHeaders
설정 이미지 헤더 상대 가상 주소 변환을 사용 하도록 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT set_imageHeaders (   
   DWORD cbData,  
   BYTE  data[],  
   BOOL  originalHeaders  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 cbData  
 [in] 헤더 데이터의 바이트 수입니다. 해야 `n*sizeof(IMAGE_SECTION_HEADER)` 여기서 `n` 섹션 헤더에는 실행 파일 수입니다.  
  
 데이터]  
 [in] 배열 `IMAGE_SECTION_HEADER` 이미지 머리글로 사용할 구조입니다.  
  
 originalHeaders  
 [in] 로 설정 `FALSE` 새 이미지에서 이미지 머리글이 되 면 `TRUE` 업그레이드 하기 전에 원본 이미지를 반영 합니다. 일반적으로 이것은로 설정 됩니다 `TRUE` 조합에 대 한 호출 에서만 [idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) 메서드.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 `IMAGE_SECTION_HEADER` 구조 Winnt.h에 선언 되었고 실행 파일의 이미지 섹션 헤더 형식을 나타냅니다.  
  
 상대 가상 주소 계산에 종속 된 `IMAGE_SECTION_HEADER` 값입니다. 일반적으로 DIA 프로그램 데이터베이스 (.pdb) 파일에서 검색 합니다. 이러한 값이 누락 되는 DIA 수 없는 경우 상대 가상 주소를 계산 하 고 [idiaaddressmap:: Get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) 메서드가 반환 `FALSE`합니다. 클라이언트를 호출 해야 합니다는 [idiaaddressmap:: Put_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md) 메서드 상대 가상 주소 계산의 누락 된 이미지 헤더 이미지 자체를 입력 한 후 사용할 수 있도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [Idiaaddressmap:: Get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)   
 [IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)