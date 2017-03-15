---
title: "IDiaLoadCallback2::RestrictDBGAccess | Microsoft Docs"
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
  - "IDiaLoadCallback2::RestrictDBGAccess 메서드"
ms.assetid: 63b67a93-2910-4fff-aa70-6b2eaa08e5c8
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaLoadCallback2::RestrictDBGAccess
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

.Dbg 파일에서 디버그 정보를 찾을 수 있는지 여부를 결정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT RestrictDBGAccess();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이외의 다른 모든 값 반환 `S_OK` .dbg 파일에서 디버그 정보를 찾는 방지 합니다.  
  
## 참고 항목  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)