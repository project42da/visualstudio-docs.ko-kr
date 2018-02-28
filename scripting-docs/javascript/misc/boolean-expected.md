---
title: "부울이 필요 합니다 | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT5010
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 35d71b7f-53fd-44c4-a7c7-b1550c65cfd4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 600ab26f60c2196ebc682adcffcd6b24c23cd358
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="boolean-expected"></a>부울이 필요합니다.
호출 하려고는 **Boolean.prototype.toString** 또는 **Boolean.prototype.valueOf** 아닌 다른 형식의 개체에서 메서드 `Boolean`합니다. 이 형식의 호출 개체 유형 이어야 `Boolean`합니다. 예:  
  
```JavaScript  
var o = new Object;  
o.f = Boolean.prototype.toString;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   부울 호출할**. prototype.toString** 또는 **Boolean.prototype.valueOf** 유형의 개체에 대 한 메서드 **부울입니다.**  
  
## <a name="see-also"></a>참고 항목  
 [Boolean 개체](../../javascript/reference/boolean-object-javascript.md)   
 [데이터 형식](../../javascript/data-types-javascript.md)   
 [프로그램 흐름 제어](../../javascript/controlling-program-flow-javascript.md)   
 [데이터 복사, 전달 및 비교](../../javascript/advanced/copying-passing-and-comparing-data-javascript.md)