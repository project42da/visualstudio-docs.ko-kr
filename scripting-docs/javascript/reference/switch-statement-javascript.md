---
title: "switch 문 (JavaScript) | Microsoft Docs"
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
- switch_JavaScriptKeyword
- default_JavaScriptKeyword
- case_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- switch statement
ms.assetid: 61f80e8b-3739-4146-a893-c2832d92b28c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a301fc8bcc72b48c6ba8e999c0ebb70fe9d92b41
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="switch-statement-javascript"></a>switch 문(JavaScript)
지정된 식의 값이 레이블과 일치할 경우 하나 이상의 문을 실행할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
switch (expression) {  
    case label :  
        statementlist  
    case label :  
    default :  
        statementlist  
}   
```  
  
## <a name="parameters"></a>매개 변수  
 `expression`  
 평가할 식입니다.  
  
 `label`  
 식별자를 일치 시킬 `expression`합니다. 경우 `label` 는 `expression`, 실행이 시작 된는 `statementlist` 바로 뒤에 콜론을 중 하나에 도달할 때까지 계속 됩니다는 `break` 선택적 문 또는 끝날은 `switch` 문.  
  
 `statementlist`  
 실행할 하나 이상의 문입니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여는 `default` 레이블 없음 값이 일치 하는 경우 실행할 문을 제공 하는 절 `expression`합니다. 내에서 위치 사용할 수 있습니다는 `switch` 코드 블록입니다.  
  
 0 개 이상의 `label` 블록을 지정할 수 있습니다. 없는 경우 `label` 의 값과 일치 `expression`, 및 `default` 사례 제공 되지 않으면, 없습니다 문이 실행 됩니다.  
  
 실행을 통해 이동는 `switch` 문은 다음과 같이 합니다.  
  
-   평가 `expression` 살펴보세요 `label` 일치 하는 항목이 발견 될 때까지 순서 대로 합니다.  
  
-   경우는 `label` 값이 `expression`, 그에 따른 실행 `statementlist`합니다.  
  
     계속 실행 될 때까지 `break` 문이 실행 될 또는 `switch` 문 종료 합니다. 즉, 여러 `label` 경우 블록이 실행 되는 `break` 문이 사용 되지 않습니다.  
  
-   없는 경우 `label` equals `expression`로 이동는 `default` 사례입니다. 없는 경우 없는 `default` 대/소문자, 마지막 단계로 이동 합니다.  
  
-   끝에 다음 문을 실행을 계속는 `switch` 코드 블록입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 해당 형식에 대 한 개체를 테스트합니다.  
  
```JavaScript  
function MyObjectType(obj) {  
    switch (obj.constructor) {  
        case Date:  
            document.write("Object is a Date.");  
            break;  
        case Number:  
            document.write("Object is a Number.");  
            break;  
        case String:  
            document.write("Object is a String.");  
            break;  
        default:  
            document.write("Object is unknown.");  
    }  
}  
  
// Output when obj is a Date:  
// Object is a Date.  
  
// Output when obj is a Number:  
// Object is a Number.  
  
// Output when obj is a String:  
// Object is a String.  
  
// Output when obj is something other than a Date, Number, or String:  
// Object is unknown.  
  
```  
  
## <a name="example"></a>예제  
 다음 코드를 사용 하지 않는 경우 어떤 일이 생기는 `break` 문.  
  
```JavaScript  
function MyObjectType(obj) {  
    switch (obj.constructor) {  
        case Date:  
            document.write("Object is a Date.");  
        case Number:  
            document.write("Object is a Number.");  
        case String:  
            document.write("Object is a String.");  
        default:  
            document.write("Object is unknown.");  
    }  
}  
  
// Output when obj is a Date:  
// Object is a Date.Object is a Number.Object is a String.Object is unknown.  
  
// Output when obj is a Number:  
// Object is a Number.Object is a String.Object is unknown.  
  
// Output when obj is a String:  
// Object is a String.Object is unknown.  
  
// Output when obj is something other than a Date, Number, or String:  
// Object is unknown.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [break 문](../../javascript/reference/break-statement-javascript.md)   
 [if...else 문](../../javascript/reference/if-dot-dot-dot-else-statement-javascript.md)