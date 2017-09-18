---
title: "Roslyn 분석기 및 코드 인식 ImmutableArrays 라이브러리 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0b0afa22-3fca-4d59-908e-352464c1d903
caps.latest.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 5
---
# Roslyn 분석기 및 코드 인식 ImmutableArrays 라이브러리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[.NET 컴파일러 플랫폼](https://github.com/dotnet/roslyn) \("Roslyn"\)를 사용 하면 코드 인식 라이브러리를 만들 수 있습니다.  코드 인식 라이브러리는 가장 좋은 방법은 또는 오류를 방지 하려면 기능을 사용할 수 및 라이브러리를 사용할 수 있도록 \(Roslyn 분석기\) 도구를 제공 합니다.  이 항목에서는 사용 하는 경우 일반적인 오류를 catch 하는 실제 Roslyn 분석기를 구축 하는 방법을 보여 줍니다는 [변경할 수 없는 컬렉션](../Topic/NIB:%20Immutable%20Collections.md) NuGet 패키지입니다.  이 예제에는 또한 분석기에 의해 발견 된 코드 문제에 대 한 코드 수정을 제공 하는 방법을 보여 줍니다.  사용자가 Visual Studio 전구 UI의에서 코드 수정 보고 코드에 대 한 수정을 자동으로 적용할 수 있습니다.  
  
## 항목 내용  
 이 항목에는 다음 섹션이 있습니다.  
  
-   시작  
  
-   이 문제는 무엇입니까?  
  
-   관련 코드 모델 형식에 분석기를 트리거할 수 찾기  
  
-   분석기 프로젝트 만들기  
  
-   분석기를 초기화합니다.  
  
-   프로그램 분석기의 사용자에 대 한 속성을 설정합니다.  
  
-   개체 생성 식을 분석  
  
-   처음으로 여 Analyzer와 함께 Visual Studio 시작  
  
-   편집 하며 계속 하기는 분석기를 사용 하 여 완료 합니다.  
  
-   코드 문제에 대 한 "코드 수정"을 추가합니다.  
  
-   코드 수정을 시도합니다.  
  
-   비디오 및 완성 된 코드 프로젝트를 설명 합니다.  
  
## 시작  
 이 예제를 빌드하려면 다음이 필요 합니다.  
  
