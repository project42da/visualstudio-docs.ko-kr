---
title: "IDiaSymbol::get_liveRangeStartAddressOffset | Microsoft Docs"
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
  - "IDiaSymbol::get_liveRangeStartAddressOffset"
ms.assetid: f5b28914-0a14-4b22-8259-59d7f97ee610
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_liveRangeStartAddressOffset
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

오프셋된 부분의 시작 주소에 로컬 기호가 유효 범위를 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_liveRangeStartAddressOffset (   
   DWORD* offset  
);  
```  
  
#### 매개 변수  
 `offset`  
 \[out\] 주소 범위 시작 부분 오프셋된을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
> [!NOTE]
>  반환 된 오류 코드 기호 라이브 범위 정보가 없는 것을 의미 합니다.  
  
## 설명  
 주소 섹션 및 오프셋으로 형성 된 기호가 유효 범위의 시작 부분입니다.  
  
 섹션 파트의 주소를 가져올 수 있습니다 [IDiaSymbol::get\_liveRangeStartAddressSection](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddresssection.md).  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia100.dll  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)