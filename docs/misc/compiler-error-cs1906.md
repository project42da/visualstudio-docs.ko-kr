---
title: "컴파일러 오류 CS1906 | Microsoft Docs"
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
  - "CS1906"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1906"
ms.assetid: 1a6abf5c-f673-4256-93ac-313dce50acc0
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1906
'option' 옵션이 잘못되었습니다. 리소스 표시 유형은 'public' 또는 'private'이어야 합니다.  
  
 이 오류는 잘못된 [\/resource\(출력 파일에 리소스 파일 포함\)](/dotnet/csharp/language-reference/compiler-options/resource-compiler-option) 또는 [\/linkresource\(.NET Framework 리소스에 대한 링크\)](/dotnet/csharp/language-reference/compiler-options/linkresource-compiler-option) 명령줄 옵션을 나타냅니다.**\/resource** 또는 **\/linkresource** 명령줄 옵션의 구문을 검사하고 사용된 접근성 한정자가 **public** 또는 `private`인지 확인합니다.