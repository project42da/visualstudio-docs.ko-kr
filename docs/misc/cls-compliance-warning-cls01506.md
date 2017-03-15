---
title: "CLS 규격 경고 CLS01506 | Microsoft Docs"
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
  - "CLS01506"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01506"
ms.assetid: 030f1b81-1159-4057-9fee-8721a419a5d6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS01506
vararg 제약 조건이 CLS의 일부가 아닙니다.  
  
 vararg 제약 조건이 CLS\(Common Language Subset\)의 일부가 아닙니다.  CLS에서는 관리되는 표준 호출 규칙만 지원합니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 함수 선언\(MSIL 어셈블리 언어 사용\)에서는 CLS01506을 발생시키는 원인을 보여 줍니다.  
  
```  
.method public instance vararg void  Method1() cil managed  
```  
  
 **vararg** 키워드를 제거하여 이 경고를 해결할 수 있습니다.  
  
```  
.method public instance void  Method1() cil managed  
```