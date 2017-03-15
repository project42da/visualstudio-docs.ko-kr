---
title: "레코드 개수가 잘못되었습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID63"
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 레코드 개수가 잘못되었습니다.
`a FileGet`, `FilePut`, `FileGetObject` 또는 `FilePutObject` 문의 레코드 번호가 0보다 작거나 같습니다.  
  
### 이 오류를 해결하려면  
  
1.  레코드 번호를 생성하는 데 사용한 계산을 확인합니다. 레코드 번호를 계산하는 데 사용한 변수 또는 레코드 번호가 포함된 변수의 철자를 확인합니다. 모듈에서 `Option Explicit On`을 사용하지 않으면 철자가 잘못된 변수 이름이 암시적으로 선언되고 0으로 초기화됩니다.  
  
## 참고 항목  
 [Option Explicit Statement](/dotnet/visual-basic/language-reference/statements/option-explicit-statement)