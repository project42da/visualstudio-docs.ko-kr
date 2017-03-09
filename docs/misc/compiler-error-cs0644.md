---
title: "컴파일러 오류 CS0644 | Microsoft Docs"
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
  - "CS0644"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0644"
ms.assetid: 835f3ee2-f897-4ba2-ad13-af629a9ab7fe
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0644
'class1'은 'class2' 특수 클래스에서 파생될 수 없습니다.  
  
 클래스는 다음 기본 클래스 중 하나에서 명시적으로 상속할 수 없습니다.  
  
-   **System.Enum**  
  
-   **System.ValueType**  
  
-   **System.Delegate**  
  
-   **System.Array**  
  
 이러한 클래스는 컴파일러에 의해 암시적 기본 클래스로 사용됩니다. 예를 들어 **System.ValueType**은 구조체의 암시적 기본 클래스입니다.  
  
 다음 샘플에서는 CS0644를 생성합니다.  
  
```  
// CS0644.cs class MyClass : System.ValueType   // CS0644 { }  
```