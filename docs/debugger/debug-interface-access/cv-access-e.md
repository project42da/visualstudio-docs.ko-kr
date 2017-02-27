---
title: "CV_access_e | Microsoft Docs"
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
  - "CV_access_e 열거형"
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# CV_access_e
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

표시 여부 \(액세스 수준\)의 멤버 함수 및 변수 범위를 지정합니다.  
  
## 구문  
  
```cpp#  
typedef enum CV_access_e {   
   CV_private   = 1,  
   CV_protected = 2,  
   CV_public    = 3  
} CV_access_e;  
```  
  
## Elements  
 CV\_private  
 멤버 전용 액세스 권한을 갖습니다.  
  
 CV\_protected  
 멤버 액세스를 보호 했습니다.  
  
 CV\_public  
 멤버는 공용 액세스 권한을 갖습니다.  
  
## 설명  
 `friend` 액세스 지정자는 포함 되지 않습니다 여기 클래스 전용 및 보호 된 요소에 액세스할 비멤버 함수에 의해 일반적으로 사용 하기 때문입니다.  사용은 [IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) 방법으로 기호를 찾을 수 `SymTagFriend` 액세스 합니다.  
  
## 요구 사항  
 헤더: cvconst.h  
  
## 참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get\_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)   
 [IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)