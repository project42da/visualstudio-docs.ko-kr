---
title: "CLS 규격 경고 CLS01703 | Microsoft Docs"
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
  - "CLS01703"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01703"
ms.assetid: b03ae369-3c4b-4080-9b78-4c9bfba581a3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS01703
관리되지 않는 포인터 형식은 CLS 규격이 아닙니다.  
  
 CLS 규격 필드에는 네이티브 포인터 선언이 포함될 수 없습니다.  
  
 CLS\(공용 언어 하위 집합\) 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 샘플에서는 CLS01703을 생성합니다.  
  
```  
// CLS01703.cpp // compile with: /clr /LD // CLS01703 expected using namespace System; using namespace System::Reflection; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; public ref class MyClass { public: int* Parameter;   // CLS01703 };  
```