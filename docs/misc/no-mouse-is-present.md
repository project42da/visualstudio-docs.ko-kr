---
title: "마우스가 없습니다. | Microsoft Docs"
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
  - "vbrMouse_NoMouseIsPresent"
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 마우스가 없습니다.
`My.Computer.Mouse` 개체의 속성 중 하나를 호출했지만 컴퓨터에 마우스 또는 마우스 포트가 설치되어 있지 않습니다.  
  
### 이 오류를 해결하려면  
  
-   `My.Computer.Mouse` 개체의 속성을 호출하는 주변에 `Try...Catch` 블록을 추가합니다.  
  
     — 또는 —  
  
-   컴퓨터에 마우스를 설치합니다.  
  
## 참고 항목  
 [My.Computer.Mouse Object](/dotnet/visual-basic/language-reference/objects/my-computer-mouse-object)   
 [Visual Basic에서 예외 및 오류 처리](http://msdn.microsoft.com/ko-kr/3e351e73-cf23-40ab-8b60-05794160529e)   
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)