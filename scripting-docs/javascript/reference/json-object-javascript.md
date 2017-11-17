---
title: "JSON 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: JSON
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: JSON object
ms.assetid: 0279a0e0-70bf-451a-a78e-0da4e2fdeb9a
caps.latest.revision: "43"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5310132368f665c6734c469a67636d33a08858d4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="json-object-javascript"></a>JSON 개체(JavaScript)
JSON(JavaScript Object Notation) 형식 간 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 값을 변환하는 함수를 제공하는 내장 개체입니다. `JSON.stringify` 함수는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 값을 JSON 텍스트로 serialize합니다. `JSON.parse` 함수는 JSON 텍스트를 deserialize하여 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 값을 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
JSON.[method]  
  
```  
  
## <a name="parameters"></a>매개 변수  
 `Method`  
 필수 요소. `JSON` 개체의 메서드 중 하나의 이름입니다.  
  
## <a name="remarks"></a>설명  
 `JSON` 연산자를 사용하여 `new` 개체를 만들 수 없습니다. 만들려고 하면 오류가 발생합니다. 그러나 `JSON` 개체를 재정의하거나 수정할 수 있습니다.  
  
 엔진이 로드될 때 스크립팅 엔진에서 `JSON` 개체를 만듭니다. 해당 메서드는 스크립트에 항상 사용할 수 있습니다.  
  
 내장 `JSON` 개체를 사용하려면 스크립트에 정의된 다른 `JSON` 개체로 이 개체를 재정의하지 못합니다. 문이 다르게 평가되기 때문에 `JSON` 개체의 존재를 검색하는 기존 스크립트 문을 수정해야 할 수 있습니다. 다음 예제를 통해 볼 수 있습니다.  
  
```JavaScript  
if (!this.JSON) {  
    // JSON object does not exist.  
    }  
```  
  
 앞의 예제에서 `!this.JSON`은 [!INCLUDE[jsv58text](../../javascript/reference/includes/jsv58text-md.md)]에서 false로 평가됩니다. 따라서 `if` 문 안의 코드가 실행되지 않습니다.  
  
## <a name="functions"></a>함수  
 [JSON.parse 함수](../../javascript/reference/json-parse-function-javascript.md)  
  
 [JSON.stringify 함수](../../javascript/reference/json-stringify-function-javascript.md)  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [toJSON 메서드 (Date)](../../javascript/reference/tojson-method-date-javascript.md)   
 [JavaScript 개체](../../javascript/reference/javascript-objects.md)   
 [허브 템플릿 샘플 앱 (Windows 스토어)](http://code.msdn.microsoft.com/Hub-template-sample-with-4b70002d)