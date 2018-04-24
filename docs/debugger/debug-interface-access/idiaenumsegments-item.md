---
title: 'Idiaenumsegments:: Item | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Item method
ms.assetid: ee44dd55-39a0-4b7b-97ff-2e1226eeb2bd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 64089113f0ad5b0e3fea0189a5dc3bf680213158
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumsegmentsitem"></a>IDiaEnumSegments::Item
인덱스를 사용 하 여 세그먼트를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Item (   
   DWORD         index,  
   IDiaSegment** segment  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 인덱스입니다.  
 [in] 인덱스는 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) 검색할 개체입니다. 인덱스는 0에서 범위에 `count`-1로, 여기서 `count` 에서 반환 되는 [idiaenumsegments:: Get_count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md) 메서드.  
  
 세그먼트  
 [out] 반환 된 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) 원하는 세그먼트를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)