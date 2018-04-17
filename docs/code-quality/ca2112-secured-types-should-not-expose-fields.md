---
title: 'CA2112: 보안된 형식은 필드를 노출 하지 해야 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2112
- SecuredTypesShouldNotExposeFields
helpviewer_keywords:
- SecuredTypesShouldNotExposeFields
- CA2112
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 050aa2a5048ed4d58e6b5a285f584eda330f178f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2112-secured-types-should-not-expose-fields"></a>CA2112: 보안 형식은 필드를 노출하면 안 됩니다.
|||  
|-|-|  
|TypeName|SecuredTypesShouldNotExposeFields|  
|CheckId|CA2112|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 Public 또는 protected 형식이 public 필드를 포함 하 고 의해 보안 됩니다는 [링크 요청](/dotnet/framework/misc/link-demands)합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 코드에 링크 요청으로 보안된 형식의 인스턴스에 대한 액세스 권한이 있으면 코드에서 링크 요청을 만족하지 않아도 해당 형식의 필드에 액세스할 수 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 public이 아닌 필드를 확인 하 고 공용 속성 또는 필드 데이터를 반환 하는 메서드를 추가 합니다. 형식에 대해 LinkDemand 보안 검사 형식의 메서드와 속성에 대 한 액세스를 보호합니다. 그러나 코드 액세스 보안 필드에 적용 되지 않습니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 모두 보안 문제에 대 한 좋은 디자인, public 필드 nonpublic 함으로써 위반 문제를 해결 해야 합니다. 필드는 보안을 유지 해야 하는 정보를 유지 하지 않으면이 규칙에서는 경고를에서 표시 하지 않을 수 있습니다 및 필드의 내용에 의존 하지 마십시오.  
  
## <a name="example"></a>예제  
 다음 예에서는 라이브러리 형식으로 구성 됩니다 (`SecuredTypeWithFields`), 보안 되지 않은 필드는 형식 (`Distributor`) 라이브러리 형식의 인스턴스를 만들 수 있는 형식에 잘못된 전달 인스턴스를 만들 수 있는 권한이 없는 및 응용 프로그램 코드에 인스턴스의 필드 형식을 보호 하는 권한 없는 경우에 읽을 수 있습니다.  
  
 라이브러리 코드의 다음 규칙을 위반 합니다.  
  
 [!code-csharp[FxCop.Security.LinkDemandOnField#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_1.cs)]  
  
## <a name="example"></a>예제  
 응용 프로그램 보안된 형식을 보호 하는 링크 요청으로 인해 인스턴스를 만들 수 없습니다. 다음 클래스에는 응용 프로그램을을 보안 된 형식의 인스턴스를 가져올 수 있습니다.  
  
 [!code-csharp[FxCop.Security.LDOnFieldsDistributor#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_2.cs)]  
  
## <a name="example"></a>예제  
 다음 응용 프로그램은 어떻게 보안된 형식의 메서드에 액세스할 수 있는 권한이 없으면 코드가 액세스할 수 있는 해당 필드를 보여 줍니다.  
  
 [!code-csharp[FxCop.Security.TestLinkDemandOnFields#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_3.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
 **SecuredTypeWithFields의 인스턴스를 만듭니다.**  
**보안 유형 필드: 22, 33**  
**보안 된 형식의 필드를 변경 하는 중...**  
**캐시 된 개체 필드: 99, 33**   
## <a name="related-rules"></a>관련된 규칙  
 [CA1051: 표시되는 인스턴스 필드를 선언하지 마십시오.](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)  
  
## <a name="see-also"></a>참고 항목  
 [링크 요구](/dotnet/framework/misc/link-demands)   
 [데이터 및 모델링](/dotnet/framework/data/index)