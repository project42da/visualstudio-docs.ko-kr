---
title: "레거시 언어 서비스 파서 및 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "파서, 언어 서비스 [관리 되는 패키지 프레임 워크]"
  - "파서는 언어 서비스 [관리 되는 패키지 프레임 워크]"
ms.assetid: 1ac3de27-a23b-438d-9593-389e45839cfa
caps.latest.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 20
---
# 레거시 언어 서비스 파서 및 검사
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

파서는 언어 서비스의 핵심입니다. 관리 되는 패키지 프레임 워크 \(MPF\) 언어 클래스에는 표시 되는 코드에 대 한 정보를 선택 하는 언어 파서가 필요 합니다. 파서가 어휘 토큰에 텍스트를 나누고 유형 및 기능으로 이러한 토큰을 식별 합니다.  
  
## 토론  
 다음은 C\# 메서드입니다.  
  
```c#  
namespace MyNamespace { class MyClass { public void MyFunction(int arg1) { int var1 = arg1; } } }  
```  
  
 이 예제에서는 토큰은 단어 및 문장 부호입니다. 토큰의 종류는 다음과 같습니다.  
  
|토큰 이름|토큰 형식|  
|-----------|-----------|  
|네임 스페이스, 클래스, public void int|keyword|  
|\=|연산자|  
|{ } \( \) ;|구분 기호|  
|MyNamespace "," MyClass "," MyFunction "," arg1 "," var1|식별자|  
|MyNamespace|namespace|  
|MyClass|클래스|  
|MyFunction|메서드|  
|arg1|매개 변수|  
|var1|지역 변수|  
  
 파서의 역할에서 토큰을 식별 하는 것입니다. 일부 토큰에는 둘 이상의 형식이 있을 수 있습니다. 파서 토큰에서 확인 하 고, 구문 강조 표시 하는 등의 유용한 기능 중괄호 일치를 제공 하는 정보 및 IntelliSense 작업 언어 서비스 사용할 수 있습니다.  
  
## 파서 유형  
 언어 서비스 파서 컴파일러의 일환으로 사용 하는 파서 같지는 않습니다. 그러나 이러한 종류의 파서 컴파일러 파서와 같은 방식에서 스캐너와는 파서를 사용 해야 합니다.  
  
-   스캐너 토큰 유형을 식별 하는 데 사용 됩니다. 이 정보는 구문 강조 표시 하 고 토큰 형식 예를 들어, 다른 작업을 트리거할 수 있는 중괄호 일치를 신속 하 게 식별 하는 데 사용 됩니다. 이 스캐너 나타내는 <xref:Microsoft.VisualStudio.Package.IScanner> 인터페이스입니다.  
  
-   파서 토큰의 범위와 함수를 설명 하는 데 사용 됩니다. 이 정보는 메서드, 변수, 매개 변수를 선언 등의 언어 요소를 식별 하 고 멤버와 컨텍스트를 기반으로 하는 메서드 시그니처에의 목록을 제공 IntelliSense 작업에 사용 됩니다. 이 파서를 중괄호 및 괄호와 같은 일치 하는 언어 요소 쌍을 찾을 사용 됩니다. 통해이 파서는 액세스는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스입니다.  
  
 언어 서비스에 대 한 스캐너 및 파서 구현 되는 방법을 사용자의 책임입니다. 사용할 수 있는 몇 가지 리소스가 파서 방식으로 사용 하 고 고유한 파서를 작성 하는 방법을 설명 하는 합니다. 또한 몇 가지 무료 및 상용 제품은 파서를 만드는 데 도움이 되는 합니다.  
  
### ParseSource 파서  
 \(여기서는 토큰 형식으로 변환 됩니다 일부의 실행 코드\) 컴파일러의 일부로 사용 되는 파서, 달리 언어 서비스 파서 다양 한 이유로 및 여러 다른 컨텍스트에서 호출할 수 있습니다. 이 접근 방식을 구현 하는 방법을 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스는 사용자의 책임입니다. 유의 해야 하는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 백그라운드 스레드에서 메서드를 호출할 수 있습니다.  
  
