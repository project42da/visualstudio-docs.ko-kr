---
title: "CLS 규격 경고 CLS04101 | Microsoft Docs"
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
  - "CLS04101"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS04101"
ms.assetid: 5ad21eb4-0c6e-4629-bc4a-af274f8a8d90
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS04101
특성은 'System::Attribute' 형식 또는 여기에서 상속된 형식이어야 합니다.  
  
 생성자 매개 변수에 적용된 모든 특성은 'System::Attribute' 형식 또는 여기에서 상속된 형식이어야 합니다.  
  
 CLS\(공용 언어 하위 집합\) 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 선언\(MSIL 어셈블리 언어 사용\)에서는 CLS04101을 발생시키는 원인을 보여 줍니다.  
  
```  
.class public auto ansi MyAttribute extends [mscorlib]System.Object { .method public specialname rtspecialname instance void  .ctor() cil managed  
```  
  
 특성이 System::Attribute에서 파생되도록 하면 경고가 해결됩니다.  
  
```  
.class public auto ansi MyAttribute extends [mscorlib]System.Object { .method public specialname rtspecialname instance void  .ctor() cil managed  
```