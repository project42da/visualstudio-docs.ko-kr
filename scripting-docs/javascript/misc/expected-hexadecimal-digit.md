---
title: "16진수가 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.WebClient.Help.SCRIPT1023"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 67a86df7-49f9-43cb-99c6-99b1a427827a
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# 16진수가 필요합니다.
잘못된 유니코드 이스케이프 시퀀스를 만들었습니다.  유니코드 이스케이프 시퀀스는 \\u로 시작하여 정확히 4 자릿수로 구성됩니다.  유니코드 16진수 자릿수는 0\-9 숫자, A\-F 대문자 및 a\-f 소문자만 포함할 수 있습니다.  다음 예제에서는 올바른 형식의 유니코드 이스케이프 시퀀스를 보여 줍니다.  
  
```javascript  
z = "\u1A5F";  
```  
  
### 이 오류를 해결하려면  
  
-   해당 유니코드 16진수 숫자가 \\u로 시작하고, 0\-9 숫자, A\-F 대문자 및 a\-f 소문자만 포함하는지 그리고 4 자릿수로 구성되었는지 확인하세요.  
  
    > [!NOTE]
    >  문자열에 리터럴 텍스트 \\u를 사용하려는 경우 두 개의 백슬래시 문자\(\\\\u\)를 사용하여 첫 번째 백슬래시 문자를 이스케이프 처리해야 합니다.  
  
## 참고 항목  
 [데이터 형식](../../javascript/data-types-javascript.md)