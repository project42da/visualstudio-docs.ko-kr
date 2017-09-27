---
title: "레거시 언어 서비스 파서 및 스캐너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsers, language services [managed package framework]
- language services [managed package framework], Parsers
ms.assetid: 1ac3de27-a23b-438d-9593-389e45839cfa
caps.latest.revision: 20
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: c95dbbeaf9dcd6e1014ce3d2af8a0398c6627fe3
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="legacy-language-service-parser-and-scanner"></a>레거시 언어 서비스 파서 및 스캐너
파서가 언어 서비스의 핵심입니다. 관리 되는 패키지 프레임 워크 (MPF) 언어 클래스에는 표시 되 고 코드에 대 한 정보를 선택할 언어 파서를 필요 합니다. 파서는 텍스트 어휘 토큰으로 분리 하 고 유형과 기능으로 이러한 토큰을 식별 합니다.  
  
## <a name="discussion"></a>토론  
 다음은 C# 메서드입니다.  
  
```csharp  
namespace MyNamespace  
{  
    class MyClass  
    {  
        public void MyFunction(int arg1)  
        {  
            int var1 = arg1;  
        }  
    }  
}  
```  
  
 이 예제에서는 토큰은 단어 및 문장 부호 표시 합니다. 토큰의 종류는 다음과 같습니다.  
  
|토큰 이름|토큰 형식|  
|----------------|----------------|  
|네임 스페이스, 클래스, public void int|keyword|  
|=|연산자|  
|{ } ( ) ;|구분 기호|  
|MyNamespace "," MyClass "," MyFunction "," arg1 "," var1|식별자|  
|MyNamespace|네임스페이스(namespace)|  
|MyClass|클래스|  
|MyFunction|메서드|  
|arg1|매개 변수|  
|var1|지역 변수|  
  
 파서가 역할에서 토큰을 식별 하는 것입니다. 일부 토큰이 여러 개 사용할 수 있습니다. 파서가 토큰을 지정 하면 후 구문 강조 표시 하는 등의 유용한 기능 중괄호 일치를 제공 하는 정보 및 IntelliSense 작업 언어 서비스 사용할 수 있습니다.  
  
## <a name="types-of-parsers"></a>파서 형식  
 언어 서비스 파서 컴파일러의 일환으로 사용 하는 파서 같지는 않습니다. 그러나 이러한 종류의 파서 컴파일러 파서 같은 방식에서 스캐너와 한 파서를 사용 해야 합니다.  
  
-   스캐너 토큰 유형을 식별 하는 데 사용 됩니다. 이 정보는 중괄호와 일치 하는 예를 들어, 다른 작업을 트리거할 수 있는 토큰 유형을 신속 하 게 식별 하 고 구문 강조에 사용 됩니다. 이 스캐너로 표시 됩니다는 <xref:Microsoft.VisualStudio.Package.IScanner> 인터페이스입니다.  
  
-   파서 토큰의 범위와 함수를 설명 하는 데 사용 됩니다. 이 정보는 메서드, 변수, 매개 변수, 선언 등의 언어 요소를 식별 하 고 멤버 및 컨텍스트에 따라 메서드 시그니처의 목록을 제공 하 IntelliSense 작업에 사용 됩니다. 중괄호 등 괄호 짝이 되는 언어 요소 쌍을 찾으려고이 파서도 사용 됩니다. 이 파서 통해 액세스 되는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스입니다.  
  
 구현 하는 방법은 스캐너 및 파서 언어 서비스에 대 한 사용자의 책임입니다. 사용할 수 있는 몇 가지 리소스가 파서 작동 하는 방식 및 자체 파서를 작성 하는 방법을 설명 하는 합니다. 또한 다양 한 무료 및 상용 제품은 사용할 수 있는 한 파서를 만드는 데 도움이 되는 합니다.  
  
### <a name="the-parsesource-parser"></a>ParseSource 파서  
 (여기서는 토큰으로 변환 됩니다 실행 코드의 몇 가지 형태) 컴파일러의 일환으로 사용 되는 한 파서와 달리 언어 서비스 파서 다양 한 이유로 및 여러 다른 컨텍스트에서 호출할 수 있습니다. 이 접근 방식을 구현 하는 방법은 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스는 사용자의 책임입니다. 유의 해야 하는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 백그라운드 스레드에서 메서드를 호출할 수 있습니다.  
  
