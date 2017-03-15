---
title: "IDiaLineNumber::get_sourceFile | Microsoft Docs"
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
  - "IDiaLineNumber::get_sourceFile 메서드"
ms.assetid: 86fc4411-375e-4b99-8f96-4da2c3f68190
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaLineNumber::get_sourceFile
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 파일에 대 한 참조를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_sourceFile (   
   IDiaSourceFile** pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 된 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 원본 파일을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)