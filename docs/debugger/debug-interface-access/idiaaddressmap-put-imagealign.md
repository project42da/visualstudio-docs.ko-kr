---
title: "IDiaAddressMap::put_imageAlign | Microsoft Docs"
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
  - "IDiaAddressMap::put_imageAlign 메서드"
ms.assetid: f9ce875d-c263-43e5-a534-f34c37f9866f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaAddressMap::put_imageAlign
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이미지 맞춤을 설정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT put_imageAlign (   
   DWORD NewVal  
);  
```  
  
#### 매개 변수  
 NewVal  
 \[in\] 실행 파일의 새 이미지 맞춤 값입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이미지 \(로드 된 실행 파일\)에 지정 된 메모리 경계선에 정렬 됩니다.  이 맞춤 현재 시스템 아키텍처 및 컴파일 및 링크 시간 옵션이 달라질 수 있습니다.  이미지 맞춤 항상 바이트 경계에 있습니다.  다음 이미지 맞춤 값이 잘못 되었습니다: 1, 2, 4, 8, 16, 32 및 64 바이트 경계입니다.  
  
 현재 이미지 맞춤을 검색할 수 있는 [IDiaAddressMap::get\_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md) 메서드.  
  
> [!NOTE]
>  이미지는이 메서드를 호출 하는 시점에 이미 로드 되었습니다.  `put_imageAlign` 메서드는 이미지 이동 되거나 변경 되었으므로 새 맞춤 필요한 때 일반적으로 사용 됩니다.  
  
## 참고 항목  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::get\_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)