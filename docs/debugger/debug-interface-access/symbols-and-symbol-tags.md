---
title: "기호 및 기호 태그 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: symbols [DIA SDK]
ms.assetid: 2ee3a262-cda6-48bf-b799-a37edde6c8b8
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 347ea483fda44d43d73b147a41a55f0945e515e9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="symbols-and-symbol-tags"></a>기호 및 기호 태그
컴파일된 프로그램에 대 한 디버그 정보 기호 디버그 인터페이스 액세스 (DIA) SDK Api를 사용 하 여 액세스할 수 있는 프로그램 데이터베이스 (.pdb) 파일에 저장 됩니다. 모든 기호는 [idiasymbol:: Get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) 및 [idiasymbol:: Get_symindexid](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md) 속성입니다. `symTag` 속성에 정의 된 대로 기호의 종류를 나타내는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 열거 합니다. `symIndexId` 속성은 한 `DWORD` 기호의 모든 인스턴스에 대해 고유 식별자를 포함 하는 값입니다.  
  
 기호에는 또한 가장 자주 기호 뿐만 아니라 다른 기호에 대 한 참조에 대 한 추가 정보를 지정할 수 있는 속성이 있는 [idiasymbol:: Get_lexicalparent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md) 또는 [idiasymbol:: Get_classparent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md). 참조로 반환 됩니다 대 한 참조를 포함 하는 속성을 쿼리할 때는 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 개체입니다. 이러한 속성은 항상 쌍을 이루는 다른 속성 하지만 접미사가 "Id"와 같은 이름으로 예를 들어 [idiasymbol:: Get_lexicalparentid](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md) 및 [idiasymbol:: Get_classparentid](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)합니다. 테이블에 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md), [기호 종류의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md), 및 [기호 종류의 클래스 계층 구조](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md) 다른 종류의 각 속성에 간략하게 설명의 기호입니다. 이러한 속성에 대 한 관련 정보 또는 다른 기호에 대 한 참조가 있을 수 있습니다. 때문에 `*Id` 속성은 관련된 속성의 서 수 단순히 숫자 식별자, 추가로 토론에서 생략 됩니다. 매개 변수 설명은 필요한 경우에에 참조 되 합니다.  
  
 오류가 발생 하지 않으면 기호 속성에 값을 할당 하는 경우의 속성을 액세스를 시도할 때 속성의 "get" 메서드 반환 `S_OK`합니다. 반환 값이 `S_FALSE` 속성이 현재 기호에 유효 하지 않음을 나타냅니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)  
 다양 한 종류의 기호를 가질 수 있습니다 위치를 설명 합니다.  
  
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)  
 파일, 모듈 및 함수 같은 어휘 계층 구조를 구성 하는 기호 형식을 설명 합니다.  
  
 [기호 형식의 클래스 계층 구조](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)  
 클래스, 배열 및 함수 반환 형식와 같은 다른 언어 요소에 해당 하는 기호 형식을 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 인터페이스 액세스 SDK](../../debugger/debug-interface-access/debug-interface-access-sdk.md)