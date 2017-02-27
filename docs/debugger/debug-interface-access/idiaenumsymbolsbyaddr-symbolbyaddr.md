---
title: "IDiaEnumSymbolsByAddr::symbolByAddr | Microsoft Docs"
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
  - "IDiaEnumSymbolsByAddr::symbolByAddr 메서드"
ms.assetid: 0b6f5a68-8402-4f29-8219-20576fda8166
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaEnumSymbolsByAddr::symbolByAddr
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

열거자가 이미지 섹션 번호 및 오프셋 기준으로 조회를 수행 하 여 배치 합니다.  
  
## 구문  
  
```cpp#  
HRESULT symbolByAddr (   
   DWORD**      isect,  
   DWORD**      offsect,  
   IDiaSymbol** ppsymbol  
);  
```  
  
#### 매개 변수  
 isect  
 \[in\] 이미지 구역 번호를 입력 합니다.  
  
 offsect  
 \[in\] 섹션의 오프셋입니다.  
  
 ppsymbol  
 \[out\] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 기호를 찾을 수를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 기호를 찾을 수 없습니다 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)