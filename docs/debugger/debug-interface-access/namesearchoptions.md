---
title: NameSearchOptions | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: NameSearchOptions enumeration
ms.assetid: 67dfbede-2678-47df-b664-5c49841d0b9b
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7ceadd085a3099721e73e04dd09ea5a0b81ad1d6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="namesearchoptions"></a>NameSearchOptions
기호 및 파일 이름에 대 한 검색 옵션을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
enum NameSearchOptions {   
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
  
## <a name="elements"></a>요소  
 `nsNone`  
 지정된 옵션이 없습니다.  
  
 `nsfCaseSensitive`  
 대/소문자 구분 이름 일치를 적용합니다.  
  
 `nsfCaseInsensitive`  
 대/소문자 구분 이름 일치를 적용합니다.  
  
 `nsfFNameExt`  
 이름 경로를 처리 하 고 filename.ext 이름 일치를 적용 합니다.  
  
 `nsfRegularExpression`  
 별표 (*) 및 물음표 (?)를 와일드 카드로 사용 하 여 대/소문자 구분 이름 일치를 적용 합니다.  
  
 `nsfUndecoratedName`  
 기호를 모두 데코 레이트 되지 않은 하 고 데코 레이트 된 이름에만 적용 됩니다.  
  
## <a name="remarks"></a>설명  
 이 열거형의 값은 다음 방법에 전달 됩니다.  
  
-   [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)  
  
-   [IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)  
  
-   [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)  
  
## <a name="requirements"></a>요구 사항  
 헤더: dia2.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasession:: Findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [Idiasession:: Findfile](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)