---
title: ": Ca1407 COM 노출 형식에 정적 멤버 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
helpviewer_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
ms.assetid: bebd0776-ad04-453c-bca8-8c124c2d7840
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9cb2b7a95772ddd95bf4379ea0749cf42419a182
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1407-avoid-static-members-in-com-visible-types"></a>CA1407: COM 노출 형식에 정적 멤버를 사용하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidStaticMembersInComVisibleTypes|  
|CheckId|CA1407|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 특히 표시 유형 구성 요소 개체 모델 (COM)에 표시 된 형식에 포함 되어는 `public``static` 메서드.  
  
## <a name="rule-description"></a>규칙 설명  
 COM 지원 하지 않습니다 `static` 메서드.  
  
 이 규칙을 무시 속성 및 이벤트 접근자, 메서드 또는 하나를 사용 하 여 표시 된 메서드를 오버 로드 된 연산자는 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 특성 또는 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> 특성입니다.  
  
 기본적으로 다음 COM에 표시 되지만: 어셈블리, public 형식, public 인스턴스 멤버를 공용 형식 및 공용 값 형식의 모든 멤버입니다.  
  
 어셈블리 수준 발생 하도록이 규칙에 대 한 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 으로 설정 되어 있어야 `false` 및 클래스- <xref:System.Runtime.InteropServices.ComVisibleAttribute> 로 설정 해야 `true`다음 코드와 같이, 합니다.  
  
```csharp  
using System;  
using System.Runtime.InteropServices;   
  
[assembly: ComVisible(false)]   
namespace Samples  
{      
    [ComVisible(true)]  
    public class MyClass  
    {  
        public static void DoSomething()  
        {  
        }  
    }  
}  
```  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반을 해결 하려면 변경와 동일한 기능을 제공 하는 인스턴스 메서드를 사용 하도록 디자인 된 `static` 메서드.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 COM 클라이언트에서 제공 하는 기능에 액세스할 필요 하지 않은 경우이 규칙에서는 경고를에서 표시 하지 않는를 안전 하 게는 `static` 메서드.  
  
## <a name="example-violation"></a>예제 위반  
  
### <a name="description"></a>설명  
 다음 예제와 `static` 이 규칙을 위반 하는 메서드입니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersViolation#1](../code-quality/codesnippet/CSharp/ca1407-avoid-static-members-in-com-visible-types_1.cs)]  
  
### <a name="comments"></a>설명  
 이 예제는 **Book.FromPages** COM에서 메서드를 호출할 수 없습니다  
  
## <a name="example-fix"></a>예제 수정  
  
### <a name="description"></a>설명  
 이전 예에서 위반을 해결 하려면 메서드 인스턴스 메서드를 변경할 수 있습니다 하지만 의미가 없으며이 인스턴스에서 합니다. 명시적으로 적용 하는 것이 좋습니다 `ComVisible(false)` COM에서 메서드를 볼 수 없는 다른 개발자가 있도록 메서드  
  
 다음 예제에서는 적용 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> 메서드에 합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1407-avoid-static-members-in-com-visible-types_2.cs)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1017: 어셈블리를 ComVisibleAttribute로 표시하십시오.](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
 [CA1406: Visual Basic 6 클라이언트에서 Int64 인수를 사용하지 않습니다.](../code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)  
  
 [CA1413: Com 노출 값 형식에 public이 아닌 필드를 사용하지 마십시오.](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)  
  
## <a name="see-also"></a>참고 항목  
 [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)