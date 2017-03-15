---
title: "기호 및 기호 태그 | Microsoft Docs"
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
  - "기호[DIA SDK]"
ms.assetid: 2ee3a262-cda6-48bf-b799-a37edde6c8b8
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# 기호 및 기호 태그
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 정보 컴파일된 프로그램에 대 한 기호는 디버그 인터페이스 액세스 \(DIA\) SDK Api를 사용 하 여 액세스할 수 있는 프로그램 데이터베이스 \(.pdb\) 파일에 저장 됩니다.  모든 기호는 [IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) a [IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md) 속성입니다.  `symTag` 속성으로 정의 된 심볼의 종류를 나타냅니다의 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 열거형입니다.  `symIndexId` 속성은 `DWORD` 심볼의 모든 인스턴스에 대 한 고유 식별자를 포함 하는 값입니다.  
  
 기호 수도 있습니다 대부분의 기타 기호에 대 한 참조 뿐만 아니라 기호에 대 한 추가 정보를 지정할 수 있는 속성은 [IDiaSymbol::get\_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md) 또는 [IDiaSymbol::get\_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md).  에 대 한 참조를 포함 하는 속성을 쿼리 하는 경우에 대 한 참조로 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 개체입니다.  이러한 속성이 항상 다른 속성을 사용 하지만 suffixed "Id"와 같은 이름으로 예를 들어, 쌍을 이루고 [IDiaSymbol::get\_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md) 및 [IDiaSymbol::get\_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md).  테이블에 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md), [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md), 및 [기호 형식의 클래스 계층 구조](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md) 속성을 각각 다른 종류의 기호에 대 한 개요입니다.  이러한 속성에 대 한 관련 정보 또는 기타 기호에 대 한 참조가 있을 수 있습니다.  때문에 `*Id` 속성은 해당 관련된 속성의 서 수 단순히 숫자 식별자, 더 이상 토론에서 생략 됩니다.  이들은 매개 변수가 필요한 경우에 의미 합니다.  
  
 오류가 발생 하지 않습니다 및 심볼 속성 값이 할당 된 경우 속성에 액세스 하면 속성의 "반환 get" `S_OK`.  반환 값이 `S_FALSE` 속성이 현재 기호를 사용할 수 없음을 나타냅니다.  
  
## 단원 내용  
 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)  
 다양 한 종류의 기호를 사용할 수 있습니다 위치에 설명 합니다.  
  
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)  
 파일, 모듈 및 함수 같은 어휘 계층 구조를 형성 하는 심볼 유형에 대해 설명 합니다.  
  
 [기호 형식의 클래스 계층 구조](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)  
 클래스, 배열 및 함수 반환 형식 같은 다른 언어 요소에 해당 하는 기호 형식에 설명 합니다.  
  
## 참고 항목  
 [디버그 인터페이스 액세스 SDK](../../debugger/debug-interface-access/debug-interface-access-sdk.md)