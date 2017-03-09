---
title: "CObject 파생 클래스 구현 시 컴파일러 오류 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "소스 코드 컴파일, CObject 파생 클래스"
  - "오류[C++]"
  - "오류[C++], 컴파일러"
  - "CObject 클래스, 파생 클래스에 대한 컴파일러 오류"
ms.assetid: 9f249b52-aeff-41a1-8a74-a52aa08c4fcf
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CObject 파생 클래스 구현 시 컴파일러 오류
`CObject`에서 파생 클래스를 구현하고 클래스에 대한 복사 생성자 또는 대입 연산자를 호출해야 하도록 코드가 작성된 경우 컴파일러에서 다음과 비슷한 오류를 보고할 수 있습니다.  
  
```  
error C2660: 'CSample::CSample' : function does not take 1 parameters error C2582: 'CSample' : 'operator =' function is unavailable  
```  
  
 아래 샘플 코드 섹션의 예제를 컴파일하면 문제를 재현할 수 있습니다.  
  
> [!NOTE]
>  이 문서에 나와 있는 샘플 코드에서는 다음과 같은 오류 메시지가 생성됩니다.  
  
```  
error C2558: 'CSample::CSample' : no copy constructor available error C2582: 'CSample' : 'operator =' function is unavailable  
```  
  
 컴파일러 오류가 발생하는 이유는 `CObject`가 AFX.h 파일에서 전용 복사 생성자 및 대입 연산자를 선언하기 때문입니다. 따라서 컴파일러는 `CObject` 파생 클래스에 대한 기본 복사 생성자와 대입 연산자를 생성하지 않습니다. 컴파일러가 클래스에 선언된 이러한 함수를 찾을 수 없기 때문에 오류를 보고합니다.  
  
 컴파일러 오류를 방지하려면 `CObject` 파생 클래스에 대한 복사 생성자와 대입 연산자를 구현해야 합니다. 이 구현은 아래 샘플 코드에 나와 있습니다. 샘플 코드에 표시된 줄의 주석 처리를 제거하면 오류를 방지할 수 있습니다.  
  
## 샘플 코드  
  
```  
// _error_Compiler_Errors_when_Implementing_a_CObject.2d.Derived_Class.cpp /* Compile options needed: /c */ // replace with #define _CONSOLE when compiling for Windows NT #define _DOS #include <afx.h> class CSample : public CObject { private: short m_nValue; public: // uncomment the lines below to avoid the compiler errors //    CSample() {} //    CSample( const CSample &s )  // copy ctor //        { m_nValue = s.m_nValue; } //    CSample& operator=( const CSample &s )  // assignment operator //        { m_nValue = s.m_nValue; return *this; } }; int main() { CSample a; CSample b = a; a = b; }  
  
```  
  
## 참고 항목  
 [컴파일러 경고s C4600 Through C4999](/visual-cpp/error-messages/compiler-warnings/compiler-warnings-c4600-through-c4799)