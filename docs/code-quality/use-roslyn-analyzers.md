---
title: 사용 하 고 Visual Studio에서 Roslyn 분석기 구성 | Microsoft Docs
ms.date: 03/26/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 17758b8cd901a03e2ce4f93fe5dfcfdbe97eadab
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="configure-and-use-roslyn-analyzer-rules"></a>구성 하 고 Roslyn 분석기 규칙 사용

.NET 컴파일러 플랫폼 ("Roslyn") analyzer 규칙 또는 *진단*를 입력할 때 C# 또는 Visual Basic 코드를 분석 합니다. 각 진단의 프로젝트에 대 한 덮어쓸 수 있는 기본 심각도 억압 상태가 되었습니다. 이 문서에서는 설정 규칙 심각도, 위반을 억제 하 고 규칙 집합을 사용 하 여 설명 합니다.

## <a name="analyzers-in-solution-explorer"></a>솔루션 탐색기에서 분석기

대부분의 진단 분석기 유틸리티의 사용자 지정을 수행할 수 있습니다 **솔루션 탐색기**합니다. 경우 있습니다 [분석기 설치](../code-quality/install-roslyn-analyzers.md) NuGet 패키지로 **분석기** 노드가 아래에 표시는 **참조** 또는 **종속성** 의노드 **솔루션 탐색기**합니다. 확장 하면 **분석기**, 분석기 어셈블리 중 하나를 확장 하 고, 어셈블리의 모든 진단 정보를 표시 합니다.

![솔루션 탐색기에서 노드 분석기](media/analyzers-expanded-in-solution-explorer.png)

속성에 해당 설명 및 기본 심각도 포함 하는 diagnostic 볼 수는 **속성** 창. 속성을 보려면 마우스 오른쪽 단추로 클릭 규칙을 선택 **속성**, 또는 규칙을 선택 하 고 누릅니다 **Alt**+**Enter**합니다.

![속성 창에서 진단 속성](media/analyzer-diagnostic-properties.png)

진단에 대 한 온라인 설명서를 보려면 진단을 마우스 오른쪽 단추로 클릭 하 고 선택 **도움말 보기**합니다.

각 진단의 옆에 있는 아이콘 **솔루션 탐색기** 규칙 집합 편집기에서 여는 경우에 표시 되는 아이콘에 해당 합니다.

