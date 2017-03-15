---
title: "&#39;Try&#39;는 짝이 되는 &#39;End Try&#39;로 끝나야 합니다. | Microsoft Docs"
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
  - "bc30384"
  - "vbc30384"
helpviewer_keywords: 
  - "BC30384"
ms.assetid: 898300b4-c091-4105-aeb0-9bd559ff6b6f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Try&#39;는 짝이 되는 &#39;End Try&#39;로 끝나야 합니다.
`Try`는 `Try` 블록을 시작하는 데 사용되므로 블록 시작 부분에서만 사용할 수 있으며 블록을 종료하는 짝이 되는 `End Try` 문이 필요합니다. 중복된 `Try`가 있거나, `Finally`를 사용하여 `Try` 블록을 종료하지 않았습니다.  
  
 **오류 ID:** BC30384  
  
### 이 오류를 해결하려면  
  
1.  잘못 사용된 `Try`를 찾아 제거하거나, 짝이 되는 `End Try`를 사용하여 블록을 종료합니다.  
  
## 참고 항목  
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Basic의 구조적 예외 처리 개요](http://msdn.microsoft.com/ko-kr/bb81af80-a735-4873-9711-6151a48e418a)