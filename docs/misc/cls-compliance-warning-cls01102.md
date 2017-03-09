---
title: "CLS 규격 경고 CLS01102 | Microsoft Docs"
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
  - "CLS01102"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01102"
ms.assetid: 49426c42-9d01-49ba-b061-ca0e8bd6782d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS01102
서명에 나타나는 모든 형식은 CLS 규격을 준수해야 합니다.  
  
 이벤트가 CLS 규격이면 CLS 비규격으로 표시되지 않은 경우 이벤트 액세스 함수에 사용된 모든 형식이 CLS 규격 형식이어야 합니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
```  
// CLS01102.cpp // compile with: /clr /LD // CLS01102 expected using namespace System; using namespace System::Reflection; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; // Test types [CLSCompliant(true)] public delegate void CompliantType([parameter:CLSCompliant(true)] int parameter); [CLSCompliant(false)] public delegate void NotCompliantType([parameter:CLSCompliant(false)] int parameter); public ref class One { public: event NotCompliantType^ MyEvent { public: void add(NotCompliantType^ Addparameter) {} void remove(NotCompliantType^ Removeparameter) {} void raise([parameter:CLSCompliant(false)] int parameter) {} } };  
```