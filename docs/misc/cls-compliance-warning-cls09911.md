---
title: "CLS 규격 경고 CLS09911 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CLS09911"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS09911"
ms.assetid: 8cc0b0c0-a823-4392-9bf9-4d12242ef451
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS09911
제네릭 형식은 CLS 규격이 아닙니다.  
  
 CLS 규격 형식도 제네릭 형식이 될 수 없습니다.  Visual C\+\+의 제네릭에 대한 자세한 내용은 [C\+\+의 제네릭에 대한 지원](/visual-cpp/windows/generics-cpp-component-extensions)을 참조하세요.  
  
 CLS\(공용 언어 하위 집합\) 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 샘플에서는 CLS09911을 생성합니다.  
  
```  
// CLS09911.cpp // compile with: /clr /LD using namespace System; using namespace System::Reflection; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; generic <class T> public ref class Five {   // CLS09911 };  
  
```