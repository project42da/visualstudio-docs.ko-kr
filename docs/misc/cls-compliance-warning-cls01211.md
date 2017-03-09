---
title: "CLS 규격 경고 CLS01211 | Microsoft Docs"
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
  - "CLS01211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01211"
ms.assetid: a6df4b7a-81e8-4e77-90d1-ec1cc3a759f5
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS01211
형식과 멤버의 표시 유형 및 접근성은 해당 멤버가 표시되고 액세스 가능한 경우 모든 멤버의 시그니처에 있는 해당 형식이 표시되고 액세스 가능해야 합니다. 예를 들어 어셈블리 외부에 표시되는 형식은 어셈블리 내부에서만 표시되는 기본 형식을 가질 수 없습니다.  
  
 형식\(A\)에 의해 상속 또는 구현된 형식과 인터페이스는 해당 형식보다 접근성이 크거나 같아야 합니다.  예를 들어 어셈블리 외부에 표시되는 공용 메서드는 어셈블리 내부에서만 표시되는 형식의 인수를 가질 수 없습니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 샘플에서는 CLS01211을 생성합니다.  
  
```  
// CLS01211.cpp // compile with: /clr /LD // CLS01211 expected using namespace System; using namespace System::Reflection; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; private interface class I {}; public interface class I2 : public I {};  
```