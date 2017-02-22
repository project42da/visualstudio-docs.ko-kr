---
title: "CA1024: 적합한 속성을 사용하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "UsePropertiesWhereAppropriate"
  - "CA1024"
helpviewer_keywords: 
  - "CA1024"
  - "UsePropertiesWhereAppropriate"
ms.assetid: 3a04f765-af7c-4872-87ad-9cc29e8e657f
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1024: 적합한 속성을 사용하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|UsePropertiesWhereAppropriate|  
|CheckId|CA1024|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 메서드가 `Get`으로 시작하는 이름을 사용하고, 매개 변수를 사용하지 않으며, 배열이 아닌 값을 반환합니다.  
  
## 규칙 설명  
 대부분의 경우 속성은 데이터를 나타내며 메서드는 작업을 수행합니다.  속성은 필드와 같은 방식으로 액세스하므로 사용하기 쉽습니다.  다음 조건 중 하나에 해당되는 경우 메서드는 속성이 될 수 있는 좋은 예입니다.  
  
-   인수를 사용하지 않으며 개체의 상태 정보를 반환하는 경우  
  
-   하나의 인수를 받아들여 개체 상태의 일부를 설정하는 경우  
  
 속성은 필드인 것처럼 작동해야 하며 필드처럼 작동할 수 없는 메서드는 속성으로 변경하지 않아야 합니다.  다음 상황에서는 속성보다 메서드를 사용하는 것이 좋습니다.  
  
-   메서드에서 시간이 많이 걸리는 작업을 수행하는 경우.  메서드에서 필드의 값을 설정하거나 가져오는 데 필요한 시간이 확실히 더 깁니다.  
  
-   메서드에서 변환을 수행하는 경우.  필드에 액세스할 때는 필드에 저장된 데이터가 변환되지 않고 반환됩니다.  
  
-   Get 메서드에 예측 가능한 파생 작업이 있는 경우.  필드 값을 검색할 때는 의도하지 않은 결과가 발생하는 경우가 없습니다.  
  
-   실행 순서가 중요한 경우.  필드 값을 설정할 때는 발생한 다른 작업에 의존하지 않습니다.  
  
-   메서드를 연속해서 두 번 호출하면 서로 다른 결과가 생성되는 경우  
  
-   메서드가 정적 메서드이지만 호출자가 변경할 수 있는 개체를 반환하는 경우.  필드 값을 검색할 때는 호출자가 필드에 저장된 데이터를 변경할 수 없습니다.  
  
-   메서드가 배열을 반환하는 경우  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 메서드를 속성으로 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 메서드가 앞에서 나열한 조건 중 하나라도 충족하는 경우 이 규칙에서 경고를 표시하지 않도록 설정합니다.  
  
## 디버거에서 속성 확장 제어  
 프로그래머가 속성을 사용하기를 피하는 한 가지 이유는 디버거에서 속성을 자동으로 확장하는 것을 원하지 않기 때문입니다.  예를 들어 속성에는 큰 개체를 할당하거나 P\/Invoke를 호출하는 작업이 수반되지만 실제로 예측 가능한 파생 작업은 발생하지 않을 수 있습니다.  
  
 <xref:System.Diagnostics.DebuggerBrowsableAttribute?displayProperty=fullName>를 적용하면 디버거에서 속성을 자동으로 확장하지 않도록 할 수 있습니다.  다음 예제에서는 이 특성이 인스턴스 속성에 적용되는 방식을 보여 줍니다.  
  
```vb  
Imports System   
Imports System.Diagnostics   
  
Namespace Microsoft.Samples   
  
    Public Class TestClass   
  
        ' [...]   
  
        <DebuggerBrowsable(DebuggerBrowsableState.Never)> _   
        Public ReadOnly Property LargeObject() As LargeObject   
            Get   
                ' Allocate large object   
                ' [...]   
            End Get   
        End Property   
  
    End Class   
  
End Namespace  
```  
  
```c#  
  
        using System;   
using System.Diagnostics;   
  
namespace Microsoft.Samples   
{   
    public class TestClass   
    {   
        // [...]   
  
        [DebuggerBrowsable(DebuggerBrowsableState.Never)]   
        public LargeObject LargeObject   
        {   
            get   
            {   
                // Allocate large object   
                // [...]   
  
        }  
    }  
}  
```  
  
## 예제  
 다음 예제에는 속성으로 변환해야 하는 메서드 몇 개와 필드처럼 작동하지 않기 때문에 속성으로 변환하지 않아야 하는 메서드 몇 개가 포함되어 있습니다.  
  
 [!code-cs[FxCop.Design.MethodsProperties#1](../code-quality/codesnippet/CSharp/ca1024-use-properties-where-appropriate_1.cs)]