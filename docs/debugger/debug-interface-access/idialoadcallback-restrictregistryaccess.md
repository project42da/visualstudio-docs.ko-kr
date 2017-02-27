---
title: "IDiaLoadCallback::RestrictRegistryAccess | Microsoft Docs"
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
  - "IDiaLoadCallback::RestrictRegistryAccess 메서드"
ms.assetid: de4760c3-a746-4bab-8065-1388fed31b67
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaLoadCallback::RestrictRegistryAccess
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

레지스트리 쿼리 기호 검색 경로 찾는 데 사용할 수 있는지 확인 합니다.  
  
## 구문  
  
```cpp#  
HRESULT RestrictRegistryAccess();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 모든 코드 이외의 반환 `S_OK` 레지스트리의 기호 검색 경로 쿼리 하는 것을 금지 합니다.  
  
## 참고 항목  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)