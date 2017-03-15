---
title: "__delegate | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__delegate_cpp"
  - "__delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "대리자를 _delegate 키워드"
  - "관리 되는 함수 포인터"
  - "__delegate 키워드"
ms.assetid: a41d2211-b79b-4509-a4c2-cc91f3d4fc9d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __delegate
**참고** 이 항목은 Managed Extensions for C\+\+ 버전 1에만 적용됩니다. 이 구문은 버전 1 코드를 유지하기 위해서만 사용해야 합니다. 참조 [delegate](/visual-cpp/windows/delegate-cpp-component-extensions) 동등한 기능을 사용 하 여 새 구문에서에 대 한 내용은 합니다.  
  
 특정 서명이 있는 메서드를 캡슐화하는 데 사용할 수 있는 참조 형식을 정의합니다.  
  
## 구문  
  
```  
  
__delegate   
function-declarator  
  
```  
  
## 설명  
 대리자는 다음 차이를 제외하고 C\+\+ 함수 포인터와 거의 같습니다.  
  
-   대리자는 \_\_gc 클래스 내에서 하나 이상의 메서드에만 바인딩될 수 있습니다.  
  
 컴파일러에서 `__delegate` 키워드를 발견하는 경우 \_\_gc 클래스의 정의가 생성됩니다. 이 \_\_gc 클래스에는 다음과 같은 특징이 있습니다.  
  
-   이는 **System::MulticastDelegate**에서 상속합니다.  
  
-   \_\_gc 클래스에 대한 포인터 또는 **NULL**\(정적 메서드에 바인딩하는 경우\) 및 지정된 형식의 정규화된 메서드 등 두 가지 인수를 취하는 생성자가 있습니다.  
  
-   `Invoke`라는 메서드가 있으며, 서명이 대리자의 선언된 서명과 일치합니다.  
  
## 예제  
 다음 예제에서는 \_\_gc 클래스\(`MyCalendar`\) 및 대리자\(`GetDayOfWeek`\)가 선언됩니다. 대리자는 `MyCalendar`의 다른 메서드와 바인딩되어 있으며 각각 차례대로 호출합니다.  
  
```  
// keyword__delegate.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__delegate int GetDayOfWeek();  
__gc class MyCalendar {  
public:  
   MyCalendar() : m_nDayOfWeek(4) {}  
   int MyGetDayOfWeek() {   
      Console::WriteLine("handler"); return m_nDayOfWeek;   
   }  
   static int MyStaticGetDayOfWeek() {   
      Console::WriteLine("static handler");   
      return 6;  
   }  
private:  
   int m_nDayOfWeek;  
};  
  
int main () {  
   GetDayOfWeek * pGetDayOfWeek;  // declare delegate type  
   int nDayOfWeek;  
  
   // bind delegate to static method  
   pGetDayOfWeek = new GetDayOfWeek(0, &MyCalendar::MyStaticGetDayOfWeek);  
   nDayOfWeek = pGetDayOfWeek->Invoke();  
   Console::WriteLine(nDayOfWeek);  
  
   // bind delegate to instance method  
   MyCalendar * pcal = new MyCalendar();  
   pGetDayOfWeek = static_cast<GetDayOfWeek*>(Delegate::Combine(pGetDayOfWeek,  
      new GetDayOfWeek(pcal, &MyCalendar::MyGetDayOfWeek)));  
   nDayOfWeek = pGetDayOfWeek->Invoke();  
   Console::WriteLine(nDayOfWeek);  
  
   // delegate now bound to two methods; remove instance method  
   pGetDayOfWeek = static_cast<GetDayOfWeek*>(Delegate::Remove(pGetDayOfWeek,  
      new GetDayOfWeek(pcal, &MyCalendar::MyGetDayOfWeek)));  
}  
```  
  
## 샘플 출력  
  
```  
static handler  
6  
static handler  
handler  
4  
```