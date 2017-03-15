---
title: "IDiaAddressMap::set_imageHeaders | Microsoft Docs"
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
  - "IDiaAddressMap::set_imageHeaders 메서드"
ms.assetid: a46b9d0e-43e6-433f-b2c7-aa203981e4e4
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaAddressMap::set_imageHeaders
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

집합 상대 가상 주소 변환 사용 하려면 머리글 이미지.  
  
## 구문  
  
```cpp#  
HRESULT set_imageHeaders (   
   DWORD cbData,  
   BYTE  data[],  
   BOOL  originalHeaders  
);  
```  
  
#### 매개 변수  
 사용  
 \[in\] 헤더 데이터의 바이트 수입니다.  되어야 합니다 `n*sizeof(IMAGE_SECTION_HEADER)` 는 `n` 섹션 헤더에 있는 실행 파일 수입니다.  
  
 데이터\]  
 \[in\] 배열 `IMAGE_SECTION_HEADER` 구조를 이미지 헤더 이름으로 사용할 수 있습니다.  
  
 originalHeaders  
 \[in\] 설정 `FALSE` 경우 새 이미지에서 이미지 헤더 `TRUE` 는 업그레이드 하기 전에 원본 이미지를 반영 하는 경우.  일반적으로이 설정 될 `TRUE` 를 호출 하는 조합에는 [IDiaAddressMap::set\_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) 메서드.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 `IMAGE_SECTION_HEADER` 구조는 winnt.h에 선언 된 및 실행 파일의 이미지 섹션 헤더 형식을 나타냅니다.  
  
 상대 가상 주소 계산에 의존의 `IMAGE_SECTION_HEADER` 값입니다.  일반적으로 DIA 프로그램 데이터베이스 \(.pdb\) 파일을 검색합니다.  이러한 값이 누락 된 경우는 DIA 상대 가상 주소를 계산할 수 없습니다 및 해당 [IDiaAddressMap::get\_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) 메서드가 반환 `FALSE`.  클라이언트 호출 해야 다음의 [IDiaAddressMap::put\_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md) 의 상대 가상 주소 계산 누락 된 이미지 헤더 이미지 자체에서 제공 된 후 메서드.  
  
## 참고 항목  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::set\_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [IDiaAddressMap::get\_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)   
 [IDiaAddressMap::put\_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)