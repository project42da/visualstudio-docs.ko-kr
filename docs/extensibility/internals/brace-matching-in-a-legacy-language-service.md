---
title: "중괄호 일치 레거시 언어 서비스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "중괄호 일치"
  - "언어 서비스 [관리 되는 패키지 프레임 워크] 중괄호 일치"
ms.assetid: 4e3d0a70-f22f-49dd-92d8-edf48ab62b52
caps.latest.revision: 27
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 27
---
# 중괄호 일치 레거시 언어 서비스
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

중괄호 일치 함께 괄호 및 중괄호 처럼 발생 해야 하는 언어 요소를 추적 하는 개발자는 데 도움이 됩니다. 개발자가 닫는 중괄호를 여는 중괄호 강조 표시 됩니다.  
  
 쌍과 삼중 쌍 이라는 두 가지 또는 세 개의 동시 발생 요소를 일치 시킬 수 있습니다. 삼중 쌍은 세 동시 발생 요소의 집합입니다. 예를 들어 C\#에서 `foreach` 삼중 쌍을 형성 하는 문: "`foreach()`","`{`", 및 "`}`"입니다. 세 요소 모두에 닫는 중괄호를 입력할 때 강조 표시 됩니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 중괄호 일치를 구현 하는 새로운 방법에 대 한 자세한 내용을 참조 하십시오 [연습: 일치 하는 중괄호를 표시합니다.](../../extensibility/walkthrough-displaying-matching-braces.md)합니다.  
  
> [!NOTE]
>  새 편집기 API를 최대한 빨리 사용을 시작 하는 것이 좋습니다. 이 언어 서비스의 성능을 향상 하 고 새로운 편집기 기능을 이용할 수 있도록 합니다.  
  
 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 클래스 모두 쌍을 지원 하며와 데이터 집합을 가져와 <xref:Microsoft.VisualStudio.Package.AuthoringSink.MatchPair%2A> 및 <xref:Microsoft.VisualStudio.Package.AuthoringSink.MatchTriple%2A> 메서드.  
  
## 구현  
 언어 서비스는 언어에서 일치 하는 모든 요소를 식별 하 고 다음 모든 일치 하는 쌍을 찾이 필요 합니다. 구현 하 여 일반적으로 이렇게 <xref:Microsoft.VisualStudio.Package.IScanner> 일치 하는 언어와 다음 사용 하 여 검색 하는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 요소와 일치 하는 방법입니다.  
  
 <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> 줄 토큰화 캐럿 바로 전에 토큰을 반환 하는 스캐너 메서드를 호출 합니다. 스캐너 토큰 트리거 값을 설정 하 여 언어 요소 쌍을 찾았으면 나타냅니다 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 현재 토큰에 있습니다.<xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> 메서드 호출의 <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> 메서드를 호출 하 여는 <xref:Microsoft.VisualStudio.Package.LanguageService.BeginParse%2A> 구문 분석 이유 값을 사용 하 여 메서드 <xref:Microsoft.VisualStudio.Package.ParseReason> 일치 하는 언어 요소를 찾습니다. 일치 하는 언어 요소가 발견 되 면 두 요소 모두 강조 표시 됩니다.  
  
 참조 항목의 "예제 구문 분석 작업" 섹션에 대 한 전체 설명은 어떻게 괄호를 입력을 트리거합니다 중괄호 강조 표시, [레거시 언어 서비스 파서 및 검사](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)합니다.  
  
## 중괄호 일치에 대 한 지원을 사용 하도록 설정  
 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 특성을 설정할 수는 `MatchBraces`, `MatchBracesAtCaret`, 및 `ShowMatchingBrace` 명명 된 해당 속성을 설정 하는 매개 변수는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 클래스입니다. 사용자가 언어 기본 설정 속성을 설정할 수도 있습니다.  
  
