---
title: "내부 오류 때문에 메모리 정보를 가져올 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrDiagnosticInfo_Memory"
ms.assetid: 1ba8f774-5858-438e-914e-99fddc9e5e7e
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 내부 오류 때문에 메모리 정보를 가져올 수 없습니다.
`My.Computer.Info` 개체의 메모리 정보 속성 중 하나에 대한 호출이 실패했습니다.  
  
### 이 오류를 해결하려면  
  
-   `My.Computer.Info` 개체의 메모리 정보 속성에 대한 호출 주위에 `Try...Catch` 블록을 추가합니다.  
  
## 참고 항목  
 [My.Computer.Info Object](/dotnet/visual-basic/language-reference/objects/my-computer-info-object)   
 [Visual Basic에서 예외 및 오류 처리](http://msdn.microsoft.com/ko-kr/3e351e73-cf23-40ab-8b60-05794160529e)   
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)