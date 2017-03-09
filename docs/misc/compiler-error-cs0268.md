---
title: "컴파일러 오류 CS0268 | Microsoft Docs"
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
  - "CS0268"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0268"
ms.assetid: a4faca71-8b4a-4f22-a89e-59d92ced48cb
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0268
가져온 'type' 형식이 잘못되었습니다. 순환 기본 클래스 종속성을 포함합니다.  
  
 이 오류는 다른 언어에서 가져온 형식에 순환 기본 클래스 종속성이 있는 경우에 발생합니다. C\# 프로그램에서는 이러한 형식을 사용할 수 없습니다. 이 오류를 해결하려면 참조된 모든 어셈블리 또는 모듈에서 다른 언어에서 가져온 형식을 검사합니다.