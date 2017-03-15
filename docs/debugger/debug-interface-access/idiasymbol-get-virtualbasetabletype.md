---
title: "IDiaSymbol::get_virtualBaseTableType | Microsoft Docs"
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
  - "IDiaSymbol::get_virtualBaseTableType 메서드"
ms.assetid: e0581c4f-0343-49b5-9754-a48477460e9f
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaSymbol::get_virtualBaseTableType
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기본 가상 테이블 포인터를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_virtualBaseTableType(  
   IDiaSymbol *pRetVal  
};  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`pRetVal`|\[out\] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 는 기본 테이블의 형식을 지정 하는 개체입니다.|  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
 기본 가상 테이블 포인터 \(`vbtptr`\)는 숨겨진 포인터에 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] vtable을 처리 하는 가상 기본 클래스에서 상속 합니다.  A `vbtptr` 상속 된 클래스에 따라 서로 다른 크기를 가질 수 있습니다.  
  
 이 메서드는 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 개체는 vbtptr의 크기를 결정 하는 데 사용할 수 있습니다.  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)