---
title: "무명 메서드 및 코드 분석 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "무명 메서드, 코드 분석"
  - "코드 분석, 무명 메서드"
  - "메서드, 무명"
ms.assetid: bf0a1a9b-b954-4d46-9c0b-cee65330ad00
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 19
---
# 무명 메서드 및 코드 분석
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

*무명 메서드*는 이름이 없는 메서드입니다.  무명 메서드는 코드 블록을 대리자 매개 변수로 전달할 때 가장 자주 사용됩니다.  
  
 이 항목에서는 코드 분석을 통해 무명 메서드와 관련된 경고 및 메트릭을 처리하는 방법을 설명합니다.  
  
## 멤버에 선언된 무명 메서드  
 메서드나 접근자처럼 멤버에서 선언되는 무명 메서드의 경고 및 메트릭은 해당 메서드를 선언하는 멤버와 연결됩니다.  메서드를 호출하는 멤버와는 연결되지 않습니다.  
  
 예를 들어 다음 클래스에서 **anonymousMethod**의 선언에 있는 모든 경고는 **Method1**에 대해서는 발생하지만 **Method2**에 대해서는 발생하지 않습니다.  
  
```vb#  
  
        Delegate Function ADelegate(ByVal value As Integer) As Boolean  
Class AClass  
  
    Sub Method1()  
        Dim anonymousMethod As ADelegate = Function(ByVal value As  Integer) value > 5  
        Method2(anonymousMethod)  
    End Sub Sub Method2(ByVal anonymousMethod As ADelegate)  
        anonymousMethod(10)  
    End Sub End Class  
```  
  
```c#  
  
        delegate void Delegate();  
class Class  
{  
    void Method1()  
    {  
        Delegate anonymousMethod = delegate()   
        {   
          Console.WriteLine("");   
        }  
        Method2(anonymousMethod);  
    }  
  
    void Method2(Delegate anonymousMethod)  
    {  
        anonymousMethod();  
    }  
}  
```  
  
## 인라인 무명 메서드  
 필드에 대한 인라인 할당으로 선언된 무명 메서드의 경고 및 메트릭은 해당 생성자와 연결됩니다.  필드가 `static`\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 `Shared`\)으로 선언된 경우에는 경고 및 메트릭이 클래스 생성자와 연결되고, 그렇지 않은 경우에는 경고 및 메트릭이 인스턴스 생성자와 연결됩니다.  
  
 예를 들어 다음 클래스에서 **anonymousMethod1**의 선언에 있는 모든 경고는 **Class**의 암시적으로 생성된 기본 생성자에 대해서 발생합니다.  반면 **anonymousMethod2**에 있는 모든 경고는 암시적으로 생성된 클래스 생성자에 대해 적용됩니다.  
  
```vb#  
  
    Delegate Function ADelegate(ByVal value As Integer) As Boolean Class AClass  
Dim anonymousMethod1 As ADelegate = Function(ByVal value As     Integer) value > 5  
Shared anonymousMethod2 As ADelegate = Function(ByVal value As      Integer) value > 5  
  
Sub Method1()  
    anonymousMethod1(10)  
    anonymousMethod2(10)  
End Sub End Class  
```  
  
```c#  
  
        delegate void Delegate();  
class Class  
{  
    Delegate anonymousMethod1 = delegate()   
    {   
       Console.WriteLine("");   
    }  
  
    static Delegate anonymousMethod2 = delegate()   
    {   
       Console.WriteLine("");   
    }  
  
    void Method()  
    {  
       anonymousMethod1();  
       anonymousMethod2();  
    }  
}  
```  
  
 클래스에는 생성자가 여러 개인 필드에 값을 할당하는 인라인 무명 메서드가 들어 있을 수 있습니다.  이 경우 경고 및 메트릭은 모든 생성자와 연결됩니다. 단, 해당 생성자가 동일한 클래스의 다른 생성자에 연결되지 않은 경우에 한합니다.  
  
 예를 들어 다음 클래스에서 **anonymousMethod**의 선언에 있는 모든 경고는 **Class\(int\)** 및 **Class\(string\)**에 대해서는 발생하지만 **Class\(\)**에 대해서는 발생하지 않습니다.  
  
```vb#  
  
    Delegate Function ADelegate(ByVal value As Integer) As Boolean Class AClass  
  
Dim anonymousMethod As ADelegate = Function(ByVal value As Integer)   
value > 5  
  
Sub New()  
    New(CStr(Nothing))  
End Sub Sub New(ByVal a As Integer)  
End Sub Sub New(ByVal a As String)  
End Sub End Class  
```  
  
```c#  
  
        delegate void Delegate();  
class Class  
{  
    Delegate anonymousMethod = delegate()   
    {   
       Console.WriteLine("");   
    }  
  
    Class() : this((string)null)  
    {  
    }  
  
    Class(int a)  
    {  
    }  
  
    Class(string a)  
    {  
    }  
}  
```  
  
 이러한 결과는 예기치 않은 것처럼 보일 수 있지만 컴파일러에서 다른 생성자에 연결되지 않은 모든 생성자에 대해 고유한 메서드를 출력하기 때문에 발생합니다.  이 동작 때문에 **무명 메서드** 내에서 발생하는 모든 위반은 개별적으로 표시되지 않도록 설정해야 합니다.  이는 또한 새 생성자가 사용될 경우 이전에 **Class\(int\)** 및 **Class\(string\)**에 대해 표시되지 않도록 설정된 경고가 새 생성자에 대해서도 표시되지 않도록 설정되어야 함을 의미합니다.  
  
 이 문제를 해결하려면  모든 생성자가 거치는 공용 생성자에 **anonymousMethod**를 선언할 수 있습니다.  또는 모든 생성자가 호출하는 초기화 메서드에 선언할 수 있습니다.  
  
## 참고 항목  
 [관리 코드 품질 분석](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)