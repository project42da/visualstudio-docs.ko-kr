---
title: "IDiaLoadCallback2::RestrictReferencePathAccess | Microsoft Docs"
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
  - "IDiaLoadCallback2::RestrictReferencePathAccess 메서드"
ms.assetid: e20cb45c-0360-4ff0-a92c-b1b6f76d6e85
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaLoadCallback2::RestrictReferencePathAccess
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

.Exe 파일이 있는 경로에서.pdb 파일을 찾을 수 있는지 여부를 결정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT RestrictReferencePathAccess();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 모든 코드 이외의 반환 `S_OK` .exe 파일이 위치한.pdb 파일의 경로 검색 하지 않도록 합니다.  
  
## 참고 항목  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)