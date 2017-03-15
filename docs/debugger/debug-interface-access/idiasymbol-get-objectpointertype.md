---
title: "IDiaSymbol::get_objectPointerType | Microsoft Docs"
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
  - "IDiaSymbol::get_objectPointerType 메서드"
ms.assetid: bce193b9-67b0-4c35-96e5-6a664937322e
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_objectPointerType
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

개체 클래스 메서드에 대 한 포인터를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_objectPointerType (   
   IDiaSymbol** pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 개체 클래스 메서드에 대 한 포인터를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
 기호를 사용에이 속성이 적용 됩니다. 한 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 을 입력 `SymTagFunctionType`.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)