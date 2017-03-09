---
title: "컴파일러 경고(수준 1) CS3014 | Microsoft Docs"
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
  - "CS3014"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3014"
ms.assetid: 6825b42f-1820-4265-b8d8-9b3387d7c130
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3014
어셈블리에 CLSCompliant 특성이 없으므로 'member'에 CLSCompliant 특성이 필요하지 않습니다.  
  
 CLS\(공용 언어 사양\) 규격이 지정되지 않은 소스 코드 파일에서 파일의 구문이 CLS 규격으로 표시되었습니다. 이것은 허용되지 않습니다. 이 경고를 해결하려면 어셈블리 수준의 CLS 규격 특성을 파일에 추가합니다\(다음 예제에서 어셈블리 수준 특성을 포함하는 줄의 주석 처리 제거\). CLS 규격에 대한 자세한 내용은 [CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3) 및 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)를 참조하세요.  
  
## 예제  
 다음 예제에서는 CS3014를 생성합니다.  
  
```  
// CS3014.cs using System; // [assembly:CLSCompliant(true)] public class I { [CLSCompliant(true)]   // CS3014 public void M() { } public static void Main() { } }  
```