> [!CAUTION]
>  <xref:Microsoft.VisualStudio.Package.ParseRequest> 에 대 한 참조를 포함 하는 구조는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 개체입니다. 이 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 백그라운드 스레드에서 개체를 사용할 수 없습니다. 실제로 다양 한 기본 MPF 클래스는 백그라운드 스레드에서 사용할 수 없습니다. 여기에 <xref:Microsoft.VisualStudio.Package.Source>, <xref:Microsoft.VisualStudio.Package.ViewFilter>, <xref:Microsoft.VisualStudio.Package.CodeWindowManager> 클래스 및 직접 또는 간접적으로 보기와 통신 하는 다른 클래스입니다.  
  
 이 파서는 일반적으로 구문 분석 하 여 호출 또는 구문 분석의 값을 설명 하는 경우 전체 소스 파일의 첫 번째 시간 <xref:Microsoft.VisualStudio.Package.ParseReason> 제공 됩니다. 에 대 한 후속 호출에서 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드 구문 분석된 된 코드의 일부만 처리 하 고 이전 전체 구문 분석 작업의 결과 사용 하 여 훨씬 더 빠르게 실행할 수 있습니다.<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드를 통해 구문 분석 작업의 결과 통신 하는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 및 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 개체입니다.<xref:Microsoft.VisualStudio.Package.AuthoringSink> 개체는 다른 이유로 구문 분석, 범위에 대 한 내용은 예를 들어 중괄호 또는 매개 변수 목록을 메서드 시그니처를 일치 하는 정보를 수집 하는 데 사용 됩니다.<xref:Microsoft.VisualStudio.Package.AuthoringScope> 선언 및 메서드 시그니처 및 지원의 컬렉션을 이동 고급 편집 옵션 제공 \(**정의로 이동**, **선언으로 이동**, **참조로 이동**\).  
  
### IScanner 스캐너  
 구현 하는 스캐너도 구현 해야 <xref:Microsoft.VisualStudio.Package.IScanner>합니다. 그러나이 스캐너 통해 줄 단위 별로 작동 하기 때문에 <xref:Microsoft.VisualStudio.Package.Colorizer> 클래스 것은 일반적으로 보다 쉽게 구현할 수 있습니다. MPF 각 줄의 시작 부분에 제공 된 <xref:Microsoft.VisualStudio.Package.Colorizer> 스캐너에 전달 되는 상태 변수로 사용할 값을 클래스입니다. 각 줄의 끝 스캐너의 업데이트 된 상태 변수에 반환합니다. MPF는 스캐너는 소스 파일의 처음부터 시작 하지 않고도 모든 줄에서 구문 분석을 시작할 수 있도록 각 줄에 대 한이 상태 정보를 캐시 합니다. 이 빠른 검색 하는 한 줄 편집기를 사용자에 게 빠른 피드백을 제공할 수 있습니다.  
  
## 중괄호 일치에 대 한 구문 분석  
 이 예제에서는 사용자가 입력 한 닫는 괄호를 일치 하는 제어 흐름을 보여 줍니다. 이 프로세스에 색 지정에 사용 되는 스캐너 유형 토큰 및 토큰 중괄호 일치 작업을 트리거할 수 있는지 여부를 결정 하도 사용 됩니다. 트리거가 없는 경우는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 짝을 찾기 위해 메서드가 호출 됩니다. 마지막으로, 두 개의 중괄호 강조 표시 됩니다.  
  
 중괄호 트리거의 이름에 사용 되는 이유를 구문 분석을 하는 경우에이 프로세스는 실제 중괄호에 제한이 없습니다. 문자를 일치 하는 지정 된 쌍의 쌍으로 된 지원 됩니다. 예를 들면, \< 및 \> 및 \[및\].  
  
 언어 서비스는 중괄호를 지원 한다는 가정 합니다.  
  
1.  사용자는 닫는 중괄호 \(}\)를 입력 합니다.  
  
2.  중괄호를 소스 파일의 커서 위치에 삽입 됩니다 및 커서 씩 고급 기능입니다.  
  
3.  <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 클래스는 형식화 된 닫는 중괄호와 함께 호출 됩니다.  
  
4.  <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> 메서드 호출의 <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 커서의 현재 위치 바로 앞 위치에서 토큰을 가져오는 클래스입니다. 이 토큰에 해당 하는 형식화 된 닫는 중괄호\)입니다.  
  
    1.  <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> 메서드 호출의 <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> 메서드를는 <xref:Microsoft.VisualStudio.Package.Colorizer> 현재 줄에는 모든 토큰을 가져올 개체입니다.  
  
    2.  <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> 메서드 호출의 <xref:Microsoft.VisualStudio.Package.IScanner.SetSource%2A> 메서드를는 <xref:Microsoft.VisualStudio.Package.IScanner> 현재 줄의 텍스트를 가진 개체입니다.  
  
    3.  <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> 메서드 반복적으로 호출 하는 <xref:Microsoft.VisualStudio.Package.IScanner.ScanTokenAndProvideInfoAboutIt%2A> 메서드를는 <xref:Microsoft.VisualStudio.Package.IScanner> 개체를 현재 줄에서 모든 토큰을 수집 합니다.  
  
    4.  <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> 의 개인 메서드를 호출 하는 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 클래스 원하는 위치를 포함 하 여 토큰 및 토큰의 목록에서 단계에서 얻은 <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> 메서드.  
  
