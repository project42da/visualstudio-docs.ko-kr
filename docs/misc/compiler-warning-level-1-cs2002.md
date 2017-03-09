---
title: "컴파일러 경고(수준 1) CS2002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS2002"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2002"
ms.assetid: 4acd054e-d3fe-4be6-a660-53a0a5e8c6a4
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS2002
'file' 소스 파일을 여러 번 지정했습니다.  
  
 소스 파일 이름이 두 번 이상 컴파일러에 전달되었습니다. 출력 파일을 빌드하기 위해 컴파일러에 파일을 한 번만 지정할 수 있습니다.  
  
 이 경고는 [\/nowarn](/dotnet/csharp/language-reference/compiler-options/nowarn-compiler-option) 옵션으로 표시하지 않을 수 없습니다.  
  
 다음 샘플에서는 CS2002를 생성합니다.  
  
```  
// CS2002.cs // compile with: CS2002.cs public class A { public static void Main(){} }  
```  
  
 오류를 생성하려면 다음 명령줄을 사용하여 예제를 컴파일합니다.  
  
```  
csc CS2002.cs CS2002.cs  
```