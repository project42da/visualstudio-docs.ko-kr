---
title: "IDiaEnumSourceFiles::Clone | Microsoft Docs"
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
  - "IDiaEnumSourceFiles::Clone 메서드"
ms.assetid: 87a9a9b6-3927-4131-927c-ad95f8f098b9
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSourceFiles::Clone
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT Clone (   
   IDiaEnumSourceFiles** ppenum  
);  
```  
  
#### 매개 변수  
 ppenum  
 \[out\] 반환 된 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md) 열거자의 복제본을 포함 하는 개체입니다.  원본 파일에 없는 중복 해당 열거자가.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)