---
title: "컴파일러 경고(수준 1) CS3018 | Microsoft Docs"
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
  - "CS3018"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3018"
ms.assetid: 35d2f4bd-10c3-4e9f-8e02-389ab84db2cd
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3018
'type'은 CLS 규격이 아닌 'type' 형식의 멤버이므로 CLS 규격으로 표시할 수 없습니다.  
  
 이 경고는 CLSCompliant 특성이 `true`으로 설정된 중첩된 클래스가 CLSCompliant 특성을 `false`으로 설정하여 선언된 클래스의 멤버로 선언된 경우에 발생합니다. 중첩된 클래스는 CLS 규격이 아닌 외부 클래스의 멤버인 경우 CLS 규격일 수 없으므로 이는 허용되지 않습니다. 이 경고를 해결하려면 중첩된 클래스에서 CLSCompliant 특성을 제거하거나`true`에서 `false`으로 변경합니다. CLS 규격에 대한 자세한 내용은 [CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3) 및 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS3018을 생성합니다.  
  
```  
// CS3018.cs // compile with: /target:library using System; [assembly: CLSCompliant(true)] [CLSCompliant(false)] public class Outer { [CLSCompliant(true)]   // CS3018 public class Nested {} // OK public class Nested2 {} [CLSCompliant(false)] public class Nested3 {} }  
```