---
title: "CLS 규격 경고 CLS00711 | Microsoft Docs"
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
  - "CLS00711"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS00711"
ms.assetid: 76481641-bda1-4128-8da8-ccba577b7ba1
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS00711
열거형의 내부 형식은 기본 제공 CLS 정수 형식이어야 합니다.  
  
 열거형의 내부 형식을 지정하고 CLS 규격 어셈블리를 원하는 경우 열거형의 내부 형식은 CLS\(공용 언어 하위 집합\) 규격 정수 형식이어야 합니다.  
  
 CLR 열거형에 대한 자세한 내용은 [enum 클래스](/visual-cpp/windows/enum-class-cpp-component-extensions)를 참조하세요.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 샘플에서는 CLS00711을 생성합니다.  
  
```  
// CLS00711.cpp // compile with: /clr /LD // CLS00711 expected using namespace System; using namespace System::Reflection; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; public ref class One { public: enum class MyEnum_cls_bad : Char { bad_one = 1, bad_two = 2, bad_three = 3 }; enum class MyEnum_cls_good : Int32 { good_one = 1, good_two = 2, good_three = 3 }; };  
```