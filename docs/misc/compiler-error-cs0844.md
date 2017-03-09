---
title: "컴파일러 오류 CS0844 | Microsoft Docs"
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
  - "CS0844"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0844"
ms.assetid: ccf74e01-292a-42d0-897c-8add7aee2118
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0844
'name' 지역 변수는 선언되지 않으면 사용할 수 없습니다. 지역 변수를 선언하면 'name' 필드가 숨겨집니다.  
  
 식별자는 지정된 블록에서 하나의 의미만 가질 수 있습니다. 클래스 필드와 이름이 같은 지역 변수는 식별자에 대한 두 번째 의미를 도입하여 필드를 숨길 수 있습니다. 따라서 메서드에서 클래스 필드를 참조한 다음 같은 이름으로 지역 변수를 선언하는 경우 컴파일러에서 오류가 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   `this.num`를 사용하여 클래스 필드를 참조합니다.  
  
-   지역 변수에 클래스 필드와 다른 이름을 지정합니다.  
  
## 예제  
 다음 코드에서는 CS0844를 생성합니다.  
  
```  
class Test { int num; public void TestMethod() { num = 5; // CS0844 int num = 6;        } public static int Main() { return 1; } }  
```