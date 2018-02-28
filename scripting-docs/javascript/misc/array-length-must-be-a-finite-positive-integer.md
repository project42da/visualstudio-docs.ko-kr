---
title: "배열 길이 유한한 양의 정수 여야 합니다. | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT5029
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1a467040-4702-4178-848f-418a5974e907
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c6589bd2e9bb4acbec5f169087a49e64417dfae7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="array-length-must-be-a-finite-positive-integer"></a>배열의 길이는 유한한 양의 정수여야 합니다.
호출 하는 **배열** 생성자 인수 (정수 0을 더한 양의 정수 집합으로 구성)는 정수를 사용 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   양의 정수를 사용 하 여 새를 만들 때만 `Array` 개체입니다. 정수가 아닌 단일 요소가 있는 배열의 만들려는 경우에 두 단계로 수행 합니다. 하나의 요소가 표시 된 배열을 만들고 후 (array[0]) 첫 번째 요소에 값을 배치 합니다. 다음은이 오류를 생성 하는 예제입니다.  
  
    ```JavaScript  
    var piArray = new Array(3.14159);  
    ```  
  
     다음 예제에서는 단일 숫자 요소가 있는 배열을 지정 하는 올바른 방법을 보여 줍니다.  
  
    ```JavaScript  
    var piArray = new Array(1);  
    piArray [0] = 3.14159;  
    ```  
  
     최대 정수 값 (약 4 십억)이 아닌 다른 배열 크기에 대 한 상위 제한은 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)