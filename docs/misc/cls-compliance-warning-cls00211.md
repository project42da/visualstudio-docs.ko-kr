---
title: "CLS 규격 경고 CLS00211 | Microsoft Docs"
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
  - "CLS00211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS00211"
ms.assetid: 3a103f6f-bfb7-42ed-83ab-1c0f34fb9672
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS00211
CLS 규격 형식이 아닌 멤버를 CLS 규격으로 표시해서는 안 됩니다.  
  
 형식이 CLS 규격이 아닌 것으로 표시된 경우 형식 멤버를 CLS 규격으로 표시할 수 없습니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 샘플에서는 CLS00211을 생성합니다.  
  
```  
// CLS00211.cpp // compile with: /clr /LD // CLS00211 expected using namespace System; using namespace System::Reflection; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; [CLSCompliant(false)] public ref class One { public: [CLSCompliant(true)]   // CLS00211 void X() {} };  
```