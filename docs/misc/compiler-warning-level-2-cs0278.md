---
title: "컴파일러 경고(수준 2) CS0278 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0278"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0278"
ms.assetid: 5418cbbe-bcec-4379-a6f6-410987beb96a
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0278
'type'은 'pattern name' 패턴을 구현하지 않습니다. 'method name'이 'method name'에서 모호합니다.  
  
 C\#에는 `foreach` 및 `using`과 같이 정의된 패턴을 사용하는 문이 여러 개 있습니다. 예를 들어 `foreach`는 "열거 가능" 패턴을 구현하는 컬렉션 클래스를 사용합니다.  
  
 컴파일러에서 모호성으로 인해 일치시킬 수 없는 경우 CS0278이 발생할 수 있습니다. 예를 들어 "열거 가능" 패턴을 사용하려면 `MoveNext` 메서드가 필요하며 코드에 `MoveNext`라는 메서드가 2개 포함될 수 있습니다. 컴파일러는 사용할 인터페이스를 찾으려고 하지만 모호성의 원인을 확인하여 해결하는 것이 좋습니다.  
  
 자세한 내용은 [방법: foreach를 사용하여 컬렉션 클래스 액세스](../Topic/How%20to:%20Access%20a%20Collection%20Class%20with%20foreach%20\(C%23%20Programming%20Guide\).md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0278을 생성합니다.  
  
```  
// CS0278.cs using System.Collections.Generic; public class myTest { public static void TestForeach<W>(W w) where W: IEnumerable<int>, IEnumerable<string> { foreach (int i in w) {}   // CS0278 } }  
```