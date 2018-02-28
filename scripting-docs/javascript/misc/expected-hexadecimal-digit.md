---
title: "예상된 16 진수 | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT1023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 67a86df7-49f9-43cb-99c6-99b1a427827a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9e29131c4ecf4f476a30da94ec67676d6bea347
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="expected-hexadecimal-digit"></a>16진수가 필요합니다.
잘못 된 유니코드 이스케이프 시퀀스를 만들었습니다. 유니코드 이스케이프 시퀀스 \u, 다음에 정확 하 게 4 자리 16 진수 (더 이상 및 더 작은)로 시작 합니다. 유니코드 16 진수는 숫자 0-9, A-F 대 문자가 소문자 문자 a-f를 포함할 수 있습니다. 다음 예제에서는 올바른 형식의 유니코드 이스케이프 시퀀스를 보여 줍니다.  
  
```JavaScript  
z = "\u1A5F";  
```  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   유니코드 16 진수 숫자 \u 시작할 0-9, A-f 소문자 문자 a-f; 대 문자가 숫자만 포함 해야 네 자리 숫자로 그룹화 됩니다.  
  
    > [!NOTE]
    >  문자열에서 리터럴 텍스트 \u를 사용 하 여 다음 두 개의 백슬래시-사용 하려는 경우 (\\\u)-첫 번째 백슬래시를 이스케이프 하 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../javascript/data-types-javascript.md)