---
title: "컴파일러 오류 CS0227 | Microsoft Docs"
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
  - "CS0227"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0227"
ms.assetid: b595a1c9-8204-4ff7-a1d0-258b0b1d6ff7
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0227
안전하지 않은 코드는 \/unsafe를 사용하여 컴파일하는 경우에만 나타날 수 있습니다.  
  
 소스 코드에 [안전하지 않은](/dotnet/csharp/language-reference/keywords/unsafe) 키워드가 있는 경우 [\/unsafe](/dotnet/csharp/language-reference/compiler-options/unsafe-compiler-option) 컴파일러 옵션도 사용해야 합니다. 자세한 내용은 [안전하지 않은 코드 및 포인터](/dotnet/csharp/programming-guide/unsafe-code-pointers/index)을 참조하세요.  
  
 [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)]에서 안전하지 않은 옵션을 설정하려면 주 메뉴에서 **프로젝트**를 클릭하고 **빌드** 창을 선택한 다음 “안전하지 않은 코드 허용"이라는 상자를 선택합니다.  
  
 다음 샘플에서는 **\/unsafe** 없이 컴파일한 경우 CS0227을 생성합니다.  
  
```  
// CS0227.cs public class MyClass { unsafe public static void Main()   // CS0227 { } }  
```  
  
## 참고 항목  
 [C\# Compiler Errors](/dotnet/csharp/language-reference/compiler-messages/index)