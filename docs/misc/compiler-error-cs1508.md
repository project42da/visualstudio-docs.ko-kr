---
title: "컴파일러 오류 CS1508 | Microsoft Docs"
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
  - "CS1508"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1508"
ms.assetid: 979bc615-58ce-49f8-ba73-e6cf57c56418
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1508
'identifier' 리소스 식별자가 이 어셈블리에서 이미 사용되었습니다.  
  
 컴파일할 때 동일한 식별자\(***identifier***\)가 둘 이상의 [\/resource](/dotnet/csharp/language-reference/compiler-options/resource-compiler-option) 또는 [\/linkresource](/dotnet/csharp/language-reference/compiler-options/linkresource-compiler-option) 컴파일러 옵션에 전달되었습니다.  
  
 예를 들어 다음 옵션은 CS1508을 생성합니다.  
  
```  
/resource:anyfile.bmp,DuplicatIdent /linkresource:a.bmp,DuplicatIdent  
```