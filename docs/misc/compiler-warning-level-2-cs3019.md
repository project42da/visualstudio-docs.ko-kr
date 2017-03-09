---
title: "컴파일러 경고(수준 2) CS3019 | Microsoft Docs"
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
  - "CS3019"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3019"
ms.assetid: b41117cf-8956-4989-93fd-9903812e2d2f
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS3019
'type'은 이 어셈블리 외부에 노출되지 않으므로 CLS 규격 검사를 수행하지 않습니다.  
  
 이 경고는 <xref:System.CLSCompliantAttribute> 특성이 있는 형식이나 멤버가 다른 어셈블리에서 표시되지 않을 때 발생합니다. 이 오류를 해결하려면 다른 어셈블리에서 표시되지 않는 모든 클래스나 멤버에서 해당 특성을 제거하거나 해당 형식 또는 멤버가 표시되도록 설정합니다. CLS 규격에 대한 자세한 내용은 [\<PAVE OVER\> CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS3019를 생성합니다.  
  
```  
// CS3019.cs // compile with: /W:2 using System; [assembly: CLSCompliant(true)] // To fix the error, remove the next line [CLSCompliant(true)]  // CS3019 class C { [CLSCompliant(false)]  // CS3019 void Foo() { } static void Main() { } }  
```  
  
## 참고 항목  
 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)