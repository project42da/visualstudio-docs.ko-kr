---
title: "CLS 규격 경고 CLS03501 | Microsoft Docs"
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
  - "CLS03501"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS03501"
ms.assetid: 26a08830-9c8a-4bf6-931d-e0c523f1eb21
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS03501
CLS에서는 공개적으로 표시되는 필수 한정자\(modreq\)를 허용하지 않지만 인식할 수 없는 선택적 한정자\(modopt\)는 허용합니다.  
  
 CLS에서는 공개적으로 표시되는 필수 한정자\(modreq\)를 허용하지 않지만 인식할 수 없는 선택적 한정자\(modopt\)는 허용합니다.  
  
 생성자 서명에는 공개적으로 표시되는 필수 한정자로 표시되는 형식이 포함되지 않아야 합니다.  
  
 CLS\(공용 언어 하위 집합\) 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 샘플에서는 CLS03501을 생성합니다.  
  
```  
// CLS03501.cpp // compile with: /clr /LD // CLS03501 expected using namespace System; using namespace System::Reflection; using namespace cli::language; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; public ref class One { public: One(volatile Int32 param) {}   // CLS03501 One( Int32 param1, Int32 param2) {}   // OK };  
```