5.  <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> 의 토큰 트리거 플래그에 대 한 메서드 조회 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 에서 반환 되는 토큰에는 <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> 메서드, 즉 닫는 중괄호를 나타내는 토큰에\).  
  
6.  트리거 플래그의 경우 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 발견 되는 <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 클래스 라고 합니다.  
  
7.  <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> 메서드 구문 분석 이유 값으로 구문 분석 작업 시작 <xref:Microsoft.VisualStudio.Package.ParseReason>합니다. 이 작업 최종적으로 호출 하는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스입니다. 비동기 구문 분석을 사용 하는 경우이 호출 하는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드는 백그라운드 스레드에서 발생 합니다.  
  
8.  구문 분석 작업이 완료 되 면, 내부 완료 처리기 \(콜백 메서드\) 라는 `HandleMatchBracesResponse` 에서 호출 되는 <xref:Microsoft.VisualStudio.Package.Source> 클래스입니다. 이 호출에서 자동으로 <xref:Microsoft.VisualStudio.Package.LanguageService> 파서가가 아닌 기본 클래스입니다.  
  
9. `HandleMatchBracesResponse` 메서드 범위에서의 목록을 가져옵니다는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 에 저장 된 개체는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체입니다. \(범위는 한 <xref:Microsoft.VisualStudio.TextManager.Interop.TextSpan> 소스 파일의 줄 및 문자 범위를 지정 하는 구조입니다.\) 이 범위 목록에는 일반적으로 열고 닫는 중괄호에 대해 각각 하나씩 두 개의 범위를 포함합니다.  
  
10. `HandleBracesResponse` 메서드 호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A> 메서드를는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 에 저장 된 개체는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체입니다. 지정 된 범위를 강조 표시 합니다.  
  
11. 하는 경우는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 속성 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A> 활성화는 `HandleBracesResponse` 메서드는 일치 하는 범위에 포함 되 고 해당 범위의 처음 80 자로 상태 표시줄에 표시 하는 텍스트를 가져옵니다. 이 작업은 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드는 일치 하는 쌍을 함께 제공 되는 언어 요소를 포함 합니다. 자세한 내용은 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A> 속성을 참조하세요.  
  
12. 이 작업을 수행 합니다.  
  
### 요약  
 일치 하는 중괄호 작업은 언어 요소의 간단한 쌍 일반적으로 제한 됩니다. 삼중 쌍 일치와 같은 좀 더 복잡 한 요소 \("`if(…)`","`{`"및"`}`", 또는 "`else`","`{`"및"`}`"\), 단어 완성 작업의 일부로 강조 표시할 수 있습니다. 예를 들어 "else" 단어 완료 되 면, 일치 하는 "`if`" 문을 강조 표시할 수 있습니다. 일련의 마치 `if`\/`else if` 중괄호 일치로 동일한 메커니즘을 사용 하 여 강조 표시 되어 문을 모두 수 있습니다.<xref:Microsoft.VisualStudio.Package.Source> 기본 클래스는 이미 지원이 다음과 같이: 스캐너 토큰 트리거 값을 반환 해야 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 트리거 값과 함께 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 커서 위치 앞에 있는 토큰에 대 한 합니다.  
  
 자세한 내용은 [중괄호 일치 레거시 언어 서비스](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)을 참조하십시오.  
  
