---
title: "컴파일러 오류 CS1110 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1110"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1110"
ms.assetid: 5b571a76-1891-4f33-b23d-7c4cc654a05f
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1110
System.Core.dll에 대한 참조 없이 메서드 선언의 첫 번째 매개 변수에서 'this' 한정자를 사용할 수 없습니다. System.Core.dll에 대한 참조를 추가하거나 메서드 선언에서 'this' 한정자를 제거합니다.  
  
 확장 메서드는 .NET Framework 3.5 이상 버전에서 지원됩니다. 확장 메서드는 특성으로 메서드를 표시하는 메타데이터를 생성합니다. 특성 클래스는 system.core.dll에 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  메시지의 내용대로 System.Core.dll에 대한 참조를 추가하거나 메서드 선언에서 `this` 한정자를 제거합니다.  
  
## 예제  
 다음 예제는 파일이 System.Core.dll에 대한 참조를 사용하여 컴파일되지 않은 경우 CS1110을 생성합니다.  
  
```  
// cs1110.cs // CS1110 // Compile with: /target:library public static class Extensions { public static bool Test(this bool b) { return b; } }  
```  
  
## 참고 항목  
 [확장 메서드](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)