> [!CAUTION]
>  <xref:Microsoft.VisualStudio.Package.ParseRequest> 에 대 한 참조를 포함 하는 구조는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 개체입니다. 이 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 백그라운드 스레드에서 개체를 사용할 수 없습니다. 사실, 여러 기본 MPF 클래스는 백그라운드 스레드에서 사용할 수 없습니다. 여기에 <xref:Microsoft.VisualStudio.Package.Source>, <xref:Microsoft.VisualStudio.Package.ViewFilter>, <xref:Microsoft.VisualStudio.Package.CodeWindowManager> 클래스 및 직접 또는 간접적으로 보기와 통신 하는 다른 클래스입니다.  
  
 이 파서 일반적으로 구문 분석 하는 호출 또는 구문 분석의 값을 설명 하는 경우 전체 소스 파일 첫 번째 시간 <xref:Microsoft.VisualStudio.Package.ParseReason> 제공 됩니다. 에 대 한 후속 호출에서 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드 구문 분석된 된 코드의 일부만 처리 하 고 이전 전체 구문 분석 작업의 결과 사용 하 여 훨씬 더 빠르게 실행할 수 있습니다. <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 통해 구문 분석 작업의 결과 전송 하는 메서드는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 및 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 개체입니다. <xref:Microsoft.VisualStudio.Package.AuthoringSink> 개체는 특정 이유로 구문 분석, 범위에 대 한 내용은 예를 들어 중괄호 또는 매개 변수 목록을 메서드 시그니처를 일치 하는 정보를 수집 하는 데 사용 됩니다. <xref:Microsoft.VisualStudio.Package.AuthoringScope> 선언 및 메서드 서명을 및 지원 컬렉션 이동 하는 고급 편집 옵션 제공 (**정의로 이동**, **선언으로 이동**, **로 이동 참조**).  
  
### <a name="the-iscanner-scanner"></a>IScanner 스캐너  
 구현 하는 스캐너 구현 해야 <xref:Microsoft.VisualStudio.Package.IScanner>합니다. 그러나이 스캐너 통해 줄 단위 별로 작동 하기 때문에 <xref:Microsoft.VisualStudio.Package.Colorizer> 은 일반적으로 쉽게 구현할 수 없는 클래스입니다. 각 줄의 시작 부분에서의 MPF 제공는 <xref:Microsoft.VisualStudio.Package.Colorizer> 클래스 스캐너에 전달 되는 상태 변수도 사용할 값입니다. 각 줄의 끝 스캐너 업데이트 상태 변수를 반환합니다. MPF는 스캐너 소스 파일의 시작 부분에서 시작할 필요 없이 모든 행에서 구문 분석을 시작할 수 있도록 각 줄에 대 한이 상태 정보를 캐시 합니다. 한 줄의 빠른 검색이 편집기를에 사용자에 게 빠른 피드백을 제공할 수 있습니다.  
  
## <a name="parsing-for-matching-braces"></a>일치 하는 중괄호에 대 한 구문 분석  
 이 예제에서는 사용자가 입력 한 닫는 중괄호 일치에 대 한 제어 흐름을 보여 줍니다. 이 프로세스에서는 토큰 및 토큰이 중괄호 일치 작업을 트리거할 수 있는지 여부의 유형을 결정 하도록 색 지정에 사용 되는 스캐너도 사용 됩니다. 트리거를 찾을 경우는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드 일치 하는 중괄호 찾기 위해 호출 됩니다. 마지막으로, 두 개의 중괄호 강조 표시 됩니다.  
  
 트리거의 이름에서 사용 하 고 이유를 구문 분석 하는 중괄호를 하는 경우에이 프로세스는 실제 중괄호에 제한이 없습니다. 문자를 일치 하는 하도록 지정 된 쌍의 쌍으로 된 사용할 수 있습니다. 예로 (및) \< 및 >, 및 [및].  
  
 언어 서비스는 중괄호를 지원 한다는 가정 합니다.  
  
1.  사용자는 닫는 중괄호 (})을 입력 합니다.  
  
2.  커서가 씩 이동, 중괄호는 소스 파일에 커서 위치에 삽입 됩니다.  
  
3.  <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 형식화 된 닫는 중괄호와 함께 클래스 라고 합니다.  
  
4.  <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> 메서드 호출의 <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 클래스 위치 커서의 현재 위치 바로 앞에 토큰을 가져옵니다. 이 토큰은 형식의 닫는 중괄호에 해당).  
  
    1.  <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> 메서드 호출의 <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.Colorizer> 개체를 현재 줄에서 모든 토큰을 가져옵니다.  
  
    2.  <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> 메서드 호출의 <xref:Microsoft.VisualStudio.Package.IScanner.SetSource%2A> 메서드를는 <xref:Microsoft.VisualStudio.Package.IScanner> 현재 줄의 텍스트를 가진 개체입니다.  
  
    3.  <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> 메서드를 반복적으로 호출는 <xref:Microsoft.VisualStudio.Package.IScanner.ScanTokenAndProvideInfoAboutIt%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.IScanner> 개체를 현재 줄에서 모든 토큰을 수집 합니다.  
  
    4.  <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> 에서 개인 메서드를 호출 하는 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 를 원하는 위치를 포함 하는 토큰을 가져올 클래스 및 토큰 목록에서 단계에서 얻은 <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> 메서드.  
  
