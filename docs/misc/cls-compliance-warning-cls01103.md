---
title: "CLS 규격 경고 CLS01103 | Microsoft Docs"
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
  - "CLS01103"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01103"
ms.assetid: 0d0aebaa-441a-4dc0-9745-8de3a551204b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS01103
서명에 나타나는 모든 형식은 CLS 규격을 준수해야 합니다.  
  
 형식이 CLS 규격이면 CLS 비규격으로 표시되지 않은 경우 모든 필드가 CLS 규격 형식이어야 합니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
```  
// CLS01103.cpp // compile with: /clr /LD // CLS01103 expected using namespace System; using namespace System::Reflection; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; [CLSCompliant(false)] public ref class NotCompliantType {}; // Ref class public ref class One { public: NotCompliantType^ Member1;   // CLS01103 static NotCompliantType^ Member2;   // CLS01103 };  
```