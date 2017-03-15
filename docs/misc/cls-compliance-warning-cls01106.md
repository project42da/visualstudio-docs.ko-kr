---
title: "CLS 규격 경고 CLS01106 | Microsoft Docs"
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
  - "CLS01106"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01106"
ms.assetid: 0c964444-387d-4348-aed5-05f1ccc241c8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS01106
**서명에 나타나는 모든 형식은 CLS 규격을 준수해야 합니다.**  
  
 형식이 CLS 규격이면 CLS 비규격으로 표시되지 않은 경우 형식의 모든 함수에 CLS 규격 형식 매개 변수가 있어야 합니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 샘플에서는 CLS01106을 생성합니다.  
  
```  
// CLS01106.cpp // compile with: /clr /LD // CLS01106 expected using namespace System; using namespace System::Reflection; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; [CLSCompliant(true)] public ref class CompliantType {}; [CLSCompliant(false)] public ref class NotCompliantType {}; [CLSCompliant(true)] public ref class One { public: NotCompliantType^ Method1(NotCompliantType^ parameter) { return parameter; } CompliantType^ Method2(CompliantType^ parameter) {   // OK return parameter; } [CLSCompliant(false)] NotCompliantType^ Method3(NotCompliantType^ parameter) {   // OK return parameter; } };  
```