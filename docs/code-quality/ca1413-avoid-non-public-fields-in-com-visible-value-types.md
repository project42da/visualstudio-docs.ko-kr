---
title: ": Ca1413 comvisible 값 형식에 public이 아닌 필드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
helpviewer_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
ms.assetid: 1352e7eb-fefc-4239-8847-25edc7804a54
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0e2763cb21107f19768a8161d18e1128eb000d29
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1413-avoid-non-public-fields-in-com-visible-value-types"></a>CA1413: ComVisible 값 형식에 public이 아닌 필드를 사용하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidNonpublicFieldsInComVisibleValueTypes|  
|CheckId|CA1413|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 특히 표시 유형 구성 요소 개체 모델 (COM)에 표시 된 값 형식에 public이 아닌 인스턴스 필드를 선언 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 public이 아니며 값 형식이 COM에 노출되는 인스턴스 필드는 COM 클라이언트에서 볼 수 있습니다. 노출 되지 않아야, 또는 의도 하지 않은 디자인 또는 보안 영향을 줄 수 있는 정보에 대 한 필드의 내용을 검토 합니다.  
  
 모든 공용 값 형식은 기본적으로 COM에 표시 됩니다. 그러나 거짓 긍정을 줄이기 위해이 규칙에서는 명시적으로 지정 되어야 하는 유형의 COM 가시성을 요구 합니다. 포함 하는 어셈블리 표시 되어야 합니다는 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 로 설정 `false` 형식으로 표시 해야 하 고는 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 로 설정 `true`합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하 고 숨겨진 필드를 유지 하려면 참조 형식에 값 형식을 변경 하거나 제거는 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 유형에 서 특성입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 필드의 노출 허용 되는 경우이 규칙에서는 경고를에서 표시 하지 않으려면 안전 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.  
  
 [!code-csharp[FxCop.Interoperability.NonpublicField#1](../code-quality/codesnippet/CSharp/ca1413-avoid-non-public-fields-in-com-visible-value-types_1.cs)]
 [!code-vb[FxCop.Interoperability.NonpublicField#1](../code-quality/codesnippet/VisualBasic/ca1413-avoid-non-public-fields-in-com-visible-value-types_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1407: COM 노출 형식에 정적 멤버를 사용하지 마십시오.](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)  
  
 [CA1017: 어셈블리를 ComVisibleAttribute로 표시하십시오.](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## <a name="see-also"></a>참고 항목  
 [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)   
 [상호 운용할 .NET 형식의 정규화](/dotnet/framework/interop/qualifying-net-types-for-interoperation)