---
title: "IDiaSymbol::get_virtualTableShapeId | Microsoft Docs"
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
  - "IDiaSymbol::get_virtualTableShapeId 메서드"
ms.assetid: cbee9944-817a-4805-9c08-fac8e0da58b7
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_virtualTableShapeId
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

심볼의 가상 테이블 셰이프 기호 식별자를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_virtualTableShapeId (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 심볼의 가상 테이블 기호 ID를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성에 사용할 수 있음을 의미 합니다.  
  
## 설명  
 식별자는 DIA SDK를 고유 이름으로 모든 기호를 표시 하 여 만든 고유한 값입니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)