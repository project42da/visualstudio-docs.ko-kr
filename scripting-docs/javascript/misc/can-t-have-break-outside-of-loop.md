---
title: "수 &#39;가 t &#39; 나누기 &#39; 루프 외부에서 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT1019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 11d02172-2a78-4705-a730-d21111db5f42
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bb23f1bc3de087515cad9ba4910cf2ebaf640353
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="can39t-have-39break39-outside-of-loop"></a>수 &#39;가 t &#39; 나누기 &#39; 루프 외부에서
사용 하려는 **나누기** 루프 외부에서 키워드입니다. **나누기** 키워드를 사용 하는 루프를 종료 또는 `switch` 문. 루프의 본문에 포함 되어 있어야 또는 `switch` 문. 그러나 한 **레이블** break 키워드 다음에 올 수 있습니다.  
  
```  
break labelname;  
```  
  
 레이블이 지정 된 형식의 하기만 하면는 **나누기** 키워드를 사용 하는 중첩 루프 또는 `switch` 문 및 필요성은 가장 안쪽 한 아닙니다. 하는 루프를 중단 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   있는지 확인은 **나누기** 키워드 바깥쪽 루프 또는 switch 문 내에 표시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [break 문](../../javascript/reference/break-statement-javascript.md)   
 [프로그램 흐름 제어](../../javascript/controlling-program-flow-javascript.md)   
 [스크립트 문제 해결](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)