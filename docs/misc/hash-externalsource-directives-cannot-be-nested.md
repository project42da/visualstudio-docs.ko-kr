---
title: "&#39;#ExternalSource&#39; 지시문은 중첩될 수 없습니다. | Microsoft Docs"
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
  - "bc30580"
  - "vbc30580"
helpviewer_keywords: 
  - "BC30580"
ms.assetid: 56c6ef4b-28b1-4a62-8afa-d83a7742b507
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;#ExternalSource&#39; 지시문은 중첩될 수 없습니다.
`#ExternalSource` 지시문을 다른 `#ExternalSource` 블록에 배치하려고 했습니다.`#ExternalSource` 지시문은 코드 외부를 참조하므로 컴파일러에서 해당 코드 내에서 예외가 발생하는 시기를 정확하게 보고할 수 있습니다.  
  
 `#ExternalSource` 블록은 다른 `#ExternalSource` 블록 내에 중첩할 수 없습니다.  
  
 **오류 ID:** BC30580  
  
### 이 오류를 해결하려면  
  
-   내부 `#ExternalSource` 지시문을 바깥쪽 `#ExternalSource` 블록 밖으로 이동합니다.  
  
## 참고 항목  
 [\#ExternalSource Directive](/dotnet/visual-basic/language-reference/directives/externalsource-directive)   
 [NOTINBUILD 조건부 컴파일\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/ad1e35e0-935e-4a35-a2ae-738bcf2a9240)