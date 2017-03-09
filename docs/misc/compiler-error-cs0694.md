---
title: "컴파일러 오류 CS0694 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0694"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0694"
ms.assetid: 048615e4-4599-4726-b5db-55322ccc936f
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0694
'identifier' 형식 매개 변수의 이름이 포함하는 형식 또는 메서드 이름과 같습니다.  
  
 형식 매개 변수의 이름은 형식 매개 변수를 포함하는 형식 또는 메서드 이름과 동일할 수 없으므로 형식 매개 변수에 다른 이름을 사용해야 합니다.  
  
## 예제  
 다음 샘플에서는 CS0694를 생성합니다.  
  
```  
// CS0694.cs // compile with: /target:library class C<C> {}   // CS0694  
```  
  
## 예제  
 제네릭 클래스와 관련된 위의 사례 외에도 이 오류는 메서드에서 발생할 수 있습니다.  
  
```  
// CS0694_2.cs // compile with: /target:library class A { public void F<F>(F arg);   // CS0694 }  
```