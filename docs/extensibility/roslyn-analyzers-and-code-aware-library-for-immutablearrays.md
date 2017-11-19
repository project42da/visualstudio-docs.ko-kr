---
title: "Roslyn 분석기 및 코드 인식 ImmutableArrays 라이브러리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b0afa22-3fca-4d59-908e-352464c1d903
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9b33516bd013f744813b2fdb357f224bcb0d9822
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="roslyn-analyzers-and-code-aware-library-for-immutablearrays"></a>Roslyn 분석기 및 코드 인식 ImmutableArrays 라이브러리

[.NET 컴파일러 플랫폼](https://github.com/dotnet/roslyn) ("Roslyn")를 사용 하면 코드 인식 라이브러리를 만들 수 있습니다.  가장 좋은 방법은 또는 오류를 방지 하려면 코드 인식 라이브러리는 라이브러리를 사용할 수 있습니다 (Roslyn 분석기) 도구 및 기능을 사용할 수 있습니다.  이 항목에서는 사용할 때 일반적인 오류를 catch 하는 실제 세계 Roslyn 분석기를 빌드하는 방법을 보여 줍니다는 [System.Collections.Immutable](https://www.nuget.org/packages/System.Collections.Immutable) NuGet 패키지 합니다.  이 예제에는 분석기에 의해 발견 된 코드 문제에 대 한 코드 수정을 제공 하는 방법을 보여 줍니다.  사용자 코드 수정 Visual Studio 전구 UI에서에서 볼 수 있으며 코드에 대 한 수정 프로그램이 자동으로 적용할 수 있습니다.

## <a name="getting-started"></a>시작

이 예제를 빌드하려면 다음이 필요 합니다.

* Visual Studio 2015 (한 Express Edition 아님) 또는 이후 버전입니다.  무료 사용할 수 있습니다 [Visual Studio Community Edition](https://www.visualstudio.com/products/visual-studio-community-vs)
* [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  확인할 수도 있습니다, Visual Studio를 설치 하는 경우 일반적인 도구는 동시에 SDK를 설치 하려면 아래에서 Visual Studio 확장성 도구입니다.  Visual Studio를 이미 설치한 경우 또한이 SDK 설치할 수 있습니다이 기본 메뉴로 이동 하 여 **파일 &#124; 새로 만들기 &#124; 프로젝트...** 왼쪽된 탐색 창에서 C#을 선택 하 고 다음 확장을 선택 합니다.  선택 하는 경우는 "**Visual Studio 확장성 도구 설치**" 이동 경로 탐색 프로젝트 템플릿을 묻는 다운로드 하 여 SDK를 설치 합니다.
* [.NET 컴파일러 플랫폼 ("Roslyn") SDK](http://aka.ms/roslynsdktemplates)합니다.  주 메뉴에 이동 하 여이 SDK를 설치할 수도 있습니다 **파일 &#124; 새로 만들기 &#124; 프로젝트...** 선택, **C#** 왼쪽된 탐색 창 고에서 다음 **확장성**합니다.  선택 하는 경우 "**.NET 컴파일러 플랫폼 SDK 다운로드**" 이동 경로 탐색 프로젝트 템플릿을 묻는 다운로드 하 여 SDK를 설치 합니다.  이 SDK에 포함 되어는 [Roslyn 구문 시각화 도우미](https://github.com/dotnet/roslyn/wiki/Syntax%20Visualizer)합니다.  코드 모델 유형을 파악이 매우 유용한 도구를 사용 하면 찾아야 프로그램 분석기.  분석기 인프라 코드만 필요한 경우에 실행 하 고 관련 코드 분석에 집중할 수 있도록 특정 코드 모델 유형에 대 한 코드를 호출 합니다.

## <a name="whats-the-problem"></a>문제가 뭔가요?

ImmutableArray에 라이브러리를 제공 가정해 보세요 (예를 들어 <xref:System.Collections.Immutable.ImmutableArray%601?displayProperty=fullName>)를 지원 합니다.  C# 개발자는.NET 배열이 포함 된 경험이 있습니다.  그러나 ImmutableArrays 및 최적화 기술을 구현에서 사용 되는 특성으로 인해 C# 개발자 intuitions 하면 사용자가 라이브러리의 끊어진된 코드를 작성 하려면 아래에 설명 된 대로.  또한 사용자가 사용 되는 Visual Studio.net에서 품질 경험이 런타임이 될 때까지 해당 오류가 표시 되지 않습니다.

사용자는 다음과 같은 코드를 작성 익숙합니다.

```csharp
var a1 = new int[0];
Console.WriteLine("a1.Length = { 0}", a1.Length);
var a2 = new int[] { 1, 2, 3, 4, 5 };
Console.WriteLine("a2.Length = { 0}", a2.Length);
```

만드는 코드의 다음 줄은 채워지는에 빈 배열 및 컬렉션 이니셜라이저 구문을 사용 하는 C# 개발자에 게 친숙 하 게 합니다.  그러나 코드는 ImmutableArray가 런타임 시 충돌 동일한 작성:

```csharp
var b1 = new ImmutableArray<int>();
Console.WriteLine("b1.Length = { 0}", b1.Length);
var b2 = new ImmutableArray<int> { 1, 2, 3, 4, 5 };
Console.WriteLine("b2.Length = { 0}", b2.Length);
```

첫 번째 오류 구조체를 사용 하 여 기본 데이터 저장소를 래핑하는 ImmutableArray 구현 때문입니다. 구조체는 매개 변수 없는 생성자가 있어야 있도록 `default(T)` 식은 모든 구조체를 반환할 수 있습니다 0 또는 null 멤버입니다.  코드에 액세스할 때 `b1.Length`는 런타임에 null ImmutableArray 구조체에 기본 저장소 배열이 없습니다 있기 때문에 오류를 역참조 합니다.  빈 ImmutableArray를 만들 수 있는 올바른 방법은 `ImmutableArray<int>.Empty`합니다.

컬렉션 이니셜라이저가 있는 오류 ImmutableArray.Add 메서드가 호출 될 때마다 새 인스턴스를 반환 하기 때문에 발생 합니다.  ImmutableArrays 변경 되지 않으면 새 요소를 추가 하면, 때문에 돌아갈 있습니다는 새 ImmutableArray 개체 (이전에 기존 ImmutableArray와 성능상의 이유로 저장소를 공유할 수 있습니다).  때문에 `b2` 호출 하기 전에 첫 번째 ImmutableArray를 가리키는 `Add()` 다섯 번 `b2` 기본값 ImmutableArray입니다.  오류를 역참조 호출 길이에 null이 충돌 합니다.  사용 하는 추가 수동으로 호출 하지 않고는 ImmutableArray를 초기화 하는 올바른 방법은 `ImmutableArray.CreateRange(new int[] {1, 2, 3, 4, 5})`합니다.

## <a name="finding-relevant-syntax-node-types-to-trigger-your-analyzer"></a>프로그램 분석기를 트리거할 관련 구문 노드 형식 찾기

 분석기 작성을 시작 하려면 먼저 파악에 대 한 확인 해야 하는 어떤 유형의 SyntaxNode 합니다. 구문 시각화 메뉴에서 시작 **보기 &#124; 다른 창 &#124; Roslyn 구문 시각화 도우미**합니다.

편집기의 캐럿 선언 하는 줄에 배치 `b1`합니다.  구문 시각화 도우미에는 표시 표시 됩니다는 `LocalDeclarationStatement` 구문 트리의 노드입니다.  이 노드에 `VariableDeclaration`, 다시는 `VariableDeclarator`, 다시는 `EqualsValueClause`, 마지막는 `ObjectCreationExpression`합니다.  시각화 도우미 구문 트리 노드를 클릭 해당 노드에 표시 되는 코드를 표시 하도록 편집기 창에서 구문 강조 표시 됩니다.  SyntaxNode 하위 형식의 이름이 C# 문법에 사용 되는 이름과 일치 합니다.

## <a name="creating-the-analyzer-project"></a>분석기 프로젝트 만들기

주 메뉴에서 선택 **파일 &#124; 새로 만들기 &#124; 프로젝트...** .  **새 프로젝트** 대화 아래에서 **C#** 프로젝트 왼쪽된 탐색 모음에서 확장성을 선택 하 고 오른쪽 창에서 선택 된 **를 사용 하 여 코드 수정** 프로젝트 서식 파일입니다.  이름을 입력 하 고 대화 상자를 확인 합니다.

서식 파일 DiagnosticAnalyzer.cs 파일을 엽니다.  해당 편집기 버퍼 탭을 선택 합니다.  이 파일에는 분석기 클래스 (구성 프로젝트 이름에서 지정한)에서 파생 된 `DiagnosticAnalyzer` (Roslyn API 유형).  새 클래스에는 `DiagnosticAnalyzerAttribute` 프로그램 분석기 선언은 컴파일러 검색 하 여 분석기를 로드 하는 C# 언어와 관련이 있습니다.

```csharp
[DiagnosticAnalyzer(LanguageNames.CSharp)]
public class ImmutableArrayAnalyzerAnalyzer : DiagnosticAnalyzer
{}
```

C# 코드를 대상으로 하는 Visual Basic을 사용 하는 분석기를 구현할 수 있으며 반대의 합니다.  언어가 하나 또는 둘 다 사용자 분석기를 대상으로 하는지 여부를 선택할 수 DiagnosticAnalyzerAttribute에 더 유용 합니다.  언어의 자세한 모델링을 필요로 하는 보다 정교한 분석기 대상으로 지정할 수 하나의 언어만 합니다.  분석기, 예를 들어만 확인 하면 형식 이름 또는 공용 멤버 이름, Roslyn Visual Basic 및 C#에서는 공용 언어 모델을 사용할 수 있습니다.  예를 들어 FxCop 경고 클래스를 구현 한다는 <xref:System.Runtime.Serialization.ISerializable>, 있지만 클래스가 없는 <xref:System.SerializableAttribute> 특성 언어 독립적 이며 Visual Basic 및 C# 코드에 대해 작동 합니다.

## <a name="initalizing-the-analyzer"></a>초기화 하는 분석기

 약간 아래로 스크롤는 `DiagnosticAnalyzer` 보려면 클래스는 `Initialize` 메서드.  컴파일러는 분석기를 활성화 하는 경우이 메서드를 호출 합니다.  메서드를 사용 하며는 `AnalysisContext` 컨텍스트 정보를 분석 하려면 코드의 종류에 대 한 이벤트에 대 한 콜백을 등록 하 여 분석기를 사용할 수 있는 개체입니다.

```csharp
public override void Initialize(AnalysisContext context) {}

```

이 컨텍스트에서 메서드 및 형식"." 새 줄을 엽니다 IntelliSense 완성 목록을 확인 합니다.  여러 완성 목록에서 볼 수 `Register...` 다양 한 종류의 이벤트를 처리 하는 방법입니다.  예를 들어 첫 번째 `RegisterCodeBlockAction`, 중괄호 사이 코드는 일반적으로 블록에 대 한 코드를 다시 호출 합니다.  블록에 대 한 등록도 다시 호출 코드에는 필드, 속성에 제공 된 값 또는 선택적 매개 변수 값의 이니셜라이저에 대 한 합니다.

또 다른 예로, `RegisterCompilationStartAction`를 위해 여러 위치를 통해 상태를 수집 해야 하는 경우에 유용 컴파일의 시작 부분에 코드를 다시 호출 합니다.  데이터 구조를 예를 들어, 수집을 사용 하는 모든 기호를 만들고 일부 구문 또는 기호에 대 한 사용자 분석기가 다시 호출 될 때마다 데이터 구조에서 각 위치에 대 한 정보를 저장할 수 있습니다.  컴파일 종료로 인해 다시 호출 하는 경우 저장, 예를 들어 있는 기호를 각각 사용 하 여 코드를 보고 하기 위해 모든 위치를 분석할 수 있습니다 `using` 문.

사용 하는 **구문 시각화 도우미**, 컴파일러는 ObjectCreationExpression 처리 될 때 호출 될 것인지를 알아보았습니다.  이 코드를 사용 하 여 콜백을 설정 하려면:

```csharp
context.RegisterSyntaxNodeAction(c => AnalyzeObjectCreation(c),
                                 SyntaxKind.ObjectCreationExpression);
```

구문 노드가 및 개체 생성 구문 노드만 대 한 필터에 대 한 등록합니다.  규칙에 따라 분석기 작성자도 상태 비저장 분석기를 유지할 수 있는 작업을 등록 하는 경우 람다를 사용 합니다.  Visual Studio 기능을 사용할 수 **사용법에서 생성** 만들려는 `AnalyzeObjectCreation` 메서드.  이 올바른 유형의 컨텍스트 매개 변수를 생성 하면 너무 합니다.

## <a name="setting-properties-for-users-of-your-analyzer"></a>프로그램 분석기의 사용자에 대 한 속성을 설정합니다.

되도록 사용자 분석기 Visual Studio UI에서 적절 하 게를 찾아서 여 분석기를 식별 하는 코드의 다음 줄을 수정:

```csharp
internal const string Category = "Naming";
```

Change `"Naming"` to `"API Guidance"`.

다음 찾기 및 열기는 `Resources.resx` 파일 사용 하 여 프로젝트에는 **솔루션 탐색기**합니다.  분석기, 제목, 등에 대 한 설명에 넣을 수 있습니다.  이러한 모든 값을 변경할 수 `"Don't use ImmutableArray<T> constructor"` 지금은 합니다.  문자열 인수 ({0}, {1 \} 등), 문자열에서 서식 지정을 넣을 수 있습니다를 호출할 때 이상 `Diagnostic.Create()`, 제공할 수 있습니다는 `params` 전달할 인수로 이루어진 배열입니다.

## <a name="analyzing-an-object-creation-expression"></a>개체 생성 식을 분석

`AnalyzeObjectCreation` 메서드가 다른 유형의 코드 분석기 프레임 워크에서 제공 하는 컨텍스트를 사용 합니다.  Initialize 메서드 `AnalysisContext` 프로그램 분석기를 설정 하려면 작업 콜백을 등록할 수 있습니다.  `SyntaxNodeAnalysisContext`, 예를 들어는 `CancellationToken` 주위 성공할 수 있습니다.  편집기에 입력을 시작 작업을 저장 하 고 성능을 개선할 수 있는 실행 중인 분석기 Roslyn 취소 됩니다.  이 컨텍스트에서 또 다른 예로, 개체 생성 구문 노드를 반환 하는 노드 속성을 있습니다.

구문 노드 작업을 필터링 유형 가정할 수 있는 노드를 가져옵니다.

```csharp
var objectCreation = (ObjectCreationExpressionSyntax)context.Node;
```

### <a name="launching-visual-studio-with-your-analyzer-the-first-time"></a>처음으로 사용자 분석기를 통해 Visual Studio를 시작합니다.

구축 하 고 프로그램 분석기를 실행 하 여 Visual Studio를 시작 (키를 눌러 **F5**).  프로젝트를 시작 하기 때문에 **솔루션 탐색기** 는 VSIX 프로젝트 코드 및 VSIX를 코드 빌드를 실행 하 고 해당 VSIX 설치 되어 있는 Visual Studio를 시작 합니다.  이러한 방식으로 Visual Studio를 시작 하면 Visual Studio의 주 사용은 영향을 받지 테스트 인스턴스 분석기를 빌드하는 동안 있도록 고유한 레지스트리 하이브를 시작 합니다.  처음에이 방법으로 시작할 때 Visual Studio 하면 처음 시작할 때 Visual Studio 설치 후와 유사한 여러 초기화가 수행 하지 않습니다.

콘솔 프로젝트를 만들고 콘솔 응용 프로그램 Main 메서드로 배열 코드를 입력 합니다.

```csharp
var b1 = new ImmutableArray<int>();
Console.WriteLine("b1.Length = {0}", b1.Length);
var b2 = new ImmutableArray<int> { 1, 2, 3, 4, 5 };
Console.WriteLine("b2.Length = {0}", b2.Length);
```

사용 하 여 코드의 줄 `ImmutableArray` 을 변경할 수 없는 NuGet 패키지를 가져오고 추가 해야 하기 때문에 물결선을 포함 한 `using` 문을 코드에 있습니다.  프로젝트 노드를 오른쪽 포인터 단추를 눌러는 **솔루션 탐색기** 선택 **NuGet 패키지 관리...** .  NuGet 관리자에서 검색 상자에 "변경"을 입력 하 고 "System.Collections.Immutable" 항목 선택 ("Microsoft.Bcl.Immutable"을 선택 하지 않으면) 하면 왼쪽 창과 오른쪽 창에서 [설치] 단추를 누르십시오.  프로젝트 참조에 대 한 참조를 추가 패키지를 설치 합니다.

아래의 빨간색 물결선을 계속 나타나면 `ImmutableArray`, 해당 식별자 및 키를 눌러에 캐럿 배치 **CTRL +.** (마침표) 제안 된 수정 프로그램 메뉴를 표시 하 고 적절 한 추가 하도록 선택한 `using` 문.

**모두 저장 하 고 닫습니다** 계속 하려면 깨끗 한 상태로 하 게 지금은 Visual Studio의 두 번째 인스턴스.

## <a name="finishing-the-analyzer-using-edit-and-continue"></a>편집 하며 계속 하기는 분석기를 사용 하 여 마치는 중

Visual Studio의 첫 번째 인스턴스에서 시작 부분에 중단점을 설정 하면 `AnalyzeObjectCreation` 메서드 키를 눌러 **F9** 첫 번째 줄에 캐럿 합니다.

사용 하 여 다시 프로그램 분석기를 시작할 **F5**, Visual Studio의 두 번째 인스턴스에서 마지막으로 만든 콘솔 응용 프로그램 다시 여세요.

Roslyn 컴파일러 개체 생성 식을 보여 준다는 사실을 알았습니다 프로그램 분석기에 대 한 호출 하기 때문에 중단점에서 Visual Studio의 첫 번째 인스턴스를 반환 합니다.

**개체 만들기 노드를 가져옵니다.** 설정 하는 선 위에 단계는 `objectCreation` 키를 눌러 변수 **F10**, 및는 **직접 실행 창** 식을 계산할 `"objectCreation.ToString()"`합니다.  변수를 가리키는 구문 노드는 코드를 참조 `"new ImmutableArray<int>()"`, 방금 무엇 원하는 합니다.

**ImmutableArray를 가져올 < T\> 형식 개체입니다.** 생성 될 형식이 ImmutableArray 인지 확인 해야 합니다.  먼저,이 형식을 나타내는 개체를 가져옵니다.  의미 체계 모델을 사용 하 여 정확 하 게 올바른 형식이 고 tostring ()에서 문자열을 비교 하지 않는 위해 형식을 검사 하는 경우.  함수의 끝에 코드의 다음 줄을 입력 합니다.

```csharp
var immutableArrayOfTType =
    context.SemanticModel
           .Compilation
           .GetTypeByMetadataName("System.Collections.Immutable.ImmutableArray`1");
```

Backquotes (')와 메타 데이터와 제네릭 매개 변수의 수에 제네릭 형식을 지정합니다.  이 표시 되지 않으면 "... 때문 ImmutableArray\<T > "에서 메타 데이터 이름입니다.

의미 체계 모델 기호, 데이터 흐름, 변수 수명에 대해 질문할 수 있는 여러 유용한 동작이 있습니다.  Roslyn 다양 한 이유로 엔지니어링 (성능, 잘못 된 코드, 등을 모델링 합니다.) 의미 체계 모델에서 구문 노드를 구분 합니다.  컴파일 모델을 정확 하 게 비교에 대 한 참조에 포함 된 정보를 조회 하려면 원하는 합니다.

편집기 창 왼쪽에 노란색 실행 파일에 대 한 포인터를 끌 수 있습니다.  설정 하는 줄 위로 끌는 `objectCreation` 변수 및 사용 하 여 코드의 새 행 건너뛰기 **F10**합니다.  변수 위에 마우스 포인터를 가져가면 `immutableArrayOfType`, 의미 체계 모델의 정확한 형식을 있음을 표시 합니다.

**개체 생성 식의 형식을 가져옵니다.** "Type"은이 문서에는 몇 가지 방법이 사용 되지만이 경우 "새 Foo" 있을 경우 Foo의 모델을 사용 하려면 필요한 식입니다.  ImmutableArray 인지 개체 생성 식의 형식을 가져오기 위해 필요한\<T > 형식입니다.  개체 생성 식에 형식 기호 (ImmutableArray)에 대 한 기호 정보를 얻으려면 의미 체계 모델을 다시 사용 합니다.  함수의 끝에 코드의 다음 줄을 입력 합니다.

```csharp
var symbolInfo = context.SemanticModel.GetSymbolInfo(objectCreation.Type).Symbol as INamedTypeSymbol;
```

프로그램 분석기 편집기 버퍼에 불완전 하거나 잘못 된 코드를 처리 하기 때문에 (예를 들어, 누락 된 `using` 문)을 검사 해야 `symbolInfo` 되 고 `null`합니다.  분석을 마치는 기호 정보 개체에서 얻으려면 명명 된 형식 (INamedTypeSymbol)를 해야 합니다.

**형식을 비교 합니다.** 형식에 관계 (개방형 제네릭 형식)에서 생성 되는 기호 정보를 쿼리할 하 고 해당 결과를 비교 우리가 찾고, t는 개방형 제네릭 형식 코드의 형식을 구체적인 제네릭 형식이 없어 `immutableArrayOfTType`합니다.  메서드의 끝에 다음을 입력 합니다.

```csharp
if (symbolInfo != null &&
    symbolInfo.ConstructedFrom.Equals(immutableArrayOfTType))
{}
```

**진단을 보고 합니다.** 진단을 보고 매우 쉽습니다.  Initialize 메서드 앞에 정의 되는 프로젝트 템플릿에에서 만들어진 규칙을 사용 하는 경우.  이 경우 코드에서 오류 이기 때문에 대체 하는 규칙을 초기화 하는 줄을 변경할 수 있습니다 `DiagnosticSeverity.Warning` (녹색 표시 선은)와 `DiagnosticSeverity.Error` (빨간색 물결 기호).  규칙의 나머지 연습 시작 편집한 리소스를 초기화 합니다.  오류 표시선 개체 생성 식 형식 지정의 위치에 대 한 위치를 보고 해야 합니다.  이 코드를 입력의 `if` 블록:

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, objectCreation.Type.GetLocation()));
```

함수 (아마도 서식이 다르게 지정) 다음과 같이 표시 됩니다.

```csharp
private void AnalyzeObjectCreation(SyntaxNodeAnalysisContext context)
{
    var objectCreation = (ObjectCreationExpressionSyntax)context.Node;
    var immutableArrayOfTType =
        context.SemanticModel
               .Compilation
               .GetTypeByMetadataName(
                   "System.Collections.Immutable.ImmutableArray`1");
    var symbolInfo = context.SemanticModel.GetSymbolInfo(objectCreation.Type).Symbol as
        INamedTypeSymbol;
    if (symbolInfo != null &&
        symbolInfo.ConstructedFrom.Equals(immutableArrayOfTType))
    {
        context.ReportDiagnostic(
            Diagnostic.Create(Rule, objectCreation.Type.GetLocation()));
    }
}
```

분석기 작업 (파악 하 고 Visual Studio의 첫 번째 인스턴스를 반환 하지) 있도록 중단점을 제거 합니다.  메서드 및 키를 눌러 시작 부분에 실행 파일에 대 한 포인터를 끌어 **F5** 실행을 계속 합니다.  Visual Studio의 두 번째 인스턴스를 다시 전환 하는 경우 컴파일러가 시작 코드를 다시 검사 하 고 프로그램 분석기에 호출 됩니다.  아래의 물결 기호 볼 수 있습니다 `ImmutableType<int>`합니다.

## <a name="adding-a-code-fix-for-the-code-issue"></a>"코드 수정을" 코드 문제에 대 한 추가

시작 하기 전에 Visual Studio의 두 번째 인스턴스를 닫고 첫 번째 인스턴스의 (여기서 개발 하는 분석기) Visual Studio에서 디버깅을 중지 합니다.

**새 클래스를 추가 합니다.** 솔루션 탐색기에서 해당 프로젝트 노드 바로 가기 메뉴 (오른쪽 포인터 단추) use 하 고 새 항목을 추가 하려면 선택 합니다.  이라는 클래스를 추가 `BuildCodeFixProvider`합니다.  이 클래스에서 파생 해야 `CodeFixProvider`를 사용 해야 하 고 **CTRL +.** (마침표)를 추가 하는 올바른 코드 수정을 호출 `using` 문.  이 클래스는도로 주석을 추가 해야 `ExportCodeFixProvider` 특성 및 사용자를 추가 해야 합니다는 `using` 해결 하는 문에 `LanguageNames` 열거형입니다.  클래스 파일에 다음 코드와 함께 있어야 합니다.

```csharp
using Microsoft.CodeAnalysis;
using Microsoft.CodeAnalysis.CodeFixes;

namespace ImmutableArrayAnalyzer
{
    [ExportCodeFixProvider(LanguageNames.CSharp)]
    class BuildCodeFixProvider : CodeFixProvider
    {}

```

**파생 된 구성원을 스텁 합니다.** 이제는 식별자에 편집기의 캐럿을 배치 `CodeFixProvider` 누릅니다 **CTRL +.** (마침표)으로이 추상 기본 클래스에 대 한 구현 합니다.  사용자에 대 한 속성과 메서드를 생성합니다.

**속성을 구현 합니다.** 입력은 `FixableDiagnosticIds` 속성의 `get` 를 다음 코드로 본문:

```csharp
return ImmutableArray.Create(ImmutableArrayAnalyzerAnalyzer.DiagnosticId);
```

Roslyn 진단 종합 하 고 이러한 식별자를 단순히 문자열을 비교 하 여 수정 합니다.  프로젝트 템플릿을, 진단 ID를 생성 하 고 변경할 수 있습니다.  속성의 코드는 방금 분석기 클래스에서 ID를 반환합니다.

**RegisterCodeFixAsync 메서드 컨텍스트를 사용 합니다.** 컨텍스트는 중요 한 코드 수정 여러 진단에 적용 하거나 코드 줄에 둘 이상의 문제 수 합니다.  "컨텍스트가."를 입력 하는 경우 메서드 본문의 IntelliSense 완성 목록 안내해 몇 가지 유용한 멤버입니다.  CancellationToken 멤버를 수정 프로그램을 취소 하려는 항목 참조를 확인할 수 있습니다.  많은 유용한 멤버 및 프로젝트 및 솔루션 모델 개체에 액세스할 수 있습니다 하는 문서 멤버가 있습니다.  범위 구성원이 며 코드 위치의 끝에서 진단 보고 되는 시점을 지정 합니다.

**비동기 될 메서드를 만듭니다.** 가장 먼저 해야 할 되도록 생성 된 메서드 선언을 수정 되는 `async` 메서드.  추상 클래스에 대 한 구현에서는 스텁에 대 한 코드 수정을 포함 되지 않습니다는 `async` 메서드가 반환 하는 경우에 키워드는 `Task`합니다.

**구문 트리의 루트를 가져옵니다.** 변경 내용으로 새 구문 트리를 만드는 데 필요한 코드를 수정 하는 코드 수정을 만듭니다.  필요한는 `Document` 호출 컨텍스트에서 `GetSyntaxRootAsync`합니다.  알 수 없는 작업 디스크에서 파일을 가져오는, 구문 분석 하 고 Roslyn 코드 모델에 대 한 빌드를 포함 하 여, 구문 트리를 가져오기 위해 있기 때문에이 비동기 메서드이므로 합니다.  Visual Studio UI를 사용 하 여이 시간 동안 응답 해야 `async` 수 있도록 합니다.  다음 메서드에서 코드 줄을을 바꿉니다.

```csharp
var root = await context.Document
                        .GetSyntaxRootAsync(context.CancellationToken);
```

**문제가 있는 노드를 찾습니다.** 컨텍스트의 범위를 변경 해야 하는 코드를 되지 않을 수 있습니다 찾을 노드에 전달 합니다.  보고 된 진단 (여기서 오류 표시선 속한)의 형식 식별자에 대 한만 범위를 제공 하지만 전체 개체 생성 식 바꿔야 포함 하는 `new` 시작과 끝에 괄호 키워드입니다.  메서드에 다음 코드를 추가 합니다. (사용 및 **CTRL +.** 추가 하는 `using` 문을 `ObjectCreationExpressionSyntax`):

```csharp
var objectCreation = root.FindNode(context.Span)
                         .FirstAncestorOrSelf<ObjectCreationExpressionSyntax>();
```

**전구 UI에 대 한 수정 하 여 코드를 등록 합니다.** 코드 수정의 등록 하면 Visual Studio 전구 UI에 Roslyn 자동으로 연결 합니다.  최종 사용자가 사용할 수 표시 **CTRL +.** 프로그램 분석기를 나타내는 물결선는 잘못 된 경우 (마침표) `ImmutableArray<T>` 생성자 사용 합니다.  코드 수정 공급자만 실행 되므로 문제가 있을 때, 찾고 있던 개체 생성 식이 있는 가정할 수 있습니다.  컨텍스트 매개 변수에서 새 코드 수정을의 끝에 다음 코드를 추가 하 여 등록할 수 있습니다 `RegisterCodeFixAsync` 메서드:

```csharp
context.RegisterCodeFix(
            CodeAction.Create("Use ImmutableArray<T>.Empty",
                              c => ChangeToImmutableArrayEmpty(objectCreation,
                                                               context.Document,
                                                               c)),
            context.Diagnostics[0]);
```

식별자에는 편집기의 캐럿을 배치 해야 `CodeAction`를 사용 하 여 **CTRL +.** 적절 한 추가할 (마침표) `using` 이 형식에 대 한 문입니다.

그런 다음에 편집기의 캐럿을 배치는 `ChangeToImmutableArrayEmpty` 식별자를 사용 하 여 **CTRL +.** 이 메서드 스텁 생성에 다시.

이 마지막 코드 조각을 추가한 코드 수정을 전달 하 여 등록 한 `CodeAction` 와 발견 한 문제의 종류에 대 한 진단 ID입니다.  이 예제에서는 하나씩만 있기이 코드를 제공 하는 진단 ID 픽스, 진단 Id 배열의 첫 번째 요소를 방금 전달할 수 있도록 합니다.  만들 때는 `CodeAction`, 코드 수정 사항에 대 한 설명을 전구 UI를 사용 해야 하는 텍스트에 전달 합니다.  CancellationToken을 사용 하 고 새 문서를 반환 하는 함수에 전달할 수도 있습니다.  새 문서에 새 구문 트리를 호출 하는 패치가 적용 된 코드가 포함 된 `ImmutableArray.Empty`합니다.  이 코드 조각은 람다를 사용 하므로 objectCreation 노드와 컨텍스트의 문서를 통해 닫을 수 있습니다.

**새 구문 트리를 생성 합니다.** 에 `ChangeToImmutableArrayEmpty` 앞에서 생성 된 스텁 코드 줄을 입력 하는 메서드: `ImmutableArray<int>.Empty;`합니다.  구문 시각화 도우미 도구 창을 다시 볼 경우이 구문은 SimpleMemberAccessExpression 노드를 볼 수 있습니다.  즉,이 이렇게 하는 사항 구성 하 고 새 문서에 반환 합니다.

첫 번째 변경 `ChangeToImmutableArrayEmpty` 추가 하는 것 `async` 전에 `Task<Document>` 코드 생성기는 메서드를 async 수 가정할 수 있으므로 합니다.

방법에는 다음과 유사 하 여 본문에 다음 코드를 입력 합니다.

```csharp
private async Task<Document> ChangeToImmutableArrayEmpty(
    ObjectCreationExpressionSyntax objectCreation, Document document,
    CancellationToken c)
{
    var generator = SyntaxGenerator.GetGenerator(document);
    var memberAccess =
        generator.MemberAccessExpression(objectCreation.Type, "Empty");
    var oldRoot = await document.GetSyntaxRootAsync(c);
    var newRoot = oldRoot.ReplaceNode(objectCreation, memberAccess);
    return document.WithSyntaxRoot(newRoot);
}
```

편집기의 캐럿을 배치 해야 합니다는 `SyntaxGenerator` 식별자를 사용 하 여 **CTRL +.** 적절 한 추가할 (마침표) `using` 이 형식에 대 한 문입니다.

이 코드에서는 사용 `SyntaxGenerator`, 새 코드를 생성 하기 위해이 매우 유용 형식은 합니다.  코드 문제는 문서에 대 한 생성기를 가져오는 후 `ChangeToImmutableArrayEmpty` 호출 `MemberAccessExpression`액세스 하려는 멤버를 가진 형식을 전달 하 고 멤버의 이름을 문자열로 전달 합니다.

다음으로 메서드는 문서의 루트를 가져오고 코드가 임의의 작업은 일반적인 경우에 사용 될 수 있습니다, 때문에이 호출이 대기 하 고 취소 토큰을 전달 합니다.  Roslyn 코드 모델은.NET 문자열로; 사용 변경할 수 없습니다. 문자열을 업데이트 하는 경우 새 문자열 개체를 반환 가져옵니다.  호출 하는 경우 `ReplaceNode`를 새 루트 노드 돌아갑니다.  대부분의 구문 트리 (아니므로 변경할 수)는 전체에서 공유 되지만 `objectCreation` 노드 아래 템플릿으로 바뀝니다는 `memberAccess` 으로 노드를 구문 트리 루트까지 모든 부모 노드.

## <a name="trying-your-code-fix"></a>코드 수정을 시도합니다.

이제 누르면 **F5** Visual Studio의 두 번째 인스턴스에서 사용자 분석기를 실행 합니다.  이전에 사용한 콘솔 프로젝트를 엽니다.  이제 새 개체 생성 식에 대 한 위치에 나타날 전구를 표시 해야 `ImmutableArray<int>`합니다.  키를 누르면 **CTRL +.** 다음 코드 수정, 표시 되 고 전구 UI에서에서 자동으로 생성 된 코드 차이 미리 보기를 표시 됩니다 (시간).  Roslyn을이 만들어집니다.

**Pro 팁:** Visual Studio의 두 번째 인스턴스를 시작할 전구 코드 수정 프로그램을 표시 되지 않는 경우 Visual Studio 구성 요소 캐시의 선택을 취소 해야 할 수 있습니다.  캐시를 지우면 Visual Studio Visual Studio 최신 구성 요소를 선택 해야 하므로 구성 요소 다시 검사를 강제로 수행 합니다.  먼저 Visual Studio의 두 번째 인스턴스를 종료 합니다.  다음 Windows 탐색기에서 디렉터리로 이동 하 여 사용자 (c:\users\\< userid\>) AppData\Local\Microsoft\VisualStudio\14.0Roslyn 했는데\\합니다.  이 디렉터리에 ComponentModelCache 하위 디렉터리를 삭제 합니다.  "14" 변경 버전을 버전 Visual Studio와 함께 합니다.

## <a name="talk-video-and-finish-code-project"></a>Talk 비디오 및 코드 프로젝트 완료 날짜

이 예제에서는 개발 하 고 논의 볼 수 있습니다에 더 이상 [이 이야기가](http://channel9.msdn.com/events/Build/2015/3-725)합니다.  작업 분석기를 보여 줍니다.와, 빌드하는 것을 안내 합니다.

완료 된 모든 코드를 볼 수 있습니다 [여기](https://github.com/DustinCampbell/CoreFxAnalyzers/tree/master/Source/CoreFxAnalyzers)합니다.  DoNotUseImmutableArrayCollectionInitializer 및 DoNotUseImmutableArrayCtor 각 하위 폴더는 문제 및 Visual Studio 전구 UI에에서 표시 되는 코드 수정 사항을 구현 하는 C# 파일을 찾기 위한 C# 파일입니다.  참고 완성 된 코드에는 약간의 추상화는 ImmutableArray를 페치 하지 않으려면\<T > 개체를 반복 해 입력 합니다.  중첩 된 등록된 작업을 사용 하 여 사용할 수 있는 컨텍스트에서 형식 개체를 저장 하려면 때마다 하위 작업 (개체 만들기를 분석 하 고 컬렉션 초기화 분석)를 실행 합니다.

## <a name="see-also"></a>참고 항목

* [\\\Build 2015 talk](http://channel9.msdn.com/events/Build/2015/3-725)
* [GitHub에서 완성 된 코드](https://github.com/DustinCampbell/CoreFxAnalyzers/tree/master/Source/CoreFxAnalyzers)
* [세 가지 분석기로 그룹화 된 GitHub의 몇 가지 예제](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)
* [GitHub OSS 사이트에서 다른 docs](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
* [GitHub의 Roslyn 분석기를 사용 하 여 구현 FxCop 규칙](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)
