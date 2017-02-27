---
title: "레거시 언어 서비스의 구문 색 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "언어 서비스 [관리 되는 패키지 프레임 워크] 구문 강조 표시"
  - "언어 서비스 [관리 되는 패키지 프레임 워크]에서 지 원하는 색 지정"
  - "강조 표시, 언어 서비스 [관리 되는 패키지 프레임 워크]에서 지 원하는 구문"
  - "언어 서비스 [관리 되는 패키지 프레임 워크], 색 지정"
ms.assetid: 1ca1736a-f554-42e4-a9c7-fe8c3c1717df
caps.latest.revision: 28
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 28
---
# 레거시 언어 서비스의 구문 색 지정
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

구문 색 지정은 서로 다른 색 및 스타일에 있는 원본 파일에 표시 되는 프로그래밍 언어의 다양 한 요소를 발생 시키는 기능입니다. 이 기능을 지원 하려면 파서 또는 어휘 요소 또는 파일에는 토큰의 종류를 식별할 수 있는 스캐너를 제공 해야 합니다. 다양 한 언어와 다른 방법으로 색을 지정 하 여 키워드, 구분 기호 \(예: 괄호나 중괄호\), 및 메모를 구별 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 자세한 내용을 참조 하십시오 [편집기 및 언어 서비스 확장](../../extensibility/extending-the-editor-and-language-services.md)합니다.  
  
> [!NOTE]
>  새 편집기 API를 최대한 빨리 사용을 시작 하는 것이 좋습니다. 이 언어 서비스의 성능을 향상 하 고 새로운 편집기 기능을 이용할 수 있도록 합니다.  
  
## 구현  
 관리 되는 패키지 프레임 워크 \(MPF\)에 포함 되어 색 지정을 지원 하려면는 <xref:Microsoft.VisualStudio.Package.Colorizer> 클래스를 구현 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 인터페이스입니다. 이 클래스와 상호 작용 하는 <xref:Microsoft.VisualStudio.Package.IScanner> 토큰 및 색을 결정 하 합니다. 스캐너에 대 한 자세한 내용은 참조 하십시오. [레거시 언어 서비스 파서 및 검사](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)합니다.<xref:Microsoft.VisualStudio.Package.Colorizer> 클래스에서 다음 색 정보를 사용 하 여 토큰의 각 문자를 표시 하 고 소스 파일을 표시 하는 편집기에 해당 정보를 반환 합니다.  
  
 편집기에 반환 되는 색 정보는 색 항목 목록에는 인덱스입니다. 각 색 항목 색 값 및 글꼴 특성 집합이 굵게 등 지정 또는 취소선 합니다. 편집기는 기본 언어 서비스에서 사용할 수 있는 색 항목 집합을 제공 합니다. 각 토큰 형식에 대 한 적절 한 색 인덱스를 지정 하면 됩니다. 그러나 토큰을 사용자 지정 색 항목 및 제공 하는 인덱스의 집합을 제공할 수 있으며 기본 목록 대신 색 항목의 고유한 목록을 참조할 수 있습니다. 설정 해야는 `RequestStockColors` 레지스트리 항목을 0으로 \(지정 하지 않으면 또는 `RequestStockColors` 전혀 항목\) 사용자 지정 색을 지원 하도록 합니다. 이 레지스트리 항목을 명명된 된 매개 변수를 설정할 수는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 사용자 정의 특성입니다. 언어 서비스를 등록 하 고 해당 옵션 설정에 대 한 자세한 내용은 참조 하십시오. [언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)합니다.  
  