5.  <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> 의 토큰 트리거 플래그에 대 한 메서드를 찾습니다 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 에서 반환 되는 토큰에는 <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> 방법으로, 즉, 닫는 중괄호를 나타내는 토큰)입니다.  
  
6.  트리거 플래그의 경우 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 발견 되는 <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 클래스 라고 합니다.  
  
7.  <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> 메서드 구문 분석 이유 값으로 구문 분석 작업 시작 <xref:Microsoft.VisualStudio.Package.ParseReason>합니다. 이 작업을 최종적으로 호출 하는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스입니다. 비동기 구문 분석을 사용 하는 경우이 호출 하 여 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드 백그라운드 스레드에서 발생 합니다.  
  
8.  구문 분석 작업이 완료 되 면, 명명 된 한 내부 완료 처리기 (콜백 메서드) `HandleMatchBracesResponse` 에서 호출 되는 <xref:Microsoft.VisualStudio.Package.Source> 클래스입니다. 이 호출에서 자동으로 <xref:Microsoft.VisualStudio.Package.LanguageService> 하지 파서에 의해 기본 클래스입니다.  
  
9. `HandleMatchBracesResponse` 메서드 가져옵니다에서 범위 목록에는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 에 저장 된 개체는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체입니다. (범위는는 <xref:Microsoft.VisualStudio.TextManager.Interop.TextSpan> 소스 파일의 줄 및 문자 범위를 지정 하는 구조입니다.) 이 범위 목록에는 일반적으로 여는 태그와 닫는 중괄호에 대해 각각 하나씩 두 개의 범위를 포함합니다.  
  
10. `HandleBracesResponse` 메서드 호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A> 메서드를는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 에 저장 된 개체는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체입니다. 지정 된 범위를 강조 표시 합니다.  
  
11. 경우는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 속성 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A> 를 사용 하는 `HandleBracesResponse` 메서드는 일치 하는 범위에 포함 되 고 해당 범위의 처음 80 자로 상태 표시줄에 표시 하는 텍스트를 가져옵니다. 이 작업은 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드에 일치 하는 쌍을 포함 하는 언어 요소를 포함 합니다. 자세한 내용은 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A> 속성을 참조하세요.  
  
12. 이 작업을 수행 합니다.  
  
### <a name="summary"></a>요약  
 일치 하는 중괄호 작업 하는 언어 요소의 단순 쌍 일반적으로 제한 됩니다. 삼중 쌍 일치와 같은 보다 복잡 한 요소 ("`if(...)`","`{`"및"`}`", 또는 "`else`","`{`"및"`}`"), 단어 완성 작업의 일부로 강조 표시할 수 있습니다. 예를 들어 "else" 단어 완료 되 면, 일치 하는 "`if`" 문을 강조 표시할 수 있습니다. 일련의 되었으면 `if` / `else if` 문을 모두 일치 하는 중괄호와 같은 메커니즘을 사용 하 여 강조 표시할 수 없습니다. <xref:Microsoft.VisualStudio.Package.Source> 기본 클래스 이미이 다음과 같은 지원: 스캐너 토큰 트리거 값을 반환 해야 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 트리거 값과 함께 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 커서 위치 앞에 있는 토큰에 대 한 합니다.  
  
 자세한 내용은 참조 [레거시 언어 서비스에서 중괄호 일치](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)합니다.  
  
