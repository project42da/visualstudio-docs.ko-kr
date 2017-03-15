---
title: "컴파일러 오류 CS1541 | Microsoft Docs"
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
  - "CS1541"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1541"
ms.assetid: db3350fe-6432-4617-8b4a-64bc6cdf83f8
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1541
잘못된 참조 옵션: 'symbol' \-\- 디렉터리를 참조할 수 없습니다.  
  
 컴파일러가 특정 파일이 아닌 디렉터리를 지정하려는 시도를 검색했습니다. 예를 들어 [\/reference](/dotnet/csharp/language-reference/compiler-options/reference-compiler-option) 컴파일러 옵션을 사용하는 경우 파일을 지정해야 하며 디렉터리를 지정할 수 없습니다.  
  
 예를 들어 컴파일러에 `/reference:c:\`를 전달하면 CS1541이 생성됩니다.