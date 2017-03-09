---
title: "컴파일러 오류 CS0138 | Microsoft Docs"
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
  - "CS0138"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0138"
ms.assetid: 970545f8-5ee5-428e-921a-3aa29f68d16d
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0138
using 네임스페이스 지시문은 네임스페이스에만 적용할 수 있습니다. 'type'은 네임스페이스가 아니라 형식입니다.  
  
 [using](/dotnet/csharp/language-reference/keywords/using) 지시문은 네임스페이스 이름만 매개 변수로 사용할 수 있습니다. 자세한 내용은 [네임스페이스](/dotnet/csharp/programming-guide/namespaces/index)을 참조하세요.  
  
 다음 샘플에서는 CS0138을 생성합니다.  
  
```  
// CS0138.cs using System.Object;   // CS0138  
```