## <a name="parsing-for-colorization"></a>색 지정에 대 한 구문 분석  
 소스 코드의 색을 지정 하는 것은 간단, 방금 해당 형식에 대 한 색 토큰 및 반환 정보 유형을 식별 합니다. <xref:Microsoft.VisualStudio.Package.Colorizer> 클래스의 모든 토큰에 대 한 색상 정보를 제공 하기 위해 편집기와 스캐너 간의 중개자 역할입니다. <xref:Microsoft.VisualStudio.Package.Colorizer> 클래스에서 사용 하는 <xref:Microsoft.VisualStudio.Package.IScanner> 개체에는 줄의 색을 지정 하 고 소스 파일의 모든 줄에 대 한 상태 정보를 수집 합니다. MPF 언어 서비스 클래스에는 <xref:Microsoft.VisualStudio.Package.Colorizer> 클래스에 스캐너와 통신 하기 때문에 재정의할 수 없는 통해서만 <xref:Microsoft.VisualStudio.Package.IScanner> 인터페이스입니다. 구현 하는 개체를 제공 하는 <xref:Microsoft.VisualStudio.Package.IScanner> 재정의 하 여 인터페이스는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스 합니다.  
  
 <xref:Microsoft.VisualStudio.Package.IScanner> 스캐너를 통해 소스 코드의 줄을 제공 되는 <xref:Microsoft.VisualStudio.Package.IScanner.SetSource%2A> 메서드. 에 대 한 호출이 <xref:Microsoft.VisualStudio.Package.IScanner.ScanTokenAndProvideInfoAboutIt%2A> 메서드 된 토큰을 가져오는 다음 줄에서 토큰의 줄 가득 찰 때까지 반복 됩니다. 색을 조정할 MPF는 모든 소스 코드 줄의 시퀀스로 처리합니다. 따라서 스캐너에 선으로 들어오는 소스에 대처 하기 위해 수 있어야 합니다. 또한 언제 든 지 모든 줄 스캐너에 전달 될 수 이며 규칙만 스캐너를 검색 하 여 줄 앞에 줄에서 상태 변수를 받습니다.  
  
 <xref:Microsoft.VisualStudio.Package.Colorizer> 클래스는 토큰 트리거를 식별 하는 데도 사용 됩니다. 이 트리거는 MPF 특정 토큰이 단어 완성 등의 보다 복잡 한 작업을 시작할 수 있음을 알려 또는 중괄호 일치 합니다. 이러한 트리거 식별 더 빨리 서 모든 위치에서 발생 해야 하기 때문 스캐너는이 작업에 가장 적합 합니다.  
  
 자세한 내용은 참조 [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)합니다.  
  
## <a name="parsing-for-functionality-and-scope"></a>기능 및 범위에 대 한 구문 분석  
 기능 및 범위에 대 한 구문 분석만 유형을 식별 하 고 발생 하는 토큰의 보다 더 많은 노력이 필요 합니다. 파서 토큰 유형 뿐만 아니라 토큰을 사용 하는 기능을 식별 하는 있습니다. 예를 들어 식별자 단순한 이름 이지만 식별자의 클래스, 네임 스페이스, 메서드 또는 컨텍스트에 따라 변수 이름을 언어에서 일 합니다. 토큰의 일반 형식은 식별자가 될 수 있습니다 하지만 식별자 무엇 인지에 따라 및 정의 된 다른 의미를 갖게 될 수 있습니다. 이 id를 구문 분석 되는 언어에 대 한 보다 광범위 한 지식이 파서가 필요 합니다. 여기에는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 클래스 제공 합니다. <xref:Microsoft.VisualStudio.Package.AuthoringSink> 식별자, 메서드, (예: 중괄호, 괄호)를 일치 하는 언어 쌍 및 언어 삼중 쌍을 포함 하는 방법에 대 한 정보를 수집 하는 클래스 (유사 하지만 언어 쌍 제외 된다는 세 가지 부분은, 예를 들어 "`foreach()`" "`{`"및"`}`"). 또한 재정의할 수 있습니다는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 디버거 로드할 보유 하지 않는 중단점의 초기 유효성 검사에 사용 되는 코드 id를 지원 하기 위해 클래스 및 **자동** 로컬 보여 주는 디버깅 창 변수 및 매개 변수 자동으로 프로그램 디버깅 되 고 시점과 적절 한 지역 변수 및 디버거를 표시 하는 것 외에 매개 변수를 식별 하려면 파서가 필요 합니다.  
  
 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 개체의 일부로 파서에 전달 됩니다는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체 및 새 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 개체는 생성 될 때마다 새 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체가 만들어집니다. 또한는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드 반환 해야 합니다는 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 다양 한 IntelliSense 작업을 처리 하는 데 사용 되는 개체입니다. <xref:Microsoft.VisualStudio.Package.AuthoringScope> 개체 유지 관리 선언에 대 한 목록 및 방법에 대 한 목록 중 하나는 채워진 구문 분석을 위한 이유에 따라 합니다. <xref:Microsoft.VisualStudio.Package.AuthoringScope> 클래스를 구현 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스를 구현합니다.](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [레거시 언어 서비스 개요](../../extensibility/internals/legacy-language-service-overview.md)   
 [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)   
 [레거시 언어 서비스의 중괄호 일치](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)