|레지스트리 항목|속성|설명|  
|--------------|--------|--------|  
|`MatchBraces`|<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableMatchBraces%2A>|활성화 중괄호 일치|  
|`MatchBracesAtCaret`|<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableMatchBracesAtCaret%2A>|이동 캐럿으로 중괄호 일치를 사용 하도록 설정 합니다.|  
|`ShowMatchingBrace`|<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A>|일치 하는 중괄호를 강조 표시합니다.|  
  
## 일치 하는 조건문  
 와 같은 조건문을 일치 시킬 수 `if`, `else if`, 및 `else`, 또는 `#if`, `#elif`, `#else`, `#endif`, 구분 기호 일치와 같은 방식에서입니다. 서브클래싱 할 수는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 클래스와 일치 하는 요소 내부 배열에 대 한 구분 기호 뿐 아니라 걸쳐 있는 텍스트를 추가할 수 있는 메서드를 제공 합니다.  
  
## 트리거 설정  
 다음 예제에서는 일치 하는 괄호와 중괄호 및 대괄호, 그리고 스캐너에서에 대 한 트리거를 설정 하는 방법을 보여 줍니다.<xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 클래스는 트리거를 검색 하 고 \(이 항목의 "일치 찾기" 섹션 참조\) 일치 하는 쌍을 찾을 파서를 호출 합니다. 이 예는 설명 목적 으로만 제공 됩니다. 스캐너는 메서드가 포함 되어 있음을 가정 `GetNextToken` 식별 하 고 텍스트 줄에서 토큰을 반환 합니다.  
  
```c#  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestScanner : IScanner  
    {  
        private const string braces = "()[]{}";  
        private Lexer lex;  
  
        public bool ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo,  
                                                   ref int state)  
        {  
            bool foundToken = false;  
            string token = lex.GetNextToken();  
            if (token != null)  
            {  
                foundToken = true;  
                char firstChar = token[0];  
                if (Char.IsPunctuation(firstChar) && token.Length > 0)  
                {  
                    if (braces.IndexOf(firstChar) != -1)  
                    {  
                        tokenInfo.Trigger = TokenTriggers.MatchBraces;  
                    }  
                }  
            }  
            return foundToken;  
        }  
```  
  
## 중괄호 일치  
 다음은 언어 요소 {}, \(,\) 및, 일치 하 고 해당 범위를 추가 하는 간소화 된 예제는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 개체입니다. 이 방법은 소스 코드를 구문 분석 하는 것이 좋습니다 하지 않습니다. 설명 목적 으로만 제공 됩니다.  
  
```c#  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class Parser  
    {  
         private IList<TextSpan[]> m_braces;  
         public IList<TextSpan[]> Braces  
         {  
             get { return m_braces; }  
         }  
         private void AddMatchingBraces(TextSpan braceSpan1, TextSpan braceSpan2)  
         {  
             if IsMatch(braceSpan1, braceSpan2)  
                 m_braces.Add(new TextSpan[] { braceSpan1, braceSpan2 });  
         }  
  
         private bool IsMatch(TextSpan braceSpan1, TextSpan braceSpan2)  
         {  
             //definition for matching here  
          }  
    }  
  
    public class TestLanguageService : LanguageService  
    {  
         Parser parser = new Parser();  
         Source source = (Source) this.GetSource(req.FileName);  
  
         private AuthoringScope ParseSource(ParseRequest req)  
         {  
             if (req.Sink.BraceMatching)  
             {  
                 if (req.Reason==ParseReason.MatchBraces)  
                 {  
                     foreach (TextSpan[] brace in parser.Braces)  
                     {  
                         req.Sink.MatchPair(brace[0], brace[1], 1);  
                     }  
                 }  
             }  
             return new TestAuthoringScope();  
         }  
    }  
}  
```  
  
## 참고 항목  
 [레거시 언어 서비스 기능](../../extensibility/internals/legacy-language-service-features1.md)   
 [레거시 언어 서비스 파서 및 검사](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)