## 색 조정에 대 한 구문 분석  
 소스 코드의 색을 지정 하는 것은 간단 하 고 방금 해당 형식에 대 한 토큰으로, return 정보의 종류를 확인 합니다.<xref:Microsoft.VisualStudio.Package.Colorizer> 클래스의 모든 토큰에 대 한 색 정보를 제공 하는 편집기와 스캐너 간의 중개자 역할입니다.<xref:Microsoft.VisualStudio.Package.Colorizer> 클래스에서 사용 하 여 <xref:Microsoft.VisualStudio.Package.IScanner> 개체 줄의 색을 지정 하는 데 도움이 하 고 소스 파일의 모든 줄에 대 한 상태 정보를 수집할 수 있습니다. MPF 언어 서비스 클래스에는 <xref:Microsoft.VisualStudio.Package.Colorizer> 클래스 스캐너와 통신 하기 때문에 재정의 될 수 없는 통해서만 <xref:Microsoft.VisualStudio.Package.IScanner> 인터페이스입니다. 구현 하는 개체를 제공 하면는 <xref:Microsoft.VisualStudio.Package.IScanner> 인터페이스를 재정의 하 여는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> 메서드는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스.  
  
 <xref:Microsoft.VisualStudio.Package.IScanner> 스캐너를 통해 소스 코드의 줄을 제공 되는 <xref:Microsoft.VisualStudio.Package.IScanner.SetSource%2A> 메서드. 에 대 한 호출이 <xref:Microsoft.VisualStudio.Package.IScanner.ScanTokenAndProvideInfoAboutIt%2A> 메서드는 토큰을 가져올 다음 줄에서 토큰의 줄 가득 찰 때까지 반복 됩니다. 색을 조정할 MPF는 모든 소스 코드 줄의 시퀀스로 처리합니다. 따라서 스캐너 대처 하는 선으로 한번 들어오는 소스 수 있어야 합니다. 또한 언제 든 지 스캐너에 모든 줄이를 전달 될 수 있고 것뿐입니다 스캐너를 검색 하 여 줄 앞에 줄에서 상태 변수를 받습니다.  
  
 <xref:Microsoft.VisualStudio.Package.Colorizer> 클래스는 토큰 트리거를 식별 하는 데도 사용 됩니다. 이 트리거는 특정 토큰이 단어 완성 등의 보다 복잡 한 작업을 시작할 수 있음을 MPF 알려 또는 중괄호 일치 합니다. 이러한 트리거를 식별 빠르게 참조할 수 있어야 하며 모든 위치에서 발생 해야 스캐너 이므로이 작업에 가장 적합 합니다.  
  
 자세한 내용은 [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)을 참조하세요.  
  
## 기능 및 범위에 대 한 구문 분석  
 기능 및 범위에 대 한 구문 분석에서 발생 하는 토큰의 형식을 식별 하는 것 보다 더 많은 노력이 필요 합니다. 파서는 토큰의 형식 뿐만 아니라 토큰을 사용 하는 기능을 식별 해야 합니다. 예를 들어 식별자가 이름에만 있지만 사용자의 언어에서 식별자의 클래스, 네임 스페이스, 메서드 또는 컨텍스트에 따라 변수 이름을 수 있습니다. 토큰의 일반 형식 식별자에 있지만 식별자도 무엇 인지에 따라 및 정의 된 다른 의미가 있습니다. 이 식별 정보가 파서 구문 분석 되는 언어에 대 한 보다 광범위 한 지식이 필요 합니다. 여기서는는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 클래스 제공 합니다.<xref:Microsoft.VisualStudio.Package.AuthoringSink> 식별자, 메서드, 일치 하는 언어 쌍 \(예: 중괄호 및 괄호\) 및 언어 삼중 쌍을 포함 하는 방법에 대 한 정보를 수집 하는 클래스 \(세 부분을 예를 들어 있다는 것을 제외 하 고 언어 쌍 유사한 "`foreach()`" "`{`"및"`}`"\). 재정의할 수는 또한는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 디버거에서 로드 하지 않아도 되도록 중단점의 초기 유효성 검사에 사용 되는 코드 id를 지원 하기 위해 클래스 및 **자동** 프로그램 디버깅 되 고 적절 한 지역 변수 및 디버거를 표시 하는 것 외에도 매개 변수를 식별 하는 파서를 해야 하는 경우 지역 변수 및 매개 변수를 자동으로 보여 주는 디버깅 창입니다.  
  
 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 개체의 일부로 파서에 전달 되는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체 및 새 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 개체는 생성 될 때마다 새 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체가 만들어집니다. 또한는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드를 반환 해야는 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 다양 한 IntelliSense 작업을 처리 하는 데 사용 되는 개체입니다.<xref:Microsoft.VisualStudio.Package.AuthoringScope> 개체는 유지 선언에 대 한 목록 및 메서드에 대 한 목록을 중 하나는 채워집니다, 구문 분석에 대 한 설명에 따라 합니다.<xref:Microsoft.VisualStudio.Package.AuthoringScope> 클래스를 구현 해야 합니다.  
  
## 참고 항목  
 [레거시 언어 서비스 구현](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [레거시 언어 서비스 개요](../../extensibility/internals/legacy-language-service-overview.md)   
 [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)   
 [중괄호 일치 레거시 언어 서비스](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)