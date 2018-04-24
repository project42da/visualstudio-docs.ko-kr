---
title: 'Idiaaddressmap:: Set_addressmap | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_addressMap method
ms.assetid: 81e82073-089b-43d5-af39-49d7a4907c7a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a1c934dc998818973b5de4106c3df952ad24f22f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaaddressmapsetaddressmap"></a>IDiaAddressMap::set_addressMap
이미지 레이아웃 번역을 지원 하기 위해 주소 맵을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT set_addressMap (   
   DWORD                     cbData,  
   struct DiaAddressMapEntry data[],  
   BOOL                      imagetoSymbols  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cbData`  
 [in] 에 있는 요소의 수는 `data` 매개 변수입니다.  
  
 `data[]`  
 [in] 배열을 [DiaAddressMapEntry 구조체](../../debugger/debug-interface-access/diaaddressmapentry.md) 변환 맵을 정의 하는 구조입니다.  
  
 `imagetoSymbols`  
 [in] `TRUE` 경우는 `data` 매개 변수 정의 원래 레이아웃으로 새 이미지 레이아웃의 지도 (디버그 기호에 의해 설명 참조). `FALSE` 경우 `data` 한 맵이 원래 레이아웃에서 가져온 새 이미지 레이아웃입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 일반적으로 DIA 프로그램 데이터베이스 (.pdb) 파일에서 주소 변환 지도 검색합니다. 이러한 값을 사용할 수 없는 경우는 [idiaaddressmap:: Set_imageheaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) 메서드는 두 번으로 `imagetoSymbols` 매개 변수 설정 `TRUE` 및 한 번의 `imagetoSymbols` 매개 변수 설정 `FALSE`합니다. 사용 하 여 주소 맵 번역을 사용할 수 없습니다는 [idiaaddressmap:: Put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md) 메서드 모두 번역 지도 제공 하지 않는 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DiaAddressMapEntry 구조체](../../debugger/debug-interface-access/diaaddressmapentry.md)   
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap:: Put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)   
 [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)