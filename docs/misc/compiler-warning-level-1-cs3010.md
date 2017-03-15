---
title: "컴파일러 경고(수준 1) CS3010 | Microsoft Docs"
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
  - "CS3010"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3010"
ms.assetid: d57bd750-df15-4e6a-9579-66de8b276b7e
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3010
'member': CLS 규격 인터페이스는 CLS 규격 멤버만 포함할 수 있습니다.  
  
 `[assembly:CLCSompliant(true)]`로 표시된 어셈블리에서 인터페이스에 `[CLCSompliant(false)]`로 표시된 멤버가 포함되어 있습니다. CLS\(공용 언어 사양\) 규격 특성 중 하나를 제거합니다. CLS 규격에 대한 자세한 내용은 [\<PAVE OVER\> CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3) 및 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)를 참조하세요.  
  
## 예제  
 다음 예제에서는 CS3010을 생성합니다.  
  
```  
// CS3010.cs using System; [assembly:CLSCompliant(true)] public interface I { [CLSCompliant(false)] int M();   // CS3010 } public class C : I { public int M() { return 1; } public static void Main() { } }  
```