## 사용자 지정 색 항목  
 사용자 고유의 사용자 지정 색 항목을 제공 하려면 재정의 해야는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetItemCount%2A> 및 <xref:Microsoft.VisualStudio.Package.LanguageService.GetColorableItem%2A> 메서드는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스입니다. 첫 번째 방법은 언어 서비스에서 지 원하는 사용자 지정 색 항목 수를 반환 하 고 두 번째 인덱스 별로 사용자 지정 색 항목을 가져옵니다. 사용자 지정 색 항목의 기본 목록을 만듭니다. 언어 서비스의 생성자에서 각 색 항목 이름으로 제공 하기만 하면 됩니다. Visual Studio는 자동으로 사용자가 다양 한 색을 선택 하는 위치 하는 경우를 처리 합니다. 이 이름이 표시 됩니다는 **글꼴 및 색** 속성 페이지에는 **옵션** 대화 상자 \(Visual Studio에서 사용할 수 있는 **도구** 메뉴\)이이 이름을 재정의 사용자는 색을 결정 합니다. 사용자의 선택 레지스트리에 캐시에 저장 되 고 색 이름으로 액세스 합니다.**글꼴 및 색** 언어 이름으로 사용 하 여 각 색 이름을 시작 하 여 사용자 지정 색을 그룹화 할 수 있도록 모든 알파벳 순서로 색 이름을 속성 페이지 나열 예를 들어 "**TestLanguage 주석**"및"**TestLanguage\-키워드**"입니다. 또는 색 항목 유형별로 그룹화 할 수 있습니다 "**메모 \(TestLanguage\)**"및"**키워드 \(TestLanguage\)**"입니다. 언어 이름으로 그룹화 것이 좋습니다.  
  
> [!CAUTION]
>  기존 색 항목 이름의 충돌을 방지 하기 색 항목 이름에 언어 이름을 포함 하는 것이 좋습니다.  
  
> [!NOTE]
>  개발 하는 동안 색 중 하나의 이름을 변경 하면 Visual Studio 처음으로 액세스 된 색을 생성 하는 캐시를 다시 설정 해야 합니다. 실행 하 여 수행할 수는 **실험 하이브 재설정** Visual Studio SDK 프로그램 메뉴에서 명령입니다.  
  
 색 항목 첫 번째 항목 목록에서 참조 되지 않는 참고 합니다. Visual Studio는 항상 기본 텍스트 색과 해당 항목에 대 한 특성에 제공합니다. 이 처리 하는 첫 번째 항목으로 자리 표시자 색 항목을 제공 하는 가장 쉬운 방법은 합니다.  
  
### 하이 컬러 색 항목  
 색 항목을 통해 24 비트 또는 높은 색상 값 기능도 사용할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> 인터페이스입니다. MPF <xref:Microsoft.VisualStudio.Package.ColorableItem> 클래스는 지원의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> 인터페이스 및 24 비트 색은 기본 색과 함께 생성자에 지정 됩니다. 참조는 <xref:Microsoft.VisualStudio.Package.ColorableItem> 대 한 자세한 내용은 클래스입니다. 아래 예제에서는 24 비트 색 키워드 및 메모를 설정 하는 방법을 보여 줍니다. 사용자의 데스크톱;에서 지원 되는 24 비트 색 24 비트 색은 사용 그렇지 않은 경우 일반 텍스트 색이 사용 됩니다.  
  
 언어;에 대 한 기본 색입니다. 사용자는 원하는 대로 자유롭게이 색상을 변경할 수 있습니다.  
  
### 예제  
 선언 하 고 사용 하 여 사용자 지정 색 항목 배열을 채울 하는 방법을 보여 주는이 예제는 <xref:Microsoft.VisualStudio.Package.ColorableItem> 클래스입니다. 이 예에서는 24 비트 색을 사용 하는 키워드와 주석 색을 설정 합니다.  
  
```c#  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        private ColorableItem[] m_colorableItems;  
  
        TestLanguageService() : base()  
        {  
            m_colorableItems = new ColorableItem[] {  
                new ColorableItem("TestLanguage – Text",  
                                  "Text",  
                                  COLORINDEX.CI_SYSPLAINTEXT_FG,  
                                  COLORINDEX.CI_SYSPLAINTEXT_BK,  
                                  System.Drawing.Color.Empty,  
                                  System.Drawing.Color.Empty,  
                                  FONTFLAGS.FF_DEFAULT),  
                new ColorableItem("TestLanguage – Keyword",  
                                  "Keyword",  
                                  COLORINDEX.CI_MAROON,  
                                  COLORINDEX.CI_SYSPLAINTEXT_BK,  
                                  System.Drawing.Color.FromArgb(192,32,32),  
                                  System.Drawing.Color.Empty,  
                                  FONTFLAGS.FF_BOLD),  
                new ColorableItem("TestLanguage – Comment",  
                                  "Comment",  
                                  COLORINDEX.CI_DARKGREEN,  
                                  COLORINDEX.CI_LIGHTGRAY,  
                                  System.Drawing.Color.FromArgb(32,128,32),  
                                  System.Drawing.Color.Empty,  
                                  FONTFLAGS.FF_DEFAULT)  
                // ...  
                // Add as many colorable items as you want to support.  
            };  
        }  
    }  
}  
```  
  
