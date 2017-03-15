---
title: "IDiaLoadCallback2::RestrictOriginalPathAccess | Microsoft Docs"
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
  - "IDiaLoadCallback2::RestrictOriginalPathAccess 메서드"
ms.assetid: 31fde3af-2824-4b0f-8d0d-cee6046596f6
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaLoadCallback2::RestrictOriginalPathAccess
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

원래 debug 디렉터리에.pdb 파일에 찾을 수 있는지 여부를 결정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT RestrictOriginalPathAccess ();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 모든 코드 이외의 반환 `S_OK` 원래 debug 디렉터리에.pdb 파일을 찾을 수 없습니다.  원래 디버그 디렉터리 디버깅 설정 하면 실행 파일로 컴파일 심볼 파일의 경로입니다.  이 경로 실행 파일이 있는 경로와 같으면 되지는지 않습니다.  
  
## 참고 항목  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)