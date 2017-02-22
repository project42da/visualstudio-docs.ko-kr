---
title: "IDiaAddressMap::put_addressMapEnabled | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaAddressMap::put_addressMapEnabled 메서드"
ms.assetid: 0f205337-4e59-4383-8059-7b1d207d6dcd
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaAddressMap::put_addressMapEnabled
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

주소 맵 기호 주소를 변환에 사용할 것인지 여부를 지정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT put_addressMapEnabled (   
   BOOL NewVal  
);  
```  
  
#### 매개 변수  
 NewVal  
 \[in\] 설정 `TRUE` 기호 변환을 설정 하려면 또는 `FALSE` 사용 하지 않도록 설정 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 실행 가능한 포스트 가끔 실행 파일을 업데이트합니다.  DIA 기호 새 레이아웃의 번역을 지원 하기 위한 메커니즘이 포함 되어 있습니다.  
  
 PDB 파일을 로드 하는 경우 파일에 저장 된 주소 맵은 사용할 수 있습니다.  그러나 클라이언트 응용 프로그램이 될 수 있습니다 필요한 경우 주소 맵 자체를 호출 하 여 제공할 수 있습니다는 [IDiaAddressMap::set\_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) 메서드가 있습니다.  경우는 `set_addressMap` 메서드가 완료 되 고 클라이언트 응용 프로그램에서 호출 해야는 `put_addressMapEnabled` 메서드를 사용는 `NewVal` 매개 변수를 `TRUE` 맵에 주소를 사용 합니다.  
  
 주소 지도 활성화 되 고의 현재 상태를 검색할 수 있는 [IDiaAddressMap::get\_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md) 메서드.  
  
## 참고 항목  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::set\_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [IDiaAddressMap::get\_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)