## 색 지정 기 클래스 및 검사  
 기본 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스에는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetColorizer%2A> 메서드는 instantiantes는 <xref:Microsoft.VisualStudio.Package.Colorizer> 클래스입니다. 반환 되는 스캐너는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> 메서드에 전달 되는 <xref:Microsoft.VisualStudio.Package.Colorizer> 클래스 생성자입니다.  
  
 구현 해야는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> 고유한 버전의 메서드는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스입니다.<xref:Microsoft.VisualStudio.Package.Colorizer> 클래스 스캐너를 사용 하 여 모든 토큰 색 정보를 얻습니다.  
  
 스캐너를 채울 필요는 <xref:Microsoft.VisualStudio.Package.TokenInfo> 구성 된 모든 토큰에 대 한 검색 합니다. 이 구조는 차지 하는 토큰 범위를 색 인덱스를 사용 하 여 같은 정보를 포함 하는 토큰 및 토큰 트리거 유형을 \(참조 <xref:Microsoft.VisualStudio.Package.TokenTriggers>\). 범위 및 색 인덱스에서 색을 조정할 필요는 <xref:Microsoft.VisualStudio.Package.Colorizer> 클래스입니다.  
  
 색 인덱스에 저장 된는 <xref:Microsoft.VisualStudio.Package.TokenInfo> 구조는 값을 일반적으로 <xref:Microsoft.VisualStudio.Package.TokenColor> 키워드 및 연산자와 같은 다양 한 언어 요소에 해당 하는 명명 된 인덱스의 수를 제공 하는 열거형입니다. 사용자 지정 색 항목에 일치 하는 항목 목록에 표시 된 항목의 <xref:Microsoft.VisualStudio.Package.TokenColor> 열거를 사용할 수 있습니다만 열거형 색으로 각 토큰에 대 한 합니다. 그러나 추가 색 항목 또는 그 순서 대로 기존 값을 사용 하지 않으려는 경우 해당 목록에는 적절 한 인덱스를 반환 하 고 필요에 따라 사용자 지정 색 항목 목록에 정렬할 수 있습니다. 인덱스를 캐스팅 그래픽을 <xref:Microsoft.VisualStudio.Package.TokenColor> 에 저장 하는 경우는 <xref:Microsoft.VisualStudio.Package.TokenInfo> 그렇지 [!INCLUDE[vs_current_short](../../code-quality/includes/vs_current_short_md.md)] 인덱스만 게 표시 합니다.  
  
### 예제  
 다음 예제에서는 어떻게 스캐너 토큰 세 가지 종류를 식별할 수 있습니다: 숫자, 문장 부호, 및 식별자 \(이외의 모든 숫자 또는 문장 부호\). 이 예에서는 설명 목적 으로만 제공 되며 포괄적인 파서 및 스캐너 구현을 나타내지 않습니다. 없다는 가정는 `Lexer` 클래스와 `GetNextToken()` 문자열을 반환 하는 메서드입니다.  
  
```c#  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    private Lexer lex;  
  
    public class TestScanner : IScanner  
    {  
        public bool ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo,  
                                                   ref int state)  
        {  
            bool foundToken = false;  
            string token = lex.GetNextToken();  
            if (token != null)  
            {  
                char firstChar = token[0];  
                if (Char.IsPunctuation(firstChar))  
                {  
                    tokenInfo.Type = TokenType.Operator;  
                    tokenInfo.Color = TokenColor.Keyword;  
                }  
                else if (Char.IsNumber(firstChar))  
                {  
                    tokenInfo.Type = TokenType.Literal;  
                    tokenInfo.Color = TokenColor.Number;  
                }  
                else  
                {  
                    tokenInfo.Type = TokenType.Identifier;  
                    tokenInfo.Color = TokenColor.Identifier;  
                }  
            }  
            return foundToken;  
        }  
```  
  
## 참고 항목  
 [레거시 언어 서비스 기능](../../extensibility/internals/legacy-language-service-features1.md)   
 [레거시 언어 서비스 파서 및 검사](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)   
 [언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)