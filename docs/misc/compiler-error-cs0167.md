---
title: "컴파일러 오류 CS0167 | Microsoft Docs"
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
  - "CS0167"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0167"
ms.assetid: e6901b40-11a0-422c-9ea3-3b25c0ad7791
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0167
'delegate' 대리자에 Invoke 메서드가 없습니다.  
  
 다른 컴파일러로 만든 관리되는 프로그램\(.NET Framework 공용 언어 런타임을 사용하는 프로그램\)을 가져와서 사용했습니다. 해당 컴파일러에서 잘못된 형식의 [대리자](/dotnet/csharp/language-reference/keywords/delegate)를 허용했습니다. 따라서 `Invoke` 메서드를 사용할 수 없습니다. 자세한 내용은 [대리자](/dotnet/csharp/programming-guide/delegates/index)을 참조하세요.