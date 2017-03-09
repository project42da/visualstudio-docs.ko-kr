---
title: "컴파일러 오류 CS0273 | Microsoft Docs"
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
  - "CS0273"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0273"
ms.assetid: 851ad056-feee-48fd-834c-578a1a13e926
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0273
'property\_accessor' 접근자의 접근성 한정자는 'property' 속성 또는 인덱서보다 제한적이어야 합니다.  
  
 set\/get 접근자의 접근성 한정자는 'property\/indexer' 속성 또는 인덱서보다 제한적이어야 합니다.  
  
 이 오류는 해당 접근자의 액세스 한정자보다 제한이 적은 액세스 한정자를 사용하여 속성이나 인덱서를 선언할 때 발생합니다. 이 오류를 해결하려면 속성 또는 set 접근자에 적절한 액세스 한정자를 사용합니다. 자세한 내용은 [접근자 접근성](/dotnet/csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility)을 참조하세요.  
  
## 예제  
 이 샘플에는 내부 set 메서드가 있는 내부 속성이 포함되어 있습니다. 다음 샘플에서는 CS0273을 생성합니다.  
  
```  
// CS0273.cs // compile with: /target:library public class MyClass { internal int Property { get { return 0; } internal set {}   // CS0273 // try the following line instead // private set {} } }  
```