---
title: "CLS 규격 경고 CLS01011 | Microsoft Docs"
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
  - "CLS01011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01011"
ms.assetid: e4141e15-14fd-491c-9639-f3f3a47d7865
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS01011
상속된 메서드를 재정의하는 경우 접근성이 변경되지 않습니다.  
  
 메서드를 재정의하면 재정의하는 메서드와 동일한 표시 유형이 있어야 합니다.  패밀리 또는 어셈블리 접근성을 갖는 다른 어셈블리에서 상속된 메서드를 재정의하는 경우를 제외하고는 상속된 메서드를 재정의할 때 접근성이 변경되어서는 안 됩니다. 이 경우 재정의는 패밀리 접근성을 가져야 합니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 샘플에서는 CLS01011을 생성합니다.  
  
```  
// CLS01011.cpp // compile with: /clr /LD // CLS01011 expected using namespace System; using namespace System::Reflection; using namespace cli::language; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; public ref class BaseType { public protected: virtual void BaseTypeMethod() {} }; public ref class One : public BaseType { public: void BaseTypeMethod() {}   // CLS01011 // OK // public protected: //    void BaseTypeMethod() {} };  
```