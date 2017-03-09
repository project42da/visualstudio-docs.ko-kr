---
title: "CLS 규격 경고 CLS00911 | Microsoft Docs"
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
  - "CLS00911"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS00911"
ms.assetid: d1a4721a-a3a6-4de0-bc14-a0b3c5e6dd78
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS00911
열거형의 리터럴 정적 필드는 그 자체가 열거형 형식을 갖습니다.  
  
 열거형의 리터럴 정적 필드 그 자체가 열거형 형식인지 확인합니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 선언\(MSIL 어셈블리 언어 사용\)에서는 CLS00911을 발생시키는 원인을 보여 줍니다.  
  
```  
.assembly extern legacy library mscorlib {} .assembly legacy library Out {} .namespace Test { .class public auto ansi sealed MyEnum1 extends [mscorlib]System.Enum { .field public specialname rtspecialname int32 value__ .field public static literal uint8 One = uint8(0x1) } // end of class MyEnum1 }  
```  
  
 열거형 필드를 열거형 형식으로 설정하면 이 경고를 해결할 수 있습니다.  
  
```  
.assembly extern legacy library mscorlib {} .assembly legacy library Out {} .namespace Test { .class public auto ansi sealed MyEnum1 extends [mscorlib]System.Enum { .field public specialname rtspecialname int32 value__ .field public static literal valuetype Test.MyEnum1 One = uint8(0x1) } // end of class MyEnum1 }  
```