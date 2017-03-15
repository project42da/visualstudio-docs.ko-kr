---
title: "DiaAddressMapEntry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DiaAddressMapEntry 열거형"
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# DiaAddressMapEntry
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

주소 맵 항목에 설명 합니다.  
  
## 구문  
  
```cpp#  
struct DiaAddressMapEntry {   
   DWORD rva,  
   DWORD rvaTo  
};  
```  
  
## Elements  
 `rva`  
 A. 이미지 상대 가상 주소 \(RVA\)  
  
 `rvaTo`  
 상대 가상 주소 `rva` B. 이미지에 매핑됩니다  
  
## 설명  
 주소 맵 이미지 레이아웃에서 번역 \(A\)를 다른 \(B\)를 제공합니다.  배열 `DiaAddressMapEntry` 구조를 기준으로 정렬 `rva` 주소 구조를 정의 합니다.  
  
 주소를 번역 `addrA`, A 이미지에 있는 주소에서 `addrB`, 이미지 B에서 다음 단계를 수행:  
  
1.  지도 항목을 검색 `e`에 가장 큰 `rva` 보다 작거나 `addrA`.  
  
2.  Set `delta = addrA – e.rva`.  
  
3.  Set `addrB = e.rvaTo + delta`.  
  
 배열 `DiaAddressMapEntry` 구조체에 전달 되는 [IDiaAddressMap::set\_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) 메서드.  
  
## 요구 사항  
 헤더: dia2.h  
  
## 참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaAddressMap::set\_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)