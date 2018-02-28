---
title: "callee 속성 (arguments) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- callee
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- callee property
ms.assetid: ad9d4d21-73f0-44f6-8bec-502f3456cd23
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33f1c2926d76c0a1f088c8f4222b6f24c004b73b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="callee-property-arguments-javascript"></a>callee 속성(arguments)(JavaScript)
반환 된 `Function` 개체를 실행 하는 지정 된 본문, 즉 `Function` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
[function.]arguments.callee  
```  
  
## <a name="remarks"></a>설명  
 선택적 *함수* 인수는 현재 실행의 이름 `Function` 개체입니다.  
  
 `callee` 속성은의 구성원은 **인수** 연결 된 함수는 실행 하는 경우에 사용할 수 있는 개체입니다.  
  
 초기 값은 `callee` 속성은는 `Function` 실행 중인 개체입니다. 따라서 익명 함수를를 반복적으로 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
  
```JavaScript  
function factorial(n){  
  if (n <= 0)  
     return 1;  
  else  
     return n * arguments.callee(n - 1)  
}  
document.write(factorial(4));  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [인수 개체](../../javascript/reference/arguments-object-javascript.md)&#124; [개체 함수](../../javascript/reference/function-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [caller 속성(Function)](../../javascript/reference/caller-property-function-javascript.md)