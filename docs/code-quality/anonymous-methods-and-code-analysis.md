---
title: "무명 메서드 및 코드 분석 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- methods, anonymous
- code analysis, anonymous methods
- anonymous methods, code analysis
ms.assetid: bf0a1a9b-b954-4d46-9c0b-cee65330ad00
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8ebf550ca92cbefbed684e2b11e0b20b62661133
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="anonymous-methods-and-code-analysis"></a>무명 메서드 및 코드 분석
*무명 메서드* 는 이름이 없는 메서드입니다. 무명 메서드는 코드 블록을 대리자 매개 변수로 전달 하는 데 가장 자주 사용 됩니다.  
  
 이 항목에서는 코드 분석 경고 및 무명 메서드와 관련된 된 메트릭을 처리 하는 방법을 설명 합니다.  
  
## <a name="anonymous-methods-declared-in-a-member"></a>멤버에서 선언 된 무명 메서드  
 경고 및 메트릭을 무명 메서드의 메서드 또는 접근자와 같은 멤버에 선언 된 메서드를 선언 하는 멤버와 연결 됩니다. 메서드를 호출 하는 멤버와 연결 되지 않습니다.  
  
 다음 클래스의 선언에 있는 모든 경고의 예를 들어 **무명 메서드** 에 대해 발생 해야 **Method1** 아닌 **Method2**합니다.  
  
```vb  
  
      Delegate Function ADelegate(ByVal value As Integer) As Boolean  
Class AClass  
  
    Sub Method1()  
        Dim anonymousMethod As ADelegate = Function(ByVal value As Integer) value > 5  
        Method2(anonymousMethod)  
    End SubSub Method2(ByVal anonymousMethod As ADelegate)  
        anonymousMethod(10)  
    End SubEnd Class  
```  
  
```csharp  
  
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
  
## <a name="inline-anonymous-methods"></a>인라인 무명 메서드  
 경고 및 필드에 할당 하는 인라인으로 선언 되는 무명 메서드의 대 한 메트릭을 해당 생성자와 연결 됩니다. 필드로 선언 되 면 `static` (`Shared` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]), 경고 및 메트릭이 되 고, 그렇지 않으면 해당 클래스 생성자와 연결, 인스턴스 생성자와 연결 되어 있습니다.  
  
 다음 클래스의 선언에 있는 모든 경고의 예를 들어 **anonymousMethod1** 의 암시적으로 생성 된 기본 생성자에 대해 발생 **클래스**합니다. 찾을 수 있는 반면 **anonymousMethod2** 암시적으로 생성 된 클래스 생성자에 대해 적용 됩니다.  
  
```vb  
  
  Delegate Function ADelegate(ByVal value As Integer) As BooleanClass AClass  
Dim anonymousMethod1 As ADelegate = Function(ByVal value As    Integer) value > 5  
Shared anonymousMethod2 As ADelegate = Function(ByVal value As     Integer) value > 5  
  
Sub Method1()  
    anonymousMethod1(10)  
    anonymousMethod2(10)  
End SubEnd Class  
```  
  
```csharp  
  
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
  
 클래스는 생성자를 여러 개 지정 된 필드에 값을 할당 하는 인라인 익명 메서드를 포함할 수 있습니다. 이 경우 경고 및 메트릭을 연관 된 모든 생성자 생성자 동일한 클래스에 있는 다른 생성자에 연결 하지 않는 한 합니다.  
  
 다음 클래스의 선언에 있는 모든 경고의 예를 들어 **무명 메서드** 에 대해 발생 해야 **class (int)** 및 **Class(string)** 하지만 대해서가 아니라 **Class()**합니다.  
  
```vb  
  
  Delegate Function ADelegate(ByVal value As Integer) As BooleanClass AClass  
  
Dim anonymousMethod As ADelegate = Function(ByVal value As Integer)   
value > 5  
  
SubNew()  
    New(CStr(Nothing))  
End SubSub New(ByVal a As Integer)  
End SubSub New(ByVal a As String)  
End SubEnd Class  
```  
  
```csharp  
  
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
  
 보이지만이 예기치 않은, 컴파일러 출력에서 다른 생성자에 연결 되지 않은 모든 생성자는 고유한 방법을 하기 때문에 발생 합니다. 이러한 동작으로 인해 모든 하에서 위반이 발생 **무명 메서드** 개별적으로 실행 되지 않아야 합니다. 즉, 하는 새로운 생성자가에 대해 이전에 표시 되지 않은 경고가 **class (int)** 및 **Class(string)** 새 생성자에 대해서도 실행 되지 않아야 합니다.  
  
 두 가지 방법 중 하나에서이 문제를 해결할 수 있습니다. 선언할 수 **무명 메서드** 공통 생성자에는 모든 생성자 체인입니다. 또는 모든 생성자에서 호출 되어 초기화 메서드에서 선언할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 코드 품질 분석](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)