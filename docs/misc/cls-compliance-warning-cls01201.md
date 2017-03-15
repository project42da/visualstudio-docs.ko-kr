---
title: "CLS 규격 경고 CLS01201 | Microsoft Docs"
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
  - "CLS01201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01201"
ms.assetid: 8c3e6ce4-8ea5-487a-bbed-56a36eceb024
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS01201
형식과 멤버의 표시 유형 및 접근성은 해당 멤버가 표시되고 액세스 가능한 경우 모든 멤버의 시그니처에 있는 해당 형식이 표시되고 액세스 가능해야 합니다. 예를 들어 어셈블리 외부에 표시되는 공용 생성자는 어셈블리 내부에서만 표시되는 형식의 인수를 가질 수 없습니다.  
  
 생성자 서명의 형식은 생성자의 서명보다 접근성이 크거나 같아야 합니다.  예를 들어 어셈블리 외부에 표시되는 공용 생성자는 어셈블리 내부에서만 표시되는 형식의 인수를 가질 수 없습니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 샘플에서는 CLS01201을 생성합니다.  
  
```  
/* CLS01201.cpp */ // compile with: /clr /LD // CLS01201 expected using namespace System; using namespace System::Reflection; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; private ref class AssemblyLevelType {}; public ref class One { public: One(AssemblyLevelType^ parameter) {}   // not cls compliant }; private value class Two { public: Two(AssemblyLevelType^ parameter) {}   // OK };  
```