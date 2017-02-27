---
title: "IDiaAddressMap::get_addressMapEnabled | Microsoft Docs"
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
  - "IDiaAddressMap::get_addressMapEnabled 메서드"
ms.assetid: 6183dc5e-befa-4e5a-ae5a-f4aa24f3ed9e
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaAddressMap::get_addressMapEnabled
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

주소 맵 특정 세션에 대해 설정 되었는지 여부를 나타냅니다.  
  
## 구문  
  
```cpp#  
HRESULT get_addressMapEnabled (   
   BOOL* pRetVal  
);  
```  
  
#### 매개 변수  
 pRetVal  
 \[out\] 반환 `TRUE` 주소 매핑을 사용 하는 경우.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 실행 가능한 포스트 가끔 실행 파일을 업데이트합니다.  DIA 기호 새 레이아웃의 번역을 지원 하기 위한 메커니즘이 포함 되어 있습니다.  
  
 클라이언트 응용 프로그램 설정 주소 맵 특정 세션에 대해 여는 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md) 에서 인터페이스는 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 인터페이스와 호출의 [IDiaAddressMap::set\_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) 메서드를 차례로 호출 하 여는 [IDiaAddressMap::put\_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md) 메서드.  `get_addressMapEnabled` 메서드 호출의 결과 반환의 `put_addressMapEnabled` 메서드.  
  
## 참고 항목  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaAddressMap::set\_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [IDiaAddressMap::put\_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)