---
title: DiaAddressMapEntry | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DiaAddressMapEntry enumeration
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc13e8813c0e1bddd1f6cb9abd3d70b26eb5a8e1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="diaaddressmapentry"></a>DiaAddressMapEntry
주소 맵에서 항목을 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
struct DiaAddressMapEntry {   
   DWORD rva,  
   DWORD rvaTo  
};  
```  
  
## <a name="elements"></a>요소  
 `rva`  
 1. 이미지의 상대 가상 주소 (RVA)  
  
 `rvaTo`  
 상대 가상 주소 `rva` 2. 이미지에 매핑될  
  
## <a name="remarks"></a>설명  
 주소 구조는 하나의 이미지 레이아웃에서 변환 (A)에 다른 (B)를 제공합니다. 배열을 `DiaAddressMapEntry` 구조를 기준으로 정렬 `rva` 주소 맵을 정의 합니다.  
  
 주소를 변환 `addrA`, 주소로 A 이미지에 `addrB`, 이미지 B에서에서 다음 단계를 수행 합니다.  
  
1.  검색에 대 한 항목에 대 한 맵을 `e`, 가장 큰와 `rva` 보다 작거나 `addrA`합니다.  
  
2.  Set `delta = addrA - e.rva`.  
  
3.  Set `addrB = e.rvaTo + delta`.  
  
 배열을 `DiaAddressMapEntry` 구조에 전달 되는 [idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: dia2.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)