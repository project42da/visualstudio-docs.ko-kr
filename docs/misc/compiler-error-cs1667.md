---
title: "컴파일러 오류 CS1667 | Microsoft Docs"
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
  - "CS1667"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1667"
ms.assetid: 59f64828-58bc-487c-862a-75537e21d4ea
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1667
'attribute' 특성은 속성 또는 이벤트 접근자에 사용할 수 없습니다. 'declaration type' 선언에만 사용할 수 있습니다.  
  
 특성이 속성 또는 이벤트 자체에 있어야 할 때 속성 또는 이벤트 접근자에서 특성을 사용하는 경우 이 오류가 발생합니다. 이 오류는 <xref:System.CLSCompliantAttribute>, <xref:System.Diagnostics.ConditionalAttribute> 및 <xref:System.ObsoleteAttribute> 특성에서 발생할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 CS1670을 생성합니다.  
  
```  
// CS1667.cs using System; public class C { private int i; //Try this instead: //[Obsolete] public int ObsoleteProperty { [Obsolete]  // CS1667 get { return i; } set { i = value; } } public static void Main() { } }  
```