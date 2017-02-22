---
title: "IDiaImageData::get_imageBase | Microsoft Docs"
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
  - "IDiaImageData::get_imageBase 메서드"
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaImageData::get_imageBase
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이미지를 기반으로 해야 합니다 메모리 위치를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_imageBase (   
   ULONGLONG* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 제안 된 이미지 기본 값을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 기준 주소가 로드 될 때 이미지 기본 충돌 하 여 이미지 자동으로 사용 하지 않는 메모리 위치를 변경 될 수 있습니다.  컴파일 타임에 해당 모듈에 저장 된 기본 힌트 \(권장 되는 메모리 위치\)이 반환 됩니다.  
  
## 참고 항목  
 [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)