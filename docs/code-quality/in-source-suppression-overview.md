---
title: "SuppressMessage 특성을 사용 하 여 Visual Studio에서 코드 분석 경고 표시 안 함 | Microsoft Docs"
ms.custom: 
ms.date: 01/29/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.topic: article
helpviewer_keywords:
- source suppression, code analysis
- code analysis, source suppression
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: 4cd3800e082673e9478eb32c6ae5627eef4d7e81
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="suppressing-code-analysis-warnings"></a>코드 분석 경고 표시하지 않기

경고가 적용 가능 하지 않은 나타내기 위해 종종 유용 합니다. 이 팀 멤버가 코드를 검토 하 고 경고가 표시 될 수 있는지를 나타냅니다. 소스 비 표시 (ISS) 사용 하 여는 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 경고를 표시 하는 특성입니다. 경고를 생성 코드 세그먼트에 가까운 특성을 배치할 수 있습니다. 추가할 수 있습니다는 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 에 입력 하 여 특성을 소스 파일에 경고의 바로 가기 메뉴를 사용할 수 있습니다는 **오류 목록** 자동으로 추가 하려면.

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 컴파일 타임에 CODE_ANALYSIS 컴파일 기호가 정의 되어 있는 경우에 관리 코드 어셈블리의 IL 메타 데이터에 포함 된 조건부 특성입니다.

C + + /CLI를 CA 매크로 사용 하 여\_표시 안 함\_메시지 또는 CA\_GLOBAL\_특성을 추가 하는 헤더 파일에 SUPPRESS_MESSAGE 합니다.

> [!NOTE]
> 소스에서 메타 데이터를 실수로 전달 방지 하기 위해 릴리스 빌드에 소스 비 표시 오류는 사용 하지 있습니다. 또한, 소스에서 처리 비용 때문에 응용 프로그램의 성능이 저하 될 수 있습니다.

## <a name="suppressmessage-attribute"></a>SuppressMessage 특성

선택 하는 경우 **표시 안 함** 에서 코드 분석 경고의 컨텍스트 또는 오른쪽 클릭 메뉴에서는 **오류 목록**, 즉 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 또는 프로젝트의 전역 비 표시 오류 특성이 추가 됩니다 파일입니다.

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 특성 형식은 다음과 같습니다.

```vb
<Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")>
```

```csharp
[Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")]
```

```cpp
CA_SUPPRESS_MESSAGE("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")
```

특성의 속성은 다음과 같습니다.

- **규칙 범주** -규칙이 정의 되어 있는 범주입니다. 코드 분석 규칙 범주에 대 한 자세한 내용은 참조 [관리 코드 경고](../code-quality/code-analysis-for-managed-code-warnings.md)합니다.

- **규칙 Id** -규칙의 식별자입니다. 지원 규칙 식별자에 대 한 단기 및 장기 이름을 모두 포함 됩니다. 짧은 이름은 CAXXXX; 긴 이름은 CAXXXX:FriendlyTypeName입니다.

- **양쪽 맞춤** -메시지를 표시 하지 않기 위한 이유를 문서화 하는 데 사용 되는 텍스트입니다.

- **메시지 Id** -각 메시지에 대 한 문제의 고유 식별자입니다.

- **범위** -경고가 표시 되 고 대상입니다. 대상이 지정 되지 않은 경우 특성의 대상으로 설정 됩니다. 지원 되는 범위는 다음과 같습니다.

    - Module

    - 네임스페이스

    - 리소스

    - 형식

    - 멤버

- **대상** -경고가 표시 되 고 대상을 지정 하는 데 사용 하는 식별자입니다. 정식 항목 이름을 포함 해야 합니다.

## <a name="suppressmessage-usage"></a>SuppressMessage 사용

수준에서 코드 분석 경고는 표시 되지 않습니다는 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 특성은 적용 됩니다. 예를 들어, 어셈블리, 모듈, 형식, 멤버, 또는 매개 변수 수준에서 특성을 적용할 수 있습니다. 이 목적은 코드를 억제 (suppression) 정보를 위반이 발생 합니다.

일반적인 형태의 억제 (suppression) 규칙 범주 및 규칙 이름에 대 한 선택적 읽을 표현이 포함 하는 규칙 식별자를 포함 합니다. 예:

`[SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`

소스에서 메타 데이터 최소화 엄격한 성능상의 이유로 인 규칙 이름을 생략할 수 있습니다. 규칙 범주와 규칙 ID는 충분히 고유한 규칙 식별자를 구성 합니다. 예:

`[SuppressMessage("Microsoft.Design", "CA1039")]`

유지 관리 용이성을 위해 규칙 이름을 생략 권장 되지 않습니다.

## <a name="suppressing-selective-violations-within-a-method-body"></a>메서드 본문 내에서 선택적 위반을 억제합니다.

비 표시 특성 메서드에 적용할 수 있지만 메서드 본문 내에서 형식을 포함할 수 없습니다. 즉, 특정 규칙의 모든 위반 추가 하는 경우 표시 되지 않습니다는 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 특성을 메서드에 합니다.