-   Visual Studio 2015 \(하지는 Express Edition\) 또는 이후 버전입니다.  무료 를 사용할 수 있습니다 [Visual Studio Community Edition](https://www.visualstudio.com/products/visual-studio-community-vs)  
  
-   [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  확인할 수도 있습니다, Visual Studio를 설치 하는 경우 동시에 SDK를 설치 하는 일반적인 도구에서 Visual Studio 확장성 도구입니다.  Visual Studio를 이미 설치한 경우 설치할 수도 있습니다이 SDK 주 메뉴로 이동 하 여 **파일 &#124; 새로 만들기 &#124; 프로젝트...**, C\# 왼쪽된 탐색 창에서 선택 하 고 다음 확장을 선택 합니다.  선택 하는 경우는 "**Visual Studio 확장성 도구 설치**" 이동 경로 탐색 프로젝트 템플릿을 하 라는 메시지가 다운로드 하 여 SDK를 설치 합니다.  
  
-   [.NET 컴파일러 플랫폼 \("Roslyn"\) SDK](http://aka.ms/roslynsdktemplates)합니다.  주 메뉴로 이동 하 여이 SDK를 설치할 수도 있습니다 **파일 &#124; 새로 만들기 &#124; 프로젝트...**, 선택, **C\#** 의 왼쪽된 탐색 창에서 선택 하 고에 **확장성**합니다.  선택 하는 경우 "**.NET 컴파일러 플랫폼 SDK 다운로드**" 이동 경로 탐색 프로젝트 템플릿을 하 라는 메시지가 다운로드 하 여 SDK를 설치 합니다.  이 SDK에 포함 된 [Roslyn 구문 시각화 도우미](https://github.com/dotnet/roslyn/wiki/Syntax%20Visualizer)합니다.  코드 모델 유형을 파악이 매우 유용한 도구를 사용 하면 확인 해야 할 사용자 분석기.  코드에서만 필요한 경우에 실행 하 고 관련 코드 분석에 집중할 수 있도록 특정 코드 모델 유형에 대 한 코드에 분석기 인프라가 호출 합니다.  
  
## 이 문제는 무엇입니까?  
 Imagine ImmutableArray와 라이브러리를 제공 \(예를 들어 <xref:System.Collections.Immutable.ImmutableArray%601?displayProperty=fullName>\)를 지원 합니다.  C\# 개발자는.NET 배열과 경험이 있습니다.  그러나 구현에 사용 되는 ImmutableArrays 및 최적화 기술 특성상 C\# 개발자 intuitions 인해 손상 된 코드를 작성 하 여 라이브러리의 사용자가 아래에서 설명한 대로.  또한 사용자 런타임까지.NET과 함께 Visual Studio에서 데 품질 경험에 관계 없는 해당 오류가 표시 되지 않습니다.  
  
 사용자를 잘 알고 다음과 같은 코드를 작성 합니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 만드는 코드의 다음 줄을 사용 하 여 채울에 빈 배열 및 컬렉션 이니셜라이저 구문을 사용 하 여 C\# 개발자에 게 친숙 하 게 됩니다.  그러나 코드는 ImmutableArray에 대 한 런타임 시 크래시 동일한 작성:  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 첫 번째 오류 ImmutableArray 구현 구조체를 사용 하 여 내부 데이터 저장소를 래핑할 때문입니다.  구조체는 매개 변수가 없는 생성자가 있어야 있도록 `default(T)` 식은 모든 구조체를 반환할 수 있습니다 0 또는 null 멤버입니다.  코드에 액세스할 때 `b1.Length`, 는 런타임에 null ImmutableArray 구조체에 기본 저장소 배열 없음 있기 때문에 오류를 역참조 합니다.  빈 ImmutableArray 만들려고 하는 올바른 방법은 `ImmutableArray<int>.Empty`합니다.  
  
 컬렉션 이니셜라이저 오류로 ImmutableArray.Add 메서드가 호출 될 때마다 새 인스턴스를 반환 하기 때문에 발생 합니다.  ImmutableArrays 변경 되지 않으면 새 요소를 추가 하면, 때문에 다시 얻습니다는 새 ImmutableArray 개체를 \(이전에 기존 ImmutableArray와 성능상의 이유로 저장소를 공유할 수 있습니다\).  때문에 `b2` 호출 하기 전에 첫 번째 ImmutableArray 가리키는 `Add()` 다섯 번 `b2` ImmutableArray 기본입니다.  오류를 역참조 호출 길이에 null이 충돌 합니다.  사용 하는 수동으로 추가 호출 하지 않고는 ImmutableArray를 초기화 하는 올바른 방법은 `ImmutableArray.CreateRange(new int[] {1, 2, 3, 4, 5})`합니다.  
  
## 관련 구문 노드 형식에 분석기를 트리거할 수 찾기  
 분석기 빌드를 시작 하려면 먼저 파악에 대 한 확인 해야 하는 어떤 유형의 SyntaxNode 합니다.    구문 시각화 메뉴에서 시작 **보기 &#124; 다른 창 &#124; Roslyn 구문 시각화 도우미**합니다.  
  
 선언 하는 줄에 편집기의 캐럿 배치 `b1`합니다.  구문 시각화 도우미에서 표시 하 고 있는 표시는 `LocalDeclarationStatement` 구문 트리 노드에 있습니다.  이 노드에 `VariableDeclaration`, 다시는 `VariableDeclarator`, 다시는 `EqualsValueClause`, 마지막는 `ObjectCreationExpression`합니다.  구문 시각화 도우미 트리 노드를 클릭 한 해당 노드에 표시 되는 코드를 표시 하려면 편집기 창에서 구문 강조 표시 됩니다.  SyntaxNode 하위 형식의 이름을 C\# 문법에서 사용 되는 이름과 일치 합니다.  
  
## 분석기 프로젝트 만들기  
 주 메뉴에서 선택 **파일 &#124; 새로 만들기 &#124; 프로젝트...**합니다.  에 **새 프로젝트** 대화 상자 아래에서 **C\#** 프로젝트의 왼쪽된 탐색 모음에서 확장성, 선택한 오른쪽 창에서 선택는 **분석기와 코드를 수정** 프로젝트 템플릿.  이름을 입력 하 고 대화 상자를 확인 합니다.  
  
 서식 파일 DiagnosticAnalyzer.cs 파일을 엽니다.  해당 편집기 버퍼 탭을 선택 합니다.  이 파일에 분석기 클래스 \(형성 된 프로젝트 이름에서 지정한\)에서 파생 되는 `DiagnosticAnalyzer` \(Roslyn API 유형\).  새 클래스에는 `DiagnosticAnalyzerAttribute` 선언 하 여 분석기는 컴파일러를 검색 하 여 분석기를 로드 하는 C\# 언어와 관련이 있습니다.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 C\# 코드를 대상으로 하는 Visual Basic을 사용 하는 분석기를 구현할 수 또는 그 반대로 합니다.  것이 더 중요 한 언어 중 하나 또는 둘 다 사용자 분석기를 대상으로 하는지 여부를 선택할 수 DiagnosticAnalyzerAttribute에 있습니다.  언어의 자세한 모델링을 필요로 하는 보다 정교한 분석기는 단일 언어를 대상만 수 있습니다.  프로그램 분석기 예를 들어만 확인 된 형식 이름 또는 공용 멤버 이름을, Roslyn는 Visual Basic 및 C\#에서 제공 하는 공용 언어 모델을 사용 하 여 수도 있습니다.  클래스에서 구현 하는 FxCop을 경고 하는 예를 들어 <xref:System.Runtime.Serialization.ISerializable>, 하지만 클래스가 없는 <xref:System.SerializableAttribute> 특성 언어 독립적 및 Visual Basic 및 C\# 코드에 대해 작동 합니다.  
  
## 초기화는 분석기  
 약간 아래로 스크롤하여는 `DiagnosticAnalyzer` 참조 하는 클래스는 `Initialize` 메서드.  컴파일러는 분석기를 활성화 하는 경우이 메서드를 호출 합니다.  메서드를 사용 하며는 `AnalysisContext` 컨텍스트 정보를 분석 하려면 코드의 종류에 대 한 이벤트에 대 한 콜백을 등록 하 여 분석기를 사용할 수 있는 개체입니다.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 이 컨텍스트에서 메서드 및 형식을"." 새 줄을 엽니다 Intellisense 완성 목록이 확인 합니다.  다 완성 목록에서 볼 수 `Register…` 다양 한 종류의 이벤트를 처리 하기 위한 메서드.  예를 들어, 첫 번째 `RegisterCodeBlockAction`, 중괄호 사이 코드는 일반적으로 블록에 대 한 코드를 다시 호출 합니다.  블록에 대 한 등록도 다시 호출 코드에는 필드에서 특성에 지정 된 값 또는 선택적 매개 변수 값의 이니셜라이저에 대 한 합니다.  
  
 또 다른 예로, `RegisterCompilationStartAction`, 컴파일, 여러 위치를 통해 상태를 수집 해야 할 때 유용의 시작 부분에 코드를 다시 호출 합니다.  데이터 구조를 예를 들어, 수집, 사용 되는 모든 기호를 만들고 일부 구문 또는 기호에 대 한 사용자 분석기를 다시 호출 될 때마다 데이터 구조에서 각 위치에 대 한 정보를 저장할 수 있습니다.  컴파일 종료로 인해 다시 호출 하는 경우 저장, 예를 들어 코드 각각에서 사용 하 여 기호를 보고 하는 모든 위치를 분석할 수 있습니다 `using` 문입니다.  
  
 사용 하 여 **구문 시각화 도우미**, 컴파일러는 ObjectCreationExpression를 처리할 때 호출 될 것인지에 대해 알아보았습니다.  이 코드를 사용 하 여 콜백을 설정 합니다.  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
 구문 노드 및 개체 생성 구문 노드만 대 한 필터에 대 한 등록 합니다.  규칙에 따라 상태 비저장 분석기를 유지 하는 데 도움이 되는 작업을 등록 하는 경우 분석기 작성자는 람다를 사용 합니다.  Visual Studio 기능을 사용할 수 **관례에서 생성** 만들려는 `AnalyzeObjectCreation` 메서드.  이 올바른 유형의 컨텍스트 매개 변수를 생성 하면 너무 합니다.  
  
## 프로그램 분석기의 사용자에 대 한 속성을 설정합니다.  
 분석기에 표시 되도록 Visual Studio UI에서 적절 하 게, 찾아서 프로그램 분석기를 식별 하는 코드의 다음 줄을 수정 합니다.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
 변경 `"Naming"` 를 `"API Guidance"`합니다.  
  
 다음 찾기 및 사용 하 여 프로젝트에서 Resources.resx 파일을 열고는 **솔루션 탐색기**합니다.  분석기, 제목, 등에 대 한 설명에 넣을 수 있습니다.  이러한 모든 값을 변경할 수 `“Don’t use ImmutableArray<T> constructor”` 지금은 합니다.  인수 문자열에서 서식 지정 문자열을 저장할 수 있습니다 \({0}, \\{1\\} 등\), 호출할 때 이상 `Diagnostic.Create()`, 매개 변수 배열을 전달 될 인수를 제공할 수 있습니다.  
  
## 개체 생성 식을 분석  
 `AnalyzeObjectCreation` 메서드는 다른 종류의 코드 분석기 프레임 워크에서 제공 하는 컨텍스트를 사용 합니다.  Initialize 메서드 `AnalysisContext` 프로그램 분석기를 설정 하려면 작업 콜백을 등록할 수 있습니다.`SyntaxNodeAnalysisContext`, 예를 들어, 한 `CancellationToken` 주위 전달할 수 있는 합니다.  사용자가 편집기에 입력을 시작 하는 경우 Roslyn 작업을 저장 하 고 성능을 향상 하는 실행 중인 분석기를 취소 합니다.  이 컨텍스트는 또 다른 예로, 개체 생성 구문 노드를 반환 하는 노드 속성을 있습니다.  
  
 구문 노드 작업을 필터링 하는 형식입니다. 가정할 수 있는 노드를 가져옵니다.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
### 처음으로 여 Analyzer와 함께 Visual Studio 시작  
 작성 하 여 분석기를 실행 하 여 Visual Studio를 시작 \(키를 눌러 **F5**\).  프로젝트를 시작 하기 때문에 **솔루션 탐색기** 는 VSIX 프로젝트 코드 및 VSIX를 코드 빌드를 실행 하 고 설치 하는 VSIX 사용 하는 Visual Studio를 시작 합니다.  이러한 방식으로 Visual Studio를 시작 하 여 Visual Studio의 주 사용은 영향을 받지 테스트 인스턴스 분석기를 작성 하는 동안 고유한 레지스트리 하이브를 시작 합니다.  처음에 이러한 방식으로 실행할 때 Visual Studio를 처음 시작할 때 Visual Studio 설치 후 비슷합니다 몇 가지 초기화가 수행 하지 않습니다.  
  
 콘솔 프로젝트를 만들고 콘솔 응용 프로그램 Main 메서드로 배열 코드를 입력 합니다.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
 사용 하 여 코드의 줄 `ImmutableArray` 물결 기호를 변경할 수 없는 NuGet 패키지를 다운로드 하 고 추가 해야 하기 때문에는 `using` 문을 코드에 있습니다.  프로젝트 노드를 오른쪽 포인터 단추를 눌러는 **솔루션 탐색기** 선택한 **NuGet 패키지 관리...**합니다.  NuGet 관리자에서 검색 상자에 "변경할 수 없는"를 입력 하 고 "System.Collections.Immutable" 항목 선택 \("Microsoft.Bcl.Immutable"을 선택 하지 않으면\)의 왼쪽된 창에서 오른쪽 창에서 설치 단추를 누릅니다.  프로젝트 참조에 대 한 참조를 추가 패키지를 설치 합니다.  
  
 아래의 빨간색 물결선을 계속 나타나면 `ImmutableArray`, 식별자 및 키를 눌러 해당 캐럿 배치 **CTRL \+.** \(마침표\)에 제안 된 해결 방법 메뉴를 표시 하 고 적절 한 추가 하도록 선택 `using` 문입니다.  
  
 **모두 저장 하 고 닫습니다** 을 계속 하려면 깨끗 한 상태로 지금은 Visual Studio의 두 번째 인스턴스.  
  
## 편집 하며 계속 하기는 분석기를 사용 하 여 완료 합니다.  
 Visual Studio의 첫 번째 인스턴스를 시작 부분에 중단점을 설정 하면 `AnalyzeObjectCreation` 키를 눌러 메서드 **F9** 첫 번째 줄에서 캐럿 합니다.  
  
 프로그램 분석기를 사용 하 여 다시 시작 **F5**, Visual Studio의 두 번째 인스턴스에서 마지막으로 만든 콘솔 응용 프로그램 다시 엽니다.  
  
 Roslyn 컴파일러 개체 생성 식을 확인 하 고 프로그램 분석기에 호출 하기 때문에 중단점에서 Visual Studio의 첫 번째 인스턴스를 반환 합니다.  
  
 **개체 만들기 노드를 가져옵니다.** 설정 하는 줄 건너뛰기는 `objectCreation` 키를 눌러 변수 **F10**, 및는 **직접 실행 창** 식을 계산할 `“objectCreation.ToString()”`합니다.  변수를 가리키는 구문 노드는 코드를 참조 하십시오 `"new ImmutableArray<int>()"`, 방금 원하는 내용을 대 한 합니다.  
  
 **\< T \> ImmutableArray 형식 개체를 가져옵니다.** 만들 유형을 ImmutableArray 인지 확인 해야 합니다.  먼저,이 형식을 나타내는 개체를 가져올 있습니다.  의미 체계 모델을 사용 하 여 올바른 형식이 정확 하 고 tostring \(\)에서 문자열을 비교 하지 않습니다 위해 형식을 검사 하는 경우.  함수의 끝에 코드의 다음 줄을 입력 합니다.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
 제네릭 매개 변수의 수와 backquotes \('\)와 함께 메타 데이터의 제네릭 형식을 지정합니다.  따라서 표시 되지 않으면 "... \< T \> ImmutableArray "메타 데이터 이름에서입니다.  
  
 의미 체계 모델에 유용한 여러 가지 기호, 데이터 흐름, 변수 수명에 대 한 질문 수 있도록 합니다.  Roslyn 다양 한 이유로 엔지니어링 \(성능, 잘못 된 코드 등을 모델링 합니다.\)는 의미 체계 모델에서 구문 노드를 구분 합니다.  컴파일 모델을 정확 하 게 비교에 대 한 참조에 포함 된 정보를 조회 하는 것이 좋습니다.  
  
 편집기 창의 왼쪽에 노란색 실행 파일에 대 한 포인터를 끌 수 있습니다.  설정 하는 줄까지 끌는 `objectCreation` 변수 및 코드를 사용 하 여 새 줄 건너뛰기 **F10**합니다.  변수 위로 마우스 포인터를 가져가면 경우 `immutableArrayOfType`, 의미 체계 모델의 정확한 형식의 있음을 표시 합니다.  
  
 **개체 생성 식의 형식을 가져옵니다.** "Type"이이 문서에는 몇 가지 방법이 사용 되지만 즉, "새 Foo" 있으면 Foo의 모델을 사용 하려면 필요한 식입니다.  \< T \> ImmutableArray 형식 있는지 개체 생성 식의 형식을 가져올 해야 합니다.  개체 생성 식에 형식 기호 \(ImmutableArray\)에 대 한 기호 정보를 얻으려면 의미 체계 모델을 다시 사용 합니다.  함수의 끝에 코드의 다음 줄을 입력 합니다.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
 편집기 버퍼에 불완전 하거나 잘못 된 코드를 처리 하 여 분석기 필요 하기 때문에 \(예를 들어, 누락 된 `using` 문\)를 확인 해야 `symbolInfo` 되 고 `null`합니다.  분석을 마치는 기호 정보 개체에서 명명 된 형식 \(INamedTypeSymbol\)를 가져오려는 필요 합니다.  
  
 **형식을 비교 합니다.** 쿼리 형식에 관계 \(개방형 제네릭 형식\)에서 생성 되는 것에 대 한 기호 정보를 조사 하 고, T의 개방형 제네릭 형식 코드의 형식을 제네릭 형식인 구체적인 없어 및 해당 결과와 비교 `immutableArrayOfTType`합니다.  메서드의 끝에 다음을 입력 합니다.  
  
<CodeContentPlaceHolder>10</CodeContentPlaceHolder>  
 **진단을 보고 합니다.** 진단 보고 매우 쉽습니다.  Initialize 메서드 앞에 정의 프로젝트 템플릿에서 생성 하는 규칙을 사용 하는 경우.  이 경우 코드에서 오류 이기 때문에 대체 하는 규칙을 초기화 하는 줄을 변경할 수 있습니다 `DiagnosticSeverity.Warning` \(녹색 오류 표시선\)와 `DiagnosticSeverity.Error` \(빨간색 물결 무늬가\).  규칙의 나머지 부분에서 자습서의 시작 부분 편집 하는 리소스를 초기화 합니다.  오류 표시선 개체 만들기 expresssion 유형 지정의 위치에 대 한 위치를 보고 해야 합니다.  이 코드를 입력는 `if` 블록:  
  
<CodeContentPlaceHolder>11</CodeContentPlaceHolder>  
 함수는 \(아마도 서식이 다르게 지정\)이 같습니다.  
  
<CodeContentPlaceHolder>12</CodeContentPlaceHolder>  
 중단점을 제거 하 고 수 있도록 분석기 작업 참조 \(Visual Studio의 첫 번째 인스턴스를 반환 하지\).  메서드 및 키를 눌러 시작 부분에 실행 파일에 대 한 포인터를 끌어 **F5** 실행을 계속 합니다.  Visual Studio의 두 번째 인스턴스를 다시 전환 하면 컴파일러 코드를 검사를 다시 시작 하 고 프로그램 분석기에 호출 됩니다.  아래에서 물결 무늬를 볼 수 `ImmutableType<int>`합니다.  
  
## 코드 문제에 대 한 "코드 수정"을 추가합니다.  
 시작 하기 전에 Visual Studio의 두 번째 인스턴스를 닫고 Visual Studio \(여기서 개발 하는 분석기\)의 첫 번째 인스턴스에서 디버깅을 중지 합니다.  
  
 **새 클래스를 추가 합니다.** 솔루션 탐색기에서 프로젝트 노드 바로 가기 메뉴 \(오른쪽 포인터 단추\)를 사용할 하 있으며 새 항목을 추가 하려면 선택할 키를 누릅니다.  라는 클래스를 추가 `BuildCodeFixProvider`합니다.  이 클래스에서 파생 해야 `CodeFixProvider`, 를 사용 해야 하 고 **CTRL \+.** \(마침표\)를 추가 하는 올바른 코드 수정을 호출 `using` 문입니다.  이 클래스는도로 주석을 추가 해야 `ExportCodeFixProvider` 특성 및 사용자를 추가 해야 합니다는 `using` 문을 확인 하는 `LanguageNames` 열거형입니다.  클래스 파일에 다음 코드와 함께 있어야 합니다.  
  
<CodeContentPlaceHolder>13</CodeContentPlaceHolder>  
 **파생 된 구성원을 스텁 합니다.** 이제는 식별자에 편집기의 캐럿을 배치 `CodeFixProvider` 누릅니다 **CTRL \+.** \(마침표\)이 추상 기본 클래스에 대 한 구현으로 합니다.  사용자에 대 한 속성과 메서드를 생성합니다.  
  
 **속성을 구현 합니다.** 입력은 `FixableDiagnosticIds` 속성의 `get` 를 다음 코드로 본문:  
  
<CodeContentPlaceHolder>14</CodeContentPlaceHolder>  
 Roslyn 함께 진단을 시작 하 고 단순한 문자열을 이러한 식별자를 비교 하 여 해결 합니다.  프로젝트 템플릿에 진단 ID를 고객을 위해 생성 하 고 변경할 수 있습니다.  속성의 코드는 방금 분석기 클래스에서 ID를 반환합니다.  
  
 **RegisterCodeFixAsync 메서드는 컨텍스트를 사용합니다.** 컨텍스트는 코드를 수정 여러 진단에 적용 하거나 코드 줄에 둘 이상의 문제 수 중요 합니다.  "컨텍스트."를 입력 하는 경우 메서드 본문에서 Intellisense 완성 목록이 표시 됩니다 몇 가지 유용한 멤버.  수정 프로그램을 취소 하려는 항목 참조를 확인할 수 있는 CancellationToken 멤버 임  많은 유용한 멤버 및 프로젝트 및 솔루션 모델 개체를 사용 하면는 문서 멤버 임  시작 되는 범위 멤버 이며 코드 위치 끝날 진단을 보고 하는 경우를 지정 합니다.  
  
 **비동기 될 메서드를 만듭니다.** 가장 먼저 해야 할는 생성 된 메서드 선언을 다음으로 수정 되는 `async` 메서드.  추상 클래스의 구현에서는 스텁에 대 한 코드 수정을 포함 되어 있지는 `async` 메서드가 반환 하는 경우에 키워드는 `Task`.  
  
 **구문 트리 루트를 가져옵니다.** 변경 내용으로 새 구문 트리를 생성 하는 데 필요한 코드를 수정 하려면 코드 수정 사항을 만듭니다.  필요한는 `Document` 호출 컨텍스트에서 `GetSyntaxRootAsync`합니다.  비동기 메서드는 디스크에서 파일 가져오기, 구문 분석 하 고 Roslyn 코드 모델에 대 한 빌드를 포함 하 여, 구문 트리를 가져오기 위해 알 수 없는 작업 때문입니다.  Visual Studio UI를 사용 하 여이 시간 동안 응답 해야 `async` 수 있습니다.  메서드에서 코드 줄을을 다음으로 바꿉니다.  
  
<CodeContentPlaceHolder>15</CodeContentPlaceHolder>  
 **문제가 있는 노드를 찾습니다.** 컨텍스트 범위를 변경 해야 하는 코드 아닐를 찾았으면 노드에 전달 합니다.  보고 된 진단 \(여기서 오류 표시선 속했던\) 하는 형식 식별자에 대 한 범위에만 제공 하지만 전체 개체 생성 식 교체 해야 포함 하는 `new` keywoard 시작과 끝에 괄호입니다.  메서드에 다음 코드를 추가 \(사용 하 여 **CTRL \+.** 추가 하는 `using` 문을 `ObjectCreationExpressionSyntax`\):  
  
<CodeContentPlaceHolder>16</CodeContentPlaceHolder>  
 **전구 UI에 대 한 수정 하 여 코드를 등록 합니다.** 코드 수정 프로그램을 등록 하면 Visual Studio 전구 UI에 Roslyn 자동으로 연결 됩니다.  사용 하 여 최종 사용자에 게 표시 됩니다 **CTRL \+.** 프로그램 분석기 물결선는 잘못 된 경우 \(마침표\) `ImmutableArray<T>` 생성자를 사용 합니다.  코드 수정 프로그램 공급자에만 실행 되므로 문제가 발생 하는 경우, 개체 생성 식이 찾고 있던 가정할 수 있습니다.  컨텍스트 매개 변수에서 새 코드 수정을의 끝에 다음 코드를 추가 하 여 등록할 수 있습니다 `RegisterCodeFixAsync` 메서드:  
  
<CodeContentPlaceHolder>17</CodeContentPlaceHolder>  
 편집기의 캐럿의 식별자에 배치 해야 `CodeAction`, 를 사용 하 여 **CTRL \+.** \(마침표\)를 적절 한 추가 하려면 `using` 이 유형에 대 한 문입니다.  
  
 그런 다음에 편집기의 캐럿을 배치는 `ChangeToImmutableArrayEmpty` 식별자 및 사용 하 여 **CTRL \+.** 을 자동으로이 메서드 스텁 생성을 다시 합니다.  
  
 이 마지막 코드 조각을 추가한 코드 수정을 전달 하 여 등록 한 `CodeAction` 문제 발견의 종류에 대 한 진단 id입니다.  이 예제에서는 하나 뿐입니다에 대 한 수정이 코드를 제공 하는 진단 ID만 진단 Id 배열의 첫 번째 요소를 전달할 수 있습니다.  만들 때의 `CodeAction`, 전구 UI 코드 수정 사항에 대 한 설명을으로 사용 해야 하는 텍스트에 전달 합니다.  CancellationToken을 사용 하 고 새 문서를 반환 하는 함수에 전달할 수도 있습니다.  새 문서에는 호출 하는 패치가 적용 된 코드를 포함 하는 새로운 구문 트리 `ImmutableArray.Empty`합니다.  이 코드 조각은 objectCreation 노드와 컨텍스트의 문서를 통해 닫을 수 있도록 하는 람다를 사용 합니다.  
  
 **새 구문 트리를 생성 합니다.** 에 `ChangeToImmutableArrayEmpty` 앞에서 생성 된 스텁 코드 줄을 입력 하는 메서드: `ImmutableArray<int>.Empty;`합니다.  다시 구문 시각화 도우미 도구 창에 보면이 구문은 SimpleMemberAccessExpression 노드를 볼 수 있습니다.  이 이렇게 하는 사항 구성 하 고 새 문서에 반환 하는 것이입니다.  
  
 첫 번째 변경 `ChangeToImmutableArrayEmpty` 추가 하는 것 `async` 전에 `Task<Document>` 되므로 코드 생성기는 메서드를 비동기 수 가정할 수 없습니다.  
  
 메서드는 다음과 유사 하 여 본문에 다음 코드를 입력 합니다.  
  
<CodeContentPlaceHolder>18</CodeContentPlaceHolder>  
 에 편집기의 캐럿을 배치 해야는 `SyntaxGenerator` 식별자 및 사용 하 여 **CTRL \+.** \(마침표\)를 적절 한 추가 하려면 `using` 이 유형에 대 한 문입니다.  
  
 이 코드를 사용 하 여 `SyntaxGenerator`, 형식인는 매우 유용한 새 코드를 생성 합니다.  뒤에 코드 문제를 포함 하는 문서에 대 한 생성기를 가져오는 `ChangeToImmutableArrayEmpty` 호출 `MemberAccessExpression`, 에 액세스 하려고 하는 멤버가 형식을 전달 하 고 멤버의 이름을 문자열로 전달 합니다.  
  
 다음으로 메서드는 문서의 루트를 인출 고 때문에 일반적인 경우 임의의 작업을 포함할 수이 코드는이 호출을 기다립니다 취소 토큰을 전달.  Roslyn 코드 모델은.NET 문자열로; 작업 처럼 변경할 수 없습니다. 문자열을 업데이트 하는 경우 새 문자열 개체를 반환에서 가져옵니다.  호출 하는 경우 `ReplaceNode`, 새 루트 노드를 다시 얻습니다.  대부분의 구문 트리 \(아니므로 변경할 수\)는 전체에서 공유 하지만 `objectCreation` 노드도 대체 되는 `memberAccess` 구문 트리 루트까지 모든 부모 노드 뿐만 아니라 노드를 합니다.  
  
## 코드 수정을 시도합니다.  
 이제 누르면 **F5** Visual Studio의 두 번째 인스턴스에서 사용자 분석기를 실행 합니다.  이전에 사용한 콘솔 프로젝트를 엽니다.  이제 새 개체 생성 식에 대 한 위치에 나타날 전구가 표시 됩니다 `ImmutableArray<int>`합니다.  키를 누르면 **CTRL \+.** \(시간\)를 수정 하 여 코드 표시 됩니다 및 전구 UI에서에서 미리 보기를 자동으로 생성 된 코드 차이점 표시 됩니다.  Roslyn을이 만들어집니다.  
  
 Pro 팁: Visual Studio의 두 번째 인스턴스를 시작 하는 경우 코드 수정으로 전구에 표시 되지 않으면 다음 해야 Visual Studio 구성 요소 캐시의 선택을 취소 합니다.  캐시를 삭제 하면 Visual Studio의 Visual Studio 다음 최신 구성 요소를 선택 해야 하므로 구성 요소를 다시 검토 하면 됩니다.  첫째, Visual Studio의 두 번째 인스턴스를 종료 합니다.  그런 다음 Windows 탐색기에서의 사용자 디렉터리 \(예: c:\\users\\ \< userid \>\)로 이동 하 고 AppData\\Local\\Microsoft\\VisualStudio\\14.0Roslyn\\ 찾기.  이 디렉터리에서 ComponentModelCache 하위 디렉터리를 삭제 합니다.  "14" 변경 내용을 Visual studio 버전입니다.  
  
## 강연 비디오 및 코드 프로젝트 완료  
 개발 하 고 설명 된이 예제를 볼 수에 대 한 자세한 [이 강연](http://channel9.msdn.com/events/Build/2015/3-725)합니다.  논의 작업 분석기를 보여 줍니다. 및 빌드하는 것을 안내 합니다.  
  
 완성 된 모든 코드를 볼 수 [여기](https://github.com/DustinCampbell/CoreFxAnalyzers/tree/master/Source/CoreFxAnalyzers)합니다.  문제 및 Visual Studio 전구 UI에에서 표시 되는 코드 수정을 구현 하는 C\# 파일을 찾기 위한 C\# 파일을 포함 하는 DoNotUseImmutableArrayCollectionInitializer 및 DoNotUseImmutableArrayCtor 각 하위 폴더.  Note 완성 된 코드에 ImmutableArray \< T \> 형식 개체를 반복 해 인출 되지 않도록 하기 위해 약간 더 많은 추상화 합니다.  중첩 된 등록된 작업을 사용 하 여 개체를 저장할 형식을 사용할 수 있는 컨텍스트에서 때마다 하위 작업 \(개체 만들기를 분석 하 고 컬렉션 초기화 분석\)를 실행 합니다.  
  
## 참고 항목  
 [\\\\Build 2015 토크](http://channel9.msdn.com/events/Build/2015/3-725)   
 [Github에서 완성 된 코드](https://github.com/DustinCampbell/CoreFxAnalyzers/tree/master/Source/CoreFxAnalyzers)   
 [그룹화 된 세 가지 유형의 분석기 github에서 몇 가지 예제](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)   
 [OSS github 사이트의 다른 문서](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)   
 [Github에서 Roslyn 분석기를 사용 하 여 구현 하는 FxCop 규칙](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)