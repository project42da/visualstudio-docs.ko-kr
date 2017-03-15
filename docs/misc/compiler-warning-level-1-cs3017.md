---
title: "컴파일러 경고(수준 1) CS3017 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS3017"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3017"
ms.assetid: 8e56b2f0-9caf-4c9a-98c2-d3ad0b70e767
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3017
어셈블리의 CLSCompliant 특성과 다른 모듈의 CLSCompliant 특성을 지정할 수 없습니다.  
  
 이 경고는 어셈블리 CLSCompliant 특성이 모듈 CLSCompliant 특성과 충돌하는 경우 발생합니다. CLS 규격의 어셈블리에는 CLS 규격이 아닌 모듈을 포함할 수 없습니다. 이 경고를 해결하려면 어셈블리 및 모듈 CLSCompliant 특성이 모두 true 또는 모두 false인지 확인하고, 그렇지 않은 경우 특성 중 하나를 제거합니다. CLS 규격에 대한 자세한 내용은 [CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3) 및 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)을 참조하세요.  
  
## 예제  
 다음 예제는 CS3017을 생성합니다.  
  
```  
// CS3017.cs // compile with: /target:module using System; [module: CLSCompliant(true)] [assembly: CLSCompliant(false)]  // CS3017 // Try this line instead: // [assembly: CLSCompliant(true)] class C { static void Main() {} }  
```