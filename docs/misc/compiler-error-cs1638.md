---
title: "컴파일러 오류 CS1638 | Microsoft Docs"
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
  - "CS1638"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1638"
ms.assetid: 5279c060-5be3-4c29-80cc-21326d4cffdb
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1638
'identifier'는 예약된 식별자이므로 ISO 언어 버전 모드가 사용 중인 경우에는 사용할 수 없습니다.  
  
 **\/langversion** 컴파일러 스위치를 통해 ISO 언어 호환성 옵션이 지정된 경우 식별자에 이중 밑줄이 있으면 이 오류가 발생합니다. 이 오류를 방지하려면 이중 밑줄이 있는 식별자를 제거하거나 ISO\-1 언어 버전 옵션을 사용하지 마세요.  
  
## 예제  
 다음 샘플에서는 CS1638을 생성합니다.  
  
```  
// CS1638.cs // compile with: /langversion:ISO-1 class bad__identifer // CS1638 (double underscores are not ISO compliant) { } // Try this instead: //class GoodIdentifier //{ //} class CMain { public static void Main() { } }  
```  
  
## 참고 항목  
 [\/langversion \(Conformant Syntax\)](/dotnet/csharp/language-reference/compiler-options/langversion-compiler-option)