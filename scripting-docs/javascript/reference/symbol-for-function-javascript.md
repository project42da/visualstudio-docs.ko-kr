---
title: "Symbol.for 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 27db15f3-9108-4892-8f89-e84031729cb6
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b7e47c00fbaa321d71a3eeba79e523eee719fb2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="symbolfor-function-javascript"></a>Symbol.for 함수(JavaScript)
지정된 키에 대한 기호를 반환하거나 키가 없는 경우 새 키를 사용하여 새 기호 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Symbol.for(key);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `key`  
 필수 요소. 설명으로도 사용되는 기호에 대한 키입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 전체 기호 레지스트리에서 해당 기호를 검색합니다. 기호를 문자열로 직렬화하는 경우 전역 기호 레지스트리를 사용하여 특정 문자열 맵이 모든 조회에 대해 올바른 기호를 보여주도록 합니다.  
  
## <a name="example"></a>예제  
  
```JavaScript  
var sym = Symbol.for("desc");  
  
console.log(sym.toString());  
  
// Two different object references.  
console.log(Symbol("symbol") === Symbol.for("symbol");)  
// Single object reference.   
console.log(Symbol.for("symbol") === Symbol.for("symbol");)  
  
// Output:  
// Symbol(desc);  
// false  
// true  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]