- 원 안에 "i" 나타냅니다는 [심각도](#rule-severity) 의 **정보**
- "!" 삼각형 나타냅니다는 [심각도](#rule-severity) 의 **경고**
- 원 안에 "x" 나타냅니다는 [심각도](#rule-severity) 의 **오류**
- 밝은 색 배경의 원 안에 "i" 나타냅니다는 [심각도](#rule-severity) 의 **숨김**
- 원 안에 있는 아래쪽 화살표에서 진단이 표시를 나타냅니다.

![솔루션 탐색기에서 진단 아이콘](media/diagnostics-icons-solution-explorer.png)

## <a name="rule-sets"></a>규칙 집합

A [규칙 집합](../code-quality/using-rule-sets-to-group-code-analysis-rules.md) 는 개별 진단에 대 한 심각도 및 표시 안 함 상태를 저장 하는 XML 파일입니다. 규칙 집합에는 단일 프로젝트에 적용 하 고 프로젝트에 여러 규칙 집합이 있을 수 있습니다. 활성 규칙 집합 편집기에서를 보려면 마우스 오른쪽 단추로 클릭는 **분석기** 노드에서 **솔루션 탐색기** 선택 **활성 규칙 집합 열기**합니다. 이 경우 처음으로 규칙에 액세스 하는 설정, 이라는 파일로 내보내집니다  *\<p r o j >.ruleset* 에 나타나고 프로젝트에 추가 **솔루션 탐색기**합니다.

> [!NOTE]
> 규칙 집합 (이진) 정적 코드 분석 및 Roslyn 분석기 규칙을 모두 포함 됩니다.

현재 규칙에는 프로젝트에 대 한 집합을 변경할 수는 **코드 분석** 프로젝트의 속성의 탭 합니다. 규칙 집합 선택은 **이 규칙 집합 실행** 드롭 다운 목록입니다. 규칙 집합에서 열 수도 있습니다는 **코드 분석** 속성 페이지를 선택 하 여 **열고**합니다.

## <a name="rule-severity"></a>규칙의 심각도

분석기 규칙의 심각도 구성할 수 있습니다 또는 *진단*경우 있습니다 [분석기 설치](../code-quality/install-roslyn-analyzers.md) NuGet 패키지로 합니다. 다음 표에서 진단에 대 한 심각도 옵션을 보여 줍니다.

|심각도|빌드 시간 동작|편집기 동작|
|-|-|-|
|Error|위반으로 표시 *오류* 에 **오류 목록** 명령줄에서 빌드 출력을을 유발할 빌드 실패 합니다.|코드에 잘못 된 구불구불한, 및 스크롤 막대에서 작은 빨간색 상자가 표시 된 빨간색으로 밑줄이 그어져 합니다.|
|경고|위반으로 표시 *경고* 에 **오류 목록** 명령줄에서 빌드 출력을 있고 빌드 실패를 일으키지 않습니다.|코드에 잘못 된 구불구불한, 및 스크롤 막대에서 작은 녹색 상자에 의해 표시 된 녹색으로 밑줄이 그어져 있습니다.|
|Info|위반으로 표시 *메시지* 에 **오류 목록**, 및 명령줄 빌드 출력에 전혀 없습니다.|코드에 잘못 된 구불구불한, 및 스크롤 막대에서 작은 회색 상자로 표시 된 회색으로 밑줄이 그어져 있습니다.|
|Hidden|비-사용자에 게 표시 합니다.|비-사용자에 게 표시 합니다. 그러나 진단 IDE 진단 엔진을 보고 됩니다.|
|없음|완전히 표시 되지 않습니다.|완전히 표시 되지 않습니다.|

또한 "다시 설정할 수 있습니다" 규칙의 심각도를 설정 하 여 **기본**합니다. 각 진단의에서 볼 수 있는 기본 심각도 **속성** 창.

다음 스크린 샷에서 서로 다른 세 가지 심각도 함께 코드 편집기에서 서로 다른 세 가지 진단 위반을 보여 줍니다. 스크롤 막대 오른쪽에 있는 작은 상자 뿐 아니라 구불구불한의 색을 확인 합니다.

![코드 편집기에서 오류, 경고 및 정보 위반](media/diagnostics-severity-colors.png)

다음 스크린샷은 동일한 세 가지 위반에 표시 되는 **오류 목록**:

![오류 목록에 위반 오류, 경고 및 정보](media/diagnostics-severities-in-error-list.png)

규칙의 심각도 변경할 수 있습니다 **솔루션 탐색기**, 또는  *\<p r o j >.ruleset* 에서규칙의심각도변경하고나면솔루션에추가된파일 **솔루션 탐색기**합니다.

![솔루션 탐색기에서 규칙 집합 파일](media/ruleset-in-solution-explorer.png)

### <a name="to-set-rule-severity-from-solution-explorer"></a>솔루션 탐색기에서 규칙의 심각도 설정 하려면

1. **솔루션 탐색기**를 확장 하 고 **참조** > **분석기** (**종속성**  >  **분석기** .NET Core 프로젝트에 대 한).

1. 에 대 한 심각도 설정 하려면 규칙을 포함 하는 어셈블리를 확장 합니다.

1. 선택한 규칙을 마우스 오른쪽 단추로 클릭 **규칙 집합 심각도 설정**합니다. 플라이 아웃 메뉴에서 심각도 옵션 중 하나를 선택 합니다.

   규칙에 대 한 심각도 활성 규칙 집합 파일에 저장 됩니다.

### <a name="to-set-rule-severity-in-the-rule-set-file"></a>규칙의 심각도 집합 파일 규칙을 설정 하려면

1. 열기 규칙 집합 파일에 두 번 클릭 하 여 **솔루션 탐색기**선택한 **활성 규칙 집합 열기** 의 오른쪽 클릭 메뉴는 **분석기** 노드를 선택 하 여 **열려** 에 **코드 분석** 프로젝트에 대 한 속성 페이지.

1. 포함 하는 어셈블리가 확장 하 여 규칙을 찾습니다.

1. 에 **동작** 열의 드롭 다운 목록을 열 수 값을 선택 하 고 목록에서 원하는 심각도 선택 합니다.

   ![편집기에에서 열려 있는 규칙 집합 파일](media/ruleset-file-in-editor.png)

## <a name="suppress-violations"></a>위반 표시 안 함

여러 가지 방법으로 규칙 위반을 표시 하지 않습니다.

- 모든 현재 위반을 표시 하지 않으려면 선택 **분석** > **코드 분석 실행 하 고 활성 문제를 표시 하지 않는** 메뉴 모음에서 합니다. 이 "기준 지정" 라고도 합니다.

- 진단 표시 하지 않으려면 **솔루션 탐색기**, 해당 심각도 설정 **None**합니다.

- 규칙 집합 편집기에서 진단을 표시 하지 않으려면 해당 이름 옆에 있는 확인란의 선택을 취소 하거나 설정 **동작** 를 **None**합니다.

- 코드 편집기에서 진단을 표시 하지 않으려면 위반 및 키를 눌러 코드 줄에 커서를 놓고 **Ctrl**+**합니다.** 열려는 **빠른 작업** 메뉴. 선택 **CAxxxx를 표시 하지 않는** > **원본의** 또는 **CAxxxx를 표시 하지 않는** > **억제 (suppression) 파일에**합니다.

   ![바로 가기 메뉴에서 진단 표시 안 함](media/suppress-diagnostic-from-editor.png)

- 진단 표시 하지 않으려면는 **오류 목록**오류, 경고 또는 메시지를 마우스 오른쪽 단추로 클릭 하 고 선택 **표시 안 함** > **소스** 또는 **표시 하지 않는** > **억제 (suppression) 파일에**합니다.

   - 선택 하는 경우 **소스**, **변경 내용 미리 보기** 대화 상자가 열리고 C#의 미리 보기가 표시 [#pragma 경고](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning) 또는 Visual Basic [#Disable경고](/dotnet/visual-basic/language-reference/directives/directives) 지시문 소스 코드에 추가 합니다.

      ![코드 파일에서 #pragma 경고를 추가 하는 미리 보기](media/pragma-warning-preview.png)

   - 선택 하는 경우 **억제 (suppression) 파일에**, **변경 내용 미리 보기** 대화 상자가 열리고의 미리 보기가 표시는 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 전역 비 표시 오류 파일에 추가 특성입니다.

      ![SuppressMessage 특성 억제 (suppression) 파일에 추가 하는 미리 보기](media/preview-changes-in-suppression-file.png)

   에 **변경 내용 미리 보기** 대화 상자에서 **적용**합니다.

> [!NOTE]
> .NET Core 프로젝트에 NuGet 분석기, 지정 된 프로젝트에 대 한 참조를 추가 하는 경우 해당 분석기는 자동으로 프로젝트에 추가 종속 너무 합니다. 예를 들어 종속 프로젝트에 단위 테스트 프로젝트는이 동작을 해제 하려면 private으로 NuGet 패키지를 표시는 *.csproj* 또는 *.vbproj* 참조 된 프로젝트의 파일:
>
> ```xml
> <PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers" Version="2.6.0" PrivateAssets="all" />
> ```

## <a name="see-also"></a>참고자료

- [Visual Studio에서 Roslyn 분석기 개요](../code-quality/roslyn-analyzers-overview.md)
- [Roslyn 분석기 버그 제출](https://github.com/dotnet/roslyn-analyzers/issues)
- [규칙 집합을 사용 하 여](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [코드 분석 경고 표시 안 함](../code-quality/in-source-suppression-overview.md)