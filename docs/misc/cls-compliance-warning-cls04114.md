---
title: "CLS 규격 경고 CLS04114 | Microsoft Docs"
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
  - "CLS04114"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS04114"
ms.assetid: 84285fbb-ecd1-46e6-9bdb-dc44db40dcc0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS04114
특성은 'System::Attribute' 형식 또는 여기에서 상속된 형식이어야 합니다.  
  
 CLS 규격을 준수하기 위해 사용자 지정 특성은 System::Attribute에서 상속해야 합니다.  System::Attribute에서 상속되지 않은 특성이 대리자에 적용되었습니다.  
  
 CLS\(공용 언어 하위 집합\) 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 선언\(MSIL 어셈블리 언어 사용\)에서는 CLS04100을 발생시키는 원인을 보여 줍니다.  
  
```  
.class public auto ansi MyAttribute extends [mscorlib]System.Object  
```  
  
 그런 다음 특성을 사용하는 대리자를 보여 줍니다.  
  
```  
.custom instance void MyAttribute::.ctor(int32) = ( 01 00 01 00 00 00 00 00 )  
```  
  
 특성이 System::Attribute에서 파생되도록 하면 경고가 해결됩니다.  
  
```  
.class public auto ansi MyAttribute extends [mscorlib]System.Attribute  
```