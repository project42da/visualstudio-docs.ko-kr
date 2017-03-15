---
title: "IDiaEnumLineNumbers::Clone | Microsoft Docs"
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
  - "IDiaEnumLineNumbers::Clone 메서드"
ms.assetid: fcd2479a-8ff7-4aba-a737-06123c280d54
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaEnumLineNumbers::Clone
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT Clone (   
   IDiaEnumLineNumbers** ppenum  
);  
```  
  
#### 매개 변수  
 `ppenum`  
 \[out\] 반환 된 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) 열거자의 복제본을 포함 하는 개체입니다.  번호 없는 줄 중복 된 열거자만.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)