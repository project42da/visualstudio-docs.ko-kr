---
title: "&#39;On Error&#39; 문은 &#39;Using&#39; 문 안에서 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc36013"
  - "bc36013"
helpviewer_keywords: 
  - "BC36013"
ms.assetid: 5b399bf9-6595-46e0-a808-378f6c28568b
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;On Error&#39; 문은 &#39;Using&#39; 문 안에서 사용할 수 없습니다.
`On Error` 문이 `Using` 문 내에 나타나지만 해당 컨텍스트에서 사용할 수 없습니다.  
  
 **오류 ID:** BC36013  
  
### 이 오류를 해결하려면  
  
-   `On Error` 문 대신 `Try…Catch` 블록과 같은 구조적 오류 처리를 사용합니다.  
  
## 참고 항목  
 [Visual Basic의 구조적 예외 처리 개요](http://msdn.microsoft.com/ko-kr/bb81af80-a735-4873-9711-6151a48e418a)   
 [구조적 및 비구조적 예외 처리 사용 시기 선택\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/e897d7ca-07e8-45dd-8a6d-a5b2a2fc9b9a)   
 [On Error Statement](/dotnet/visual-basic/language-reference/statements/on-error-statement)   
 [방법: Visual Basic에서 Try…Catch 블록을 사용하여 코드 테스트](http://msdn.microsoft.com/ko-kr/8368e205-ed73-4185-a247-af84fb4fafa9)   
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)