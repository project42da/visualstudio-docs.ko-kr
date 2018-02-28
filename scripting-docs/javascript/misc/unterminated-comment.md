---
title: "주석 종결 되지 않은 | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT1016
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d4286315-814b-4966-b4c4-1ee19d796eff
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9fde5d5edd7e81060b088e4940d752aa05e65ded
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="unterminated-comment"></a>종결되지 않은 주석입니다.
여러 줄의 주석 블록을 시작 하지만 제대로 종료 되지 않았습니다. 여러 줄 주석을로 시작는 "/ *" 조합과로 끝나야 "\*/" 조합 합니다. 예를 들면 다음과 같습니다.  
  
```JavaScript  
/* This is a comment  
This is another part of the same comment.*/  
```  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   여러 줄의 주석을 종결 합니다 "* /"입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Comment 문](../../javascript/reference/comment-statements-javascript.md)