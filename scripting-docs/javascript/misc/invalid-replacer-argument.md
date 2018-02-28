---
title: "잘못 된 치환 인수입니다. | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5035
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 4727186f-facd-4aa6-9447-bbefbae83f07
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 588909bae9c5cf198d3108490111b36d5a2d182b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="invalid-replacer-argument"></a>잘못된 치환 인수입니다.
호출 하려고 `JSON.stringify` 유효 하지 않은 인수를 사용 합니다. `replacer` 인수는 함수 또는 배열 이어야 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   변경 된 `replacer` 인수는 함수 또는 배열입니다.  
  
## <a name="example"></a>예제  
 이 예제의 코드 때문에 런타임 오류를 발생 `memberfilter` 은 함수 또는 배열 하는 대신 개체입니다.  
  
```JavaScript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
var memberfilter = new Object();  
  
// This line will cause a runtime error.  
var jsontext = JSON.stringify(contact, memberfilter, "\t");  
```  
  
## <a name="see-also"></a>참고 항목  
 [JSON 개체](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse 함수](../../javascript/reference/json-parse-function-javascript.md)   
 [JavaScript 런타임 오류](../../javascript/reference/javascript-run-time-errors.md)