---
title: "컴파일러 오류 CS1706 | Microsoft Docs"
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
  - "CS1706"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1706"
ms.assetid: 8c589a49-3959-422e-ac18-65a2eaae3da0
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1706
식에는 무명 메서드 또는 람다 식을 사용할 수 없습니다.  
  
 식 안에 무명 메서드를 삽입할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  식 안에 정규 `delegate`를 사용합니다.  
  
## 예제  
 다음 예제는 CS1706을 생성합니다.  
  
```  
// CS1706.cs using System; delegate void MyDelegate(); class MyAttribute : Attribute { public MyAttribute(MyDelegate d) { } } // Anonymous Method in Attribute declaration is not allowed. [MyAttribute(delegate{/* anonymous Method in Attribute declaration */})]  // CS1706 class Program { }  
```