---
title: "IDiaEnumSourceFiles::Item | Microsoft Docs"
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
  - "IDiaEnumSourceFiles::Item 메서드"
ms.assetid: 3c19d7ed-0232-4b0e-9b10-f33ed9e0c93b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaEnumSourceFiles::Item
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 파일의 인덱스를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Item (   
   DWORD            index,  
   IDiaSourceFile** sourceFile  
);  
```  
  
#### 매개 변수  
 인덱스\(index\)  
 \[in\] 색인은 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 검색할 개체입니다.  인덱스는 범위가 0입니다 `count`\-1, 어디 `count` 반환 하는 있는 [IDiaEnumSourceFiles::get\_Count](../../debugger/debug-interface-access/idiaenumsourcefiles-get-count.md) 메서드.  
  
 원본 파일  
 \[out\] 반환 된 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 원하는 원본 파일을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)