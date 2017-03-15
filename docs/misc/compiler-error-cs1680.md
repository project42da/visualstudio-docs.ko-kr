---
title: "컴파일러 오류 CS1680 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1680"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1680"
ms.assetid: 973da155-e6fa-4de8-94fd-7838f839a81f
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1680
잘못된 참조 별칭 옵션: 'alias\='. 파일 이름이 없습니다.  
  
 이 오류는 올바른 파일 이름을 지정하지 않고 **\/reference** 컴파일러 옵션과 함께 `alias` 기능을 사용하는 경우에 발생합니다.  
  
 다음 샘플에서는 CS1680을 생성합니다.  
  
```  
// CS1680.cs // compile with: /reference:alias= // CS1680 expected // To resolve, specify the name of a file with an assembly manifest class MyClass {}  
  
```