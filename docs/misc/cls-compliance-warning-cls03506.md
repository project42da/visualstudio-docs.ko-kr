---
title: "CLS 규격 경고 CLS03506 | Microsoft Docs"
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
  - "CLS03506"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS03506"
ms.assetid: baec820c-aabb-44c4-b0cd-043c3ca9c537
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS03506
**CLS에서는 공개적으로 표시되는 필수 한정자\(modreq\)를 허용하지 않지만 인식할 수 없는 선택적 한정자\(modopt\)는 허용합니다.**  
  
 CLS에서는 공개적으로 표시되는 필수 한정자\(modreq\)를 허용하지 않지만 인식할 수 없는 선택적 한정자\(modopt\)는 허용합니다.  
  
 메서드 서명에는 공개적으로 표시되는 필수 한정자로 표시되는 형식이 포함되지 않아야 합니다.  
  
 CLS\(공용 언어 하위 집합\) 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 샘플에서는 CLS03506을 생성합니다.  
  
```  
// CLS03506.cpp // compile with: /clr /LD // CLS03506 expected using namespace System; using namespace System::Reflection; using namespace cli::language; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; public ref class One { public: void F1(volatile Int32 parameter) {}   // CLS03506 void F2( Int32 parameter) {}   // OK };  
```