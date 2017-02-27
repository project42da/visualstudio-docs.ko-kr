---
title: "Friend(디버그 인터페이스 액세스 SDK) | Microsoft Docs"
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
  - "friend 함수[DIA SDK]"
  - "friend 클래스[DIA SDK]"
  - "Friend 기호"
ms.assetid: 5147a170-41ce-4727-8ace-c318e8d11647
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# Friend(디버그 인터페이스 액세스 SDK)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Friend 클래스 및 friend 함수에서 확인 `SymTagFriend` 기호입니다.  사용자 정의 형식 \(Udt\) 부모 자식이 되 고 있는 [IDiaSymbol::get\_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md) 속성입니다.  
  
## 속성  
 다음 표에서이 심볼 유형 추가 유효한 속성이 표시 됩니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|UDT 부모에 대 한 기호입니다.|  
|[IDiaSymbol::get\_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|부모 기호가 클래스의 ID입니다.|  
|[IDiaSymbol::get\_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|클래스 또는 함수 이름입니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagFriend` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
|[IDiaSymbol::get\_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|클래스 또는 함수에 대 한 기호입니다.|  
|[IDiaSymbol::get\_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID 유형 기호입니다.|  
  
## 참고 항목  
 [기호 형식의 클래스 계층 구조](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)