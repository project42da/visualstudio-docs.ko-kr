---
title: "IDiaAddressMap::get_relativeVirtualAddressEnabled | Microsoft Docs"
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
  - "IDiaAddressMap::get_relativeVirtualAddressEnabled 메서드"
ms.assetid: 4c48af81-7148-4d9a-818e-dbe62cbfc638
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaAddressMap::get_relativeVirtualAddressEnabled
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

계산 및 사용의 상대 가상 주소 \(RVA\)의 사용 여부를 나타냅니다.  
  
## 구문  
  
```cpp#  
HRESULT get_relativeVirtualAddressEnabled (   
   BOOL* pRetVal  
);  
```  
  
#### 매개 변수  
 pRetVal  
 \[out\] 반환 `TRUE` Rva의 계산을 사용 하는 경우.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 Rva는 세그먼트에서 PDB 파일을 처음에 로드 되지 않은 경우 사용할 수 있습니다.  호출 하 여 Rva의 사용을 일시적으로 사용할 수 있습니다에서 [IDiaAddressMap::put\_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md) 메서드.  
  
 또한 새로운 이미지 헤더를 호출 하 여 설정할 수 있습니다는 [IDiaAddressMap::set\_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) 메서드를 차례로 호출 하 여 해당 `put_relativeVirtualAddressEnabled` Rva가 새로운 이미지 헤더를 사용 하 여 사용 하는 방법.  
  
## 참고 항목  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::set\_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)   
 [IDiaAddressMap::put\_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)