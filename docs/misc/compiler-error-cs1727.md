---
title: "컴파일러 오류 CS1727 | Microsoft Docs"
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
  - "CS1727"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1727"
ms.assetid: 66478a58-e0f6-4886-b940-5473ad485a01
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1727
권한 부여 없이 자동으로 오류 보고서를 보낼 수 없습니다. 오류 보고서를 보낼 권한을 부여하려면 ''을\(를\) 방문하세요.  
  
 오류 텍스트에 나열된 웹 사이트는 [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)] 명령줄 도구에 대해 자동 오류 보고를 사용하도록 설정하는 방법을 설명합니다.  
  
## 예제  
 다음 샘플에서는 CS1727을 생성합니다.  
  
```  
// CS1727.cs // compile with: /errorreport:send // CS1727 expected class Test { static void Main(){} }  
```  
  
## 참고 항목  
 [\/errorreport \(Set Error Reporting Behavior\)](/dotnet/csharp/language-reference/compiler-options/errorreport-compiler-option)