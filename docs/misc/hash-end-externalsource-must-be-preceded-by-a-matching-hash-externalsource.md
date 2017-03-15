---
title: "&#39;#End ExternalSource&#39;는 짝이 되는 &#39;#ExternalSource&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "bc30578"
  - "vbc30578"
helpviewer_keywords: 
  - "BC30578"
ms.assetid: f011673d-eced-46a7-a08e-d54d86c8a76b
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;#End ExternalSource&#39;는 짝이 되는 &#39;#ExternalSource&#39; 뒤에 와야 합니다.
`#ExternalSource` 지시문은 코드 외부를 참조하므로 컴파일러에서 해당 코드 내에서 예외가 발생하는 시기를 정확하게 보고할 수 있습니다.`#ExternalSource` 블록은 `#ExternalSource`로 시작하고 `#End ExternalSource`로 끝나야 합니다.  
  
 **오류 ID:** BC30578  
  
### 이 오류를 해결하려면  
  
1.  `#ExternalSource`를 코드의 적절한 위치에 추가합니다.  
  
2.  필요하지 않으면 `#End ExternalSource`를 제거합니다.  
  
## 참고 항목  
 [\#ExternalSource Directive](/dotnet/visual-basic/language-reference/directives/externalsource-directive)   
 [NOTINBUILD 조건부 컴파일\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/ad1e35e0-935e-4a35-a2ae-738bcf2a9240)