---
title: "IDiaAddressMap::put_relativeVirtualAddressEnabled | Microsoft Docs"
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
  - "IDiaAddressMap::put_relativeVirtualAddressEnabled 메서드"
ms.assetid: 767c078e-8ad7-4940-9e00-cae7704aadee
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaAddressMap::put_relativeVirtualAddressEnabled
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

계산 및 상대 가상 주소 \(RVA\)의 사용을 설정 하거나 해제 하는 클라이언트를 허용 합니다.  
  
## 구문  
  
```cpp#  
HRESULT put_relativeVirtualAddressEnabled (   
   BOOL NewVal  
);  
```  
  
#### 매개 변수  
 NewVal  
 \[in\] 설정 `TRUE` 를 사용 하려면 또는 `FALSE` 사용 하지 않도록 설정 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 상대 가상 주소로 DIA 인터페이스를 기본으로 실행 파일의 이미지를 기준으로 설명 되어 디버그 개체 주소를 검색할 수 있습니다.  
  
 Rva가 사용 하는 세그먼트에서 PDB 파일을 처음에 로드 될 때 사용 가능 합니다.  Rva의 사용의 현재 상태를 가져오려면 호출을 [IDiaAddressMap::get\_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) 메서드.  
  
 `put_relativeVirtualAddress` Rva가 성공적으로 호출 후 설정 하려면 메서드를 호출 해야 합니다는 [IDiaAddressMap::set\_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) 메서드는 새 이미지 헤더 설정 했습니다.  
  
## 참고 항목  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::get\_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)   
 [IDiaAddressMap::set\_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)