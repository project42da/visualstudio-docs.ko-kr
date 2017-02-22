---
title: "NameSearchOptions | Microsoft Docs"
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
  - "NameSearchOptions 열거형"
ms.assetid: 67dfbede-2678-47df-b664-5c49841d0b9b
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# NameSearchOptions
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호 및 파일 이름에 대 한 검색 옵션을 지정합니다.  
  
## 구문  
  
```cpp#  
enum NameSearchOptions {   
   nsNone,  
   nsfCaseSensitive     = 0x1,  
   nsfCaseInsensitive   = 0x2,  
   nsfFNameExt          = 0x4,  
   nsfRegularExpression = 0x8,  
   nsfUndecoratedName   = 0x10,  
  
// For backward compatibility:  
   nsCaseSensitive           = nsfCaseSensitive,  
   nsCaseInsensitive         = nsfCaseInsensitive,  
   nsFNameExt                = nsfCaseInsensitive | nsfFNameExt,  
   nsRegularExpression       = nsfRegularExpression | nsfCaseSensitive,  
   nsCaseInRegularExpression = nsfRegularExpression | nsfCaseInsensitive  
};  
```  
  
## Elements  
 `nsNone`  
 옵션을 지정하지 않았습니다.  
  
 `nsfCaseSensitive`  
 대\/소문자 구분 이름 일치 하는 항목에 적용 됩니다.  
  
 `nsfCaseInsensitive`  
 대\/소문자 구분 이름 일치 하는 항목에 적용 됩니다.  
  
 `nsfFNameExt`  
 이름과 경로로 취급 및 filename.ext 이름이 일치 하는 항목에 적용 됩니다.  
  
 `nsfRegularExpression`  
 와일드 카드로 별표 \(\*\)와 물음표 \(?\)를 사용 하 여 대\/소문자 구분 이름 일치 하는 항목에 적용 됩니다.  
  
 `nsfUndecoratedName`  
 있는 데코레이팅된 이름 및 데코레이팅되지 않은 기호에만 적용 합니다.  
  
## 설명  
 이 열거형의 값은 다음 방법으로 전달 됩니다.  
  
-   [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)  
  
-   [IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)  
  
-   [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)  
  
## 요구 사항  
 헤더: dia2.h  
  
## 참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)