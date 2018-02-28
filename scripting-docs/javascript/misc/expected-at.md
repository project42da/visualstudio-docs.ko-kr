---
title: "예상 &#39; @&#39; | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT1032
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 82ff8b74-1710-4358-9a26-dc92ab29c53b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f007129aa8da3ac49112fbc83b7abd31e4356c4f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="expected-3939"></a>예상 &#39; @&#39;
조건부 컴파일 문에 사용 하 여 사용할 변수를 만들려고는 `@set` 문을 배치 하지 않고 있지만 at 기호 "**@**" 변수 이름 앞입니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   추가 at 기호 "**@**"는 변수 이름 바로 앞입니다. 예:  
  
    ```JavaScript  
    @set @myvar = 1  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [@set문](../../javascript/reference/at-set-statement-javascript.md)   
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)   
 [조건부 컴파일 변수](../../javascript/advanced/conditional-compilation-variables-javascript.md)