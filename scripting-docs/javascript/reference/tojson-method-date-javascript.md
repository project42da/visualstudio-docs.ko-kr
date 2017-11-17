---
title: "toJSON 메서드 (Date) (JavaScript) | Microsoft Docs"
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
helpviewer_keywords: toJSON method
ms.assetid: f91df030-e9c9-425e-8e6d-b46bdda66cb6
caps.latest.revision: "27"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a131c7b248ca0486ab0b3b02d40e4351136c37c9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="tojson-method-date-javascript"></a>toJSON 메서드(Date)(JavaScript)
사용 하는 [JSON.stringify](../../javascript/reference/json-stringify-function-javascript.md) 메서드 개체 JSON (JavaScript Notation) serialization에 대 한 개체의 데이터의 변환을 사용할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
objectname.toJSON()  
```  
  
## <a name="parameters"></a>매개 변수  
 `objectname`  
 필수 요소. JSON에 대 한 serialization 하고자 하는 개체입니다.  
  
## <a name="remarks"></a>설명  
 `toJSON` 메서드를 사용 하 여는 `JSON.stringify` 함수입니다. `JSON.stringify`직렬화는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] JSON 텍스트에는 값입니다. 경우는 `toJSON` 메서드를 제공 됩니다 `JSON.stringify`, `toJSON` 메서드를 호출한 경우 `JSON.stringify` 라고 합니다.  
  
 `toJSON` 메서드는 기본 제공 소속 된 [날짜](../../javascript/reference/date-object-javascript.md) [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체입니다. UTC 표준 시간대 (접미사 Z로 표시)에 대 한 ISO 형식의 날짜 문자열을 반환 합니다.  
  
 재정의할 수 있습니다는 `toJSON` 에 대 한 메서드는 `Date` 입력 하거나 정의 `toJSON` JSON serialization 전에 특정 개체 유형에 대 한 데이터의 변환과 달성 하기 위해 다른 개체 형식에 대 한 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `toJSON` 대문자로 문자열 멤버 값을 serialize 하는 메서드. `toJSON` 메서드를 호출한 경우 `JSON.stringify` 라고 합니다.  
  
```JavaScript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
contact.toJSON = function(key)  
 {  
    var replacement = new Object();  
    for (var val in this)  
    {  
        if (typeof (this[val]) === 'string')  
            replacement[val] = this[val].toUpperCase();  
        else  
            replacement[val] = this[val]  
    }  
    return replacement;  
};  
  
var jsonText = JSON.stringify(contact);  
  
/* The value of jsonText is:  
'{"firstname":"JESPER","surname":"AABERG","phone":["555-0100","555-0120"]}'  
*/  
```  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 `toJSON` 의 기본 제공 멤버인 메서드는 [날짜](../../javascript/reference/date-object-javascript.md) 개체입니다.  
  
```JavaScript  
var dt = new Date('8/24/2009');  
dt.setUTCHours(7, 30, 0);  
var jsonText = JSON.stringify(dt);  
  
/* The value of jsonText is:  
'"2009-08-24T07:30:00Z"'  
*/  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)]**적용 대상:** [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [JSON 개체](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse 함수](../../javascript/reference/json-parse-function-javascript.md)   
 [JSON.stringify 함수](../../javascript/reference/json-stringify-function-javascript.md)   
 [JavaScript 메서드](../../javascript/reference/javascript-methods.md)