---
title: "ManagedType | Microsoft Docs"
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
  - "SymTagManagedType 기호"
  - "관리되는 형식 기호"
  - "ManagedType 기호"
ms.assetid: 5db99e2a-4f2e-4796-89b7-b401b151826f
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# ManagedType
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

관리 되는 형식 \(메타 데이터 또는 C\#와 같은 언어의 메모리 및 리소스 관리 기능을 기본으로 정의 된 기호\)로 식별 되는 `SymTagManagedType` 기호입니다.  
  
## 속성  
 다음 표에서이 심볼 유형 추가 유효한 속성이 표시 됩니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|관리 되는 심볼의 이름입니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagManagedType` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
  
## 참고 항목  
 [기호 형식의 클래스 계층 구조](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)