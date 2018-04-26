---
title: 'CA1824: NeutralResourcesLanguageAttribute로 어셈블리 표시'
ms.date: 03/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: beaef23dd5b3047d1d65b90fdd984dfdedd7e145
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824: NeutralResourcesLanguageAttribute로 어셈블리 표시

|||
|-|-|
|TypeName|MarkAssembliesWithNeutralResourcesLanguage|
|CheckId|CA1824|
|범주|Microsoft.Performance|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

포함 된 어셈블리는 **ResX**-리소스를 기반으로 하지만 없는 <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> 적용 합니다.

## <a name="rule-description"></a>규칙 설명

<xref:System.Resources.NeutralResourcesLanguageAttribute> 특성은 응용 프로그램의 기본 문화권의 리소스 관리자에 게 알립니다. 기본 문화권의 리소스 응용 프로그램의 주 어셈블리에 포함 된 경우 및 <xref:System.Resources.ResourceManager> 가 기본 culture와 같은 문화권에 속해 있는 리소스를 검색 하는 <xref:System.Resources.ResourceManager> 주 어셈블리에 있는 리소스를 자동으로 사용 대신 위성 어셈블리를 검색 합니다. 이러한 일반적인 어셈블리 프로브 무시, 첫 번째 리소스를 로드 하 고 작업 집합을 줄일 수에 대 한 찾기 성능을 향상 시킬 수 있습니다.

> [!TIP]
> 참조 [리소스 패키징 및 배포](/dotnet/framework/resources/packaging-and-deploying-resources-in-desktop-apps) 프로세스는 <xref:System.Resources.ResourceManager> 리소스 파일에 대 한 검색을 사용 하 여 합니다.

## <a name="fix-violations"></a>위반 문제를 해결합니다

이 규칙 위반 문제를 해결 하는 어셈블리에 특성을 추가 하 고 중립 문화권의 리소스의 언어를 지정 합니다.

### <a name="to-specify-the-neutral-language-for-resources"></a>리소스에 대 한 중립 언어를 지정 하려면

1. **솔루션 탐색기**를 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 선택 **속성**합니다.

2. 선택 된 **응용 프로그램** 탭을 선택한 다음 선택 **어셈블리 정보**합니다.

   > [!NOTE]
   > 표준.NET 또는.NET Core 프로젝트를 프로젝트의 경우 선택 된 **패키지** 탭 합니다.

3. 언어를 선택는 **중립 언어** 또는 **어셈블리 중립 언어** 드롭 다운 목록입니다.

4. **확인**을 선택합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를에서 표시 하지 않을 경우합니다 그러나 시작 성능이 저하 될 수 있습니다.

## <a name="see-also"></a>참고자료

- <xref:System.Resources.NeutralResourcesLanguageAttribute>
- [데스크톱 응용 프로그램 (.NET)의 리소스](/dotnet/framework/resources/)
- [-리소스 문자열 해야 ca1703](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1701-복합 단어는 올바르게 대/소문자를 사용 해야 하는 리소스 문자열](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)