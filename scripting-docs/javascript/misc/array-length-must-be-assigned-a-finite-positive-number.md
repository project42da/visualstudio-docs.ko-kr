---
title: "배열 길이 유한한 양수로 할당 해야 | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT5030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: c51c66a4-a543-4e95-b18d-2cfbcb3d1fdd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63a9d714173334192028b9096de41968befa85ef
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="array-length-must-be-assigned-a-finite-positive-number"></a>배열의 길이는 유한한 양수로 할당해야 합니다.
설정 하는 경우는 **길이** 기존 속성 **배열** 양수 또는 0이 되지 않은 배열 길이 지정한 개체입니다. 에 값을 할당 하는 경우이 오류가 발생는 **길이** 속성은 `Array` 가 음수 개체나 not-a-number (`NaN`). [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 소수 정수일에서 자동으로 변환 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   Length 속성에 양의 정수를 할당 합니다. 최대 정수 값 (약 4 십억)이 아닌 다른 배열 크기에 대 한 상위 제한은 없습니다. 다음 예제에서는 설정 하는 올바른 방법은 **길이** 속성은 **배열** 개체입니다.  
  
    ```JavaScript  
    var my_array = new Array();  
    my_array.length = 99;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)