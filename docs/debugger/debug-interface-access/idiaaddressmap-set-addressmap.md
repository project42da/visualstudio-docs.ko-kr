---
title: "IDiaAddressMap::set_addressMap | Microsoft Docs"
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
  - "IDiaAddressMap::set_addressMap 메서드"
ms.assetid: 81e82073-089b-43d5-af39-49d7a4907c7a
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaAddressMap::set_addressMap
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이미지가 레이아웃 변환을 지원 하기 위해 주소 맵을 제공 합니다.  
  
## 구문  
  
```cpp#  
HRESULT set_addressMap (   
   DWORD                     cbData,  
   struct DiaAddressMapEntry data[],  
   BOOL                      imagetoSymbols  
);  
```  
  
#### 매개 변수  
 `cbData`  
 \[in\] 요소의 수는 `data` 매개 변수.  
  
 `data[]`  
 \[in\] 배열 [DiaAddressMapEntry 구조체](../../debugger/debug-interface-access/diaaddressmapentry.md) 변환 매핑이 정의 구조체입니다.  
  
 `imagetoSymbols`  
 \[in\] `TRUE` 경우는 `data` 매개 변수 정의 지도 새 이미지 레이아웃을 원래 레이아웃에 \(에서 디버그 기호를 설명 하는 대로\).  `FALSE`경우 `data` 지도에 새로운 이미지 레이아웃을 원래 레이아웃에서 찍은 것입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 일반적으로 DIA 주소 변환 맵의 프로그램 데이터베이스 \(.pdb\) 파일을 검색합니다.  이러한 값이 없는 경우는 [IDiaAddressMap::set\_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) 메서드가 두 번 호출 한 번에 `imagetoSymbols` 매개 변수를 설정 `TRUE` 및 한 번에 `imagetoSymbols` 매개 변수를 설정 `FALSE`.  주소 맵 변환을 사용 하 여 사용할 수 없습니다의 [IDiaAddressMap::put\_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md) 메서드 모두 변환을 지도 제공 하는 경우를 제외 합니다.  
  
## 참고 항목  
 [DiaAddressMapEntry 구조체](../../debugger/debug-interface-access/diaaddressmapentry.md)   
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::put\_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)   
 [IDiaAddressMap::set\_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)