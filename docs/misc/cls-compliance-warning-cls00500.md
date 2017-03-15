---
title: "CLS 규격 경고 CLS00500 | Microsoft Docs"
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
  - "CLS00500"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS00500"
ms.assetid: faaf377e-3738-4c0d-9a51-09db4073564e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS00500
CLS 규격 범위의 모든 이름 종류는 고유하고 독립적이어야 합니다.  
  
 CLS 규격 범위에 소개된 모든 이름은 이름이 동일한 경우를 제외하고는 종류가 독립적이고 고유한 이름이어야 하며 오버로드를 통해 확인됩니다. CLS에서는 소문자 매핑이 동일한 두 이름의 경우 동일합니다. 속성 및 함수만 오버로드될 수 있습니다. 오버로드되면 반환 형식에 따라서도 오버로드 될 수 있는 변환 연산자를 제외하고, 속성 및 함수는 매개 변수의 개수나 형식에 따라서만 오버로드될 수 있습니다. 자세한 내용은 [사용자 정의 변환](/visual-cpp/dotnet/user-defined-conversions-cpp-cli)를 참조하세요.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 샘플에서는 CLS00500을 생성합니다.  
  
```  
// CLS00500.cpp // compile with: /clr /LD // CLS00500 expected using namespace System; using namespace System::Reflection; [assembly:AssemblyKeyFile("clscompliance.snk")]; [assembly:System::CLSCompliant(true)]; public ref class a {}; public ref class A {};   // CLS00500  
```