경우에 따라 향후 코드를 자동으로 코드 분석 규칙에서 제외 되지 않습니다 수 있도록 예제에 대 한 위반의 특정 인스턴스를 표시 하지 않을 수 있습니다. 특정 코드 분석 규칙을 사용 하면 사용 하 여이 작업을 수행할 수 있도록는 `MessageId` 의 속성은 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 특성입니다. 레거시 규칙 (지역 변수 또는 매개 변수) 특정 기호 관련 위반에 대 한 일반적으로 `MessageId` 속성입니다. [CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md) 은 이러한 규칙의 예입니다. 그러나 실행 코드 (비 기호)에 위반에 대 한 레거시 규칙을 고려 하지 않는 `MessageId` 속성입니다. 또한 Roslyn 분석기 고려 하지 않는 `MessageId` 속성입니다.

특정 기호는 규칙 위반을 표시 하지 않으려면에 대 한 기호 이름을 지정는 `MessageId` 의 속성은 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 특성입니다. 다음 예제에서는 두 개의 위반을 사용 하 여 코드 [CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md)&mdash;에 대 한 하나는 `name` 변수 되 고 다른 하나는 `age` 변수입니다. 에 대 한 위반만는 `age` 기호가 표시 되지 않습니다.

```vb
Public Class Animal
    Dim age As Integer
    Dim name As String

    <CodeAnalysis.SuppressMessage("Microsoft.Maintainability", "CA1500:VariableNamesShouldNotMatchFieldNames", MessageId:="age")>
    Sub PrintInfo()
        Dim age As Integer = 5
        Dim name As String = "Charlie"

        Console.WriteLine("Age {0}, Name {1}", age, name)
    End Sub

End Class
```

```csharp
public class Animal
{
    int age;
    string name;

    [System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Maintainability", "CA1500:VariableNamesShouldNotMatchFieldNames", MessageId = "age")]
    private void PrintInfo()
    {
        int age = 5;
        string name = "Charlie";

        Console.WriteLine($"Age {age}, Name {name}");
    }
}
```

## <a name="generated-code"></a>생성 된 코드

관리 코드 컴파일러 및 일부 타사 도구에는 코드를 빠르게 개발을 용이 하 게 하려면 코드를 생성 합니다. 소스 파일에 표시 되는 컴파일러에서 생성 된 코드는 일반적으로 기본적으로 `GeneratedCodeAttribute` 특성입니다.

코드 분석 경고 및 생성 된 코드에 대 한 오류를 표시 하지 않을 것인지를 선택할 수 있습니다. 이러한 경고 및 오류를 표시 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 생성 된 코드에 대 한 경고 표시 안 함](../code-quality/how-to-suppress-code-analysis-warnings-for-generated-code.md)합니다.

> [!NOTE]
> 코드 분석에서 무시 `GeneratedCodeAttribute` 전체 어셈블리 또는 단일 매개 변수 중 하나에 적용 된 경우.

## <a name="global-level-suppressions"></a>Global 수준 비 표시 오류

관리 코드 분석 도구는 검사 `SuppressMessage` 어셈블리, 모듈, 형식, 멤버 또는 매개 변수 수준에서 적용 되는 특성입니다. 리소스와 네임 스페이스에 대해 위반을 발생 시킵니다. 이러한 위반의 전역 수준에서 적용 해야 하 고 범위가 한정 되 고 대상으로 합니다. 예를 들어 다음과 같은 메시지가 표시는 네임 스페이스 위반을 하지 않습니다.

`[module: SuppressMessage("Microsoft.Design", "CA1020:AvoidNamespacesWithFewTypes", Scope = "namespace", Target = "MyNamespace")]`

> [!NOTE]
> 네임 스페이스 범위와 함께 경고를 표시 하지 않는 네임 스페이스 자체에 대 한 경고를 표시 하지 않습니다. 네임 스페이스 내의 형식에 대 한 경고를 숨기지는 않습니다.

모든 비 표시 오류는 명시적 범위를 지정 하 여 표현할 수 있습니다. 이러한 비 표시이 오류는 전역 수준에서 활성화 되어야 합니다. 형식을 데코레이팅하여 구성원 수준 억제 (suppression)를 지정할 수 없습니다.

Global 수준 비 표시 오류는를 명시적으로 제공 되는 사용자 소스에 매핑되지 않는 컴파일러에서 생성 된 코드를 참조 하는 메시지를 표시 하지 않는 유일한 방법입니다. 예를 들어 다음 코드는 컴파일러에서 내보낸 생성자에 대 한 위반을 표시 하지 않습니다.

`[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="Microsoft.Tools.FxCop.Type..ctor()")]`

> [!NOTE]
> `Target`정규화 된 항목 이름 항상 포함 됩니다.

## <a name="global-suppression-file"></a>전역 억제 (suppression) 파일

전역 비 표시 오류 파일은 전역 수준 비 표시 오류 또는 대상을 지정 하지 않는 비 표시 오류 중 하나인 비 표시 오류를 유지 관리 합니다. 예를 들어 어셈블리 수준 위반에 대해가이 파일에 저장 됩니다. 또한 일부 ASP.NET 비 표시 오류 프로젝트 수준 설정을 뒤 폼 코드에 사용할 수 없기 때문에이 파일에 저장 됩니다. 전역 억제 (suppression) 파일을 만들고 선택 하는 처음으로 프로젝트에 추가 **프로젝트 억제 (suppression) 파일에서** 옵션의는 **표시 안 함** 명령에 **오류 목록**창.

## <a name="see-also"></a>참고 항목

<xref:System.Diagnostics.CodeAnalysis>