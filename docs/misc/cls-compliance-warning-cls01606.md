---
title: "CLS 규격 경고 CLS01606 | Microsoft Docs"
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
  - "CLS01606"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01606"
ms.assetid: 24291af4-d2b1-4a91-b50f-fb61d8ff1687
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS01606
배열에는 CLS 규격 형식의 요소가 있어야 하며 배열의 모든 차원은 하한이 0이어야 합니다.  
  
 배열에는 CLS 규격 형식의 요소가 있어야 하며 배열의 모든 차원은 하한이 0이어야 합니다. 항목은 배열이며 이 배열의 요소 형식은 오버로드 간에 구분되어야 합니다. 오버로드가 2개 이상의 배열 형식에 기반하는 경우 요소 형식은 명명된 형식이어야 합니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 샘플에서는 CLS01606을 생성합니다.  
  
```  
// CLS01606.cpp // compile with: /clr /LD // CLS01606 expected using namespace System; using namespace System::Reflection; using namespace cli::language; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; [CLSCompliant(true)] public ref class CompliantType {}; [CLSCompliant(false)] public ref class NotCompliantType {}; public ref class One { public: // CLS01606 array<NotCompliantType^>^ Method1() { return gcnew array<NotCompliantType^>(10); } // OK array<CompliantType^>^ Method2() { return gcnew array<CompliantType^>(10); } };  
```