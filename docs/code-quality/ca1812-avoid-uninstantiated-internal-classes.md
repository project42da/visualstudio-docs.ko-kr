---
title: 'CA1812: 인스턴스화되지 않은 내부 클래스 방지 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1812
- AvoidUninstantiatedInternalClasses
helpviewer_keywords:
- AvoidUninstantiatedInternalClasses
- CA1812
ms.assetid: 1bb92a42-322a-44cc-98a8-8858212c1e1f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 47ddd32dd590523fa4b3bfe4ab2d63951ccf503a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812: 인스턴스화되지 않은 내부 클래스를 사용하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidUninstantiatedInternalClasses|  
|CheckId|CA1812|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 어셈블리 수준 형식의 인스턴스가 어셈블리에서 코드에 의해 만들어지지 않습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 규칙 형식의 생성자 중 하나에 대 한 호출을 찾으려고 시도 하 고 호출 찾을 수 없으면 위반을 보고 합니다.  
  
 이 규칙에서 다음 형식 검사 하지 않습니다.  
  
-   값 형식  
  
-   추상 형식  
  
-   열거형  
  
-   대리자  
  
-   컴파일러에서 내보낸 배열 형식  
  
-   인스턴스화할 수 없습니다 및 정의 하는 형식 `static` (`Shared` Visual basic에서) 메서드에만 합니다.  
  
 적용 하는 경우 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName> 분석 되는 어셈블리에이 규칙으로 표시 된 생성자에서 발생 하지 것입니다 `internal` 필드 다른 사용 중인지 여부를 알 수 없습니다 때문에 `friend` 어셈블리입니다.  
  
 이 제한을 해결할 수 있지만 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코드 분석, 외부 독립 실행형 FxCop 경우 내부 생성자에 모든 `friend` 어셈블리는 분석에 포함 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 유형을 제거 하거나 사용 하는 코드를 추가 합니다. 유형이 정적 메서드만 포함 하는 경우 컴파일러는 기본 public 인스턴스 생성자를 생성 하지 않도록 하려면 형식에는 다음 중 하나를 추가 합니다.  
  
-   Private 생성자 형식을 대상으로 하는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전 1.0 및 1.1입니다.  
  
-   `static` (`Shared` Visual basic에서) 한정자에 대 한 대상으로 하는 형식 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 다음과 같은 상황에서이 경고를 표시 하는 것이 좋습니다.  
  
-   클래스는 런타임에 바인딩된 리플렉션 메서드를 통해와 같은 만들 <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>합니다.  
  
-   클래스는 런타임 또는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]에 의해 자동으로 만들어집니다. 이러한 예로 <xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName> 또는 <xref:System.Web.IHttpHandler?displayProperty=fullName>를 구현하는 클래스를 들 수 있습니다.  
  
-   클래스는 새 제약 조건이 있는 제네릭 형식 매개 변수로 전달 됩니다. 예를 들어 다음 예제에서는이 규칙을 발생 합니다.  
  
    ```csharp  
    internal class MyClass  
    {     
        public DoSomething()     
        {  
        }  
    }   
    public class MyGeneric<T> where T : new()  
    {  
        public T Create()  
        {  
            return new T();     
        }  
    }  
    // [...]   
    MyGeneric<MyClass> mc = new MyGeneric<MyClass>();  
    mc.Create();  
    ```  
  
 이러한 상황에서이 경고를 표시 하는 것이 좋습니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1811: 호출되지 않는 전용 코드를 사용하지 마십시오.](../code-quality/ca1811-avoid-uncalled-private-code.md)  
  
 [CA1801: 사용되지 않은 매개 변수를 검토하십시오.](../code-quality/ca1801-review-unused-parameters.md)  
  
 [CA1804: 사용되지 않는 로컬 항목을 제거하십시오.](../code-quality/ca1804-remove-unused-locals.md)