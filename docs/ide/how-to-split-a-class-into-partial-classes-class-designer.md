---
title: "How to: Split a Class into Partial Classes (Class Designer) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Class Designer, partial classes"
  - "partial classes, Class Designer"
ms.assetid: 6f6b0b30-3996-4569-9200-20482b3adf90
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# How to: Split a Class into Partial Classes (Class Designer)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Basic에서 `Partial` 키워드를 사용하거나 Visual C\#에서 `partial` 키워드를 사용하여 여러 선언 중에서 클래스 또는 구조체의 선언을 나눌 수 있습니다.  원하는 만큼의 다양한 소스 파일 또는 하나의 소스 파일에 partial 선언을 원하는 만큼 사용할 수 있습니다.  그러나 모든 선언은 동일한 어셈블리와 네임스페이스에 있어야 합니다.  
  
 Partial 클래스는 여러 상황에 유용합니다.  예를 들어 대규모 프로젝트를 수행하는 경우 하나의 클래스를 두 개 이상의 파일로 분할하면 두 명 이상의 프로그래머가 동시에 해당 프로젝트를 수행할 수 있습니다.  Visual Studio에서 생성된 코드를 사용하여 작업하는 경우 소스 파일을 다시 만들 필요 없이 클래스를 변경할 수 있습니다.  Visual Studio에서 생성된 코드의 예로는 Windows Forms 및 웹 서비스 래퍼 코드가 있습니다. 따라서 Visual Studio에서 만든 파일을 수정할 필요 없이 자동 생성된 클래스를 사용하는 코드를 만들 수 있습니다.  
  
 부분 메서드\(Partial Method\)에는 두 가지 종류가 있습니다.  Visual C\#에서는 선언\(declaring\) 및 구현\(implementing\)이라고 하며 Visual Basic에서는 선언\(declaration\) 및 구현\(implementation\)이라고 합니다.  
  
 클래스 디자이너에서는 partial 클래스 및 메서드를 지원합니다.  클래스 다이어그램의 형식 모양은 partial 클래스의 단일 선언 위치를 참조합니다.  partial 클래스가 여러 파일에 정의되어 있는 경우 **속성** 창에서 **새 멤버 위치** 속성을 설정하여 클래스 디자이너에서 사용할 선언 위치를 지정할 수 있습니다.  즉, 클래스 모양을 두 번 클릭하면 클래스 디자이너는 **새 멤버 위치** 속성에 지정된 클래스 선언이 포함된 소스 파일로 이동합니다.  클래스 모양의 부분 메서드를 두 번 클릭하면 클래스 디자이너는 부분 메서드 선언으로 이동합니다.  또한 **속성** 창의 **파일 이름** 속성도 선언 위치를 참조합니다.  partial 클래스의 경우 **파일 이름**에는 해당 클래스의 선언 및 구현 코드가 포함된 모든 파일이 나열됩니다.  그러나 부분 메서드의 경우에는 **파일 이름**에 부분 메서드 선언이 포함된 파일만 나열됩니다.  
  
 다음 예제에서는 `Employee` 클래스의 정의를 두 개의 선언으로 분리합니다. 각 선언에서는 서로 다른 프로시저를 정의합니다.  예제의 두 partial 정의는 하나의 소스 파일이나 서로 다른 두 개의 소스 파일에 존재할 수 있습니다.  
  
> [!NOTE]
>  Visual Basic에서는 partial 클래스 정의를 사용하여 Visual Studio에서 생성된 코드와 사용자가 작성한 코드를 분리합니다.  코드는 별도의 소스 파일로 분할됩니다.  예를 들어, **Windows Form 디자이너**는 `Form`과 같은 컨트롤에 대한 partial 클래스를 정의합니다.  이러한 컨트롤에서 생성된 코드를 수정하면 안 됩니다.  
  
 Visual Basic의 부분 형식에 대한 자세한 내용은 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial)을 참조하십시오.  
  
## 예제  
 Visual Basic에서 클래스 정의를 분할하려면 다음 예제와 같이 `Partial` 키워드를 사용하십시오.  
  
```vb#  
' First part of class definition.  
Partial Public Class Employee  
    Public Sub CalculateWorkHours()  
    End Sub  
End Class  
  
' Second part of class definition.  
Partial Public Class Employee  
    Public Sub CalculateTaxes()  
    End Sub  
End Class  
```  
  
## 예제  
 Visual C\#에서 클래스 정의를 분할하려면 다음 예제와 같이 `partial` 키워드를 사용하십시오.  
  
```c#  
// First part of class definition.  
public partial class Employee  
{  
    public void CalculateWorkHours()  
    {  
    }  
}  
  
// Second part of class definition.  
public partial class Employee  
{  
    public void CalculateTaxes()  
    {  
    }  
}  
```  
  
## 참고 항목  
 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)   
 [부분\(형식\)](/dotnet/csharp/language-reference/keywords/partial-type)   
 [부분\(메서드\)\(C\# 참조\)](/dotnet/csharp/language-reference/keywords/partial-method)   
 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial)