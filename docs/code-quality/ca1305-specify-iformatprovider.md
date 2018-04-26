---
title: 'CA1305: IFormatProvider를 지정하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SpecifyIFormatProvider
- CA1305
helpviewer_keywords:
- CA1305
- SpecifyIFormatProvider
ms.assetid: fb34ed9a-4eab-47cc-8eef-3068a4a1397e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: da4125a87ea7fe1576834dacc14af9a1a1861206
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1305-specify-iformatprovider"></a>CA1305: IFormatProvider를 지정하십시오.
|||
|-|-|
|TypeName|SpecifyIFormatProvider|
|CheckId|CA1305|
|범주|Microsoft.Globalization|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 메서드 또는 생성자 호출 허용 하는 오버 로드가 있는 하나 이상의 멤버는 <xref:System.IFormatProvider?displayProperty=fullName> 매개 변수를 메서드 또는 생성자는 오버 로드를 호출 하지 않습니다는 <xref:System.IFormatProvider> 매개 변수입니다. 이 규칙에 대 한 호출을 무시 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 무시로 설명 된 방법의 <xref:System.IFormatProvider> 매개 변수 및 또한 다음 메서드:

-   <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>

-   <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=fullName>

-   <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>

## <a name="rule-description"></a>규칙 설명
 경우는 <xref:System.Globalization.CultureInfo?displayProperty=fullName> 또는 <xref:System.IFormatProvider> 개체가 제공 되지 않으면, 오버 로드 된 멤버에서 제공 되는 기본값 모든 로캘에서 원하는 효과 없을 수 있습니다. 또한 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 멤버 기본 culture를 선택 하 고 코드에 대 한 올바르지 않을 수 있다는 가정 하에 따라 서식 지정 합니다. 을 코드가 시나리오에 대해 예상 대로 작동 하는지 확인 하기 위해 다음 지침에 따라 문화권 관련 정보를 제공 해야 합니다.

-   값은 사용자에 게 표시 됩니다, 현재 문화권을 사용 합니다. <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>을 참조하세요.

-   값을 저장 하 고 액세스 하 여 소프트웨어 (파일 또는 데이터베이스에 유지 됨)을 하는 경우 고정 문화권을 사용 합니다. <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>을 참조하세요.

-   값의 대상의 알 수 없는 경우 데이터 소비자 없거나 공급자가 문화권을 지정 합니다.

 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 의 인스턴스를 사용 하 여 지역화 된 리소스를 검색 하는 데에 사용 되는 <xref:System.Resources.ResourceManager?displayProperty=fullName> 클래스입니다.

 오버 로드 된 멤버의 기본 동작은 사용자의 요구에 적합 한, 경우에 코드를 자동으로 문서화 되 고 더 쉽게 유지 관리 하는 문화권별 오버 로드를 명시적으로 호출 하는 것이 좋습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하는 오버 로드를 사용 하 여 한 <xref:System.Globalization.CultureInfo> 또는 <xref:System.IFormatProvider> 하며 앞에 나열 된 지침에 따라 인수를 지정 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 기본 문화권/형식 공급자가 올바르게 선택 하 고 코드 유지 관리 되지 않는 한 중요 한 개발 우선 순위는 것이 확실 한 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제
 다음 예에서 `BadMethod` 이 규칙을 두 번 위반 합니다. `GoodMethod` 고정 문화권을 전달 하 여 첫 번째 위반이 해결 <xref:System.String.Compare%2A>, 현재 문화권을 전달 하 여 두 번째 위반을 해결 하 고 <xref:System.String.ToLower%2A> 때문에 `string3` 사용자에 게 표시 됩니다.

 [!code-csharp[FxCop.Globalization.CultureInfo#1](../code-quality/codesnippet/CSharp/ca1305-specify-iformatprovider_1.cs)]

## <a name="example"></a>예제
 다음 예제에서는 기본에서 현재 문화권의 효과 보여 줍니다. <xref:System.IFormatProvider> 으로 선택 되어 있는 <xref:System.DateTime> 유형입니다.

 [!code-csharp[FxCop.Globalization.IFormatProvider#1](../code-quality/codesnippet/CSharp/ca1305-specify-iformatprovider_2.cs)]

 이 예제의 결과는 다음과 같습니다.

 **1900 년 6 월 4 일 오후 12시 15분: 12**
**06/04/1900 12시 15분: 12**
## <a name="related-rules"></a>관련된 규칙
 [CA1304: CultureInfo를 지정하십시오.](../code-quality/ca1304-specify-cultureinfo.md)

## <a name="see-also"></a>참고 항목
[CultureInfo 클래스를 사용 하 여](/dotnet/standard/globalization-localization/globalization#Cultures)