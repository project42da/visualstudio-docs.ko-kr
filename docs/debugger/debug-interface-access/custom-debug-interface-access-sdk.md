---
title: "사용자 지정(디버그 인터페이스 액세스 SDK) | Microsoft Docs"
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
  - "사용자 지정 기호"
ms.assetid: a219fc83-d2a8-4bc5-b7e1-bfafeb247f16
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# 사용자 지정(디버그 인터페이스 액세스 SDK)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

일부 컴파일러에서는 표준 어휘 기호 종류 중 하나를 사용 하 여 식별 된 심볼을 소개 합니다.  이러한 기호로 식별 되는 `SymTagCustom` 태그.  
  
## 속성  
 다음 표에서이 기호 형식에 대해 유효한 속성을 보여 줍니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_dataBytes](../../debugger/debug-interface-access/idiasymbol-get-databytes.md)|`BYTE`|심볼과 관련 된 데이터의 배열입니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagCustom` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
  
## 참고 항목  
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)