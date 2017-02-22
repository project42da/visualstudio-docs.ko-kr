---
title: "레거시 언어 서비스의 매개 변수 정보 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IntelliSense, 매개 변수 정보 도구 설명"
  - "언어 서비스 [관리 되는 패키지 프레임 워크] IntelliSense 매개 변수 정보"
  - "언어 서비스 [관리 되는 패키지 프레임 워크]에서 지 원하는 매개 변수 정보 (IntelliSense)"
ms.assetid: a117365d-320d-4bb5-b61d-3e6457b8f6bc
caps.latest.revision: 23
caps.handback.revision: 23
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 언어 서비스의 매개 변수 정보
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

IntelliSense 매개 변수 정보는 사용자가 매개 변수 목록 메서드 시그니처를 표시 하는 도구 설명이 메서드 매개 변수 목록에 대 한 문자 \(일반적으로 여는 괄호\)를 시작 합니다. 각 매개 변수를 입력 하 고 매개 변수 구분 기호 \(쉼표\)를 입력, 도구 설명에 표시할 굵게 표시 된 다음 매개 변수를 표시 하도록 업데이트 됩니다.  
  
 매개 변수 정보 도구 설명 관리 하기 위한 지원을 제공 하는 관리 되는 패키지 \(MPF\) 프레임 워크 클래스. 매개 변수를 매개 변수 다음에 시작한 매개 변수 끝 문자 이므로 메서드 서명과 연결 된 매개 변수 목록을 제공 해야 파서가 감지 해야 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 자세한 내용을 참조 하십시오 [편집기 및 언어 서비스 확장](../../extensibility/extending-the-editor-and-language-services.md)합니다.  
  
> [!NOTE]
>  새 편집기 API를 최대한 빨리 사용을 시작 하는 것이 좋습니다. 이 언어 서비스의 성능을 향상 하 고 새로운 편집기 기능을 이용할 수 있도록 합니다.  
  
## 구현  
 트리거 값을 설정 해야 하는 파서는 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 매개 변수 목록 시작 문자 \(대개는 괄호\)를 발견 하면 설정 됩니다. 설정 해야는 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 매개 변수 구분 기호 \(쉼표 종종\)를 발견 하면 발생 합니다. 그러면 업데이트를 굵게 표시 된 다음 매개 변수를 표시 합니다. 매개 변수 정보 도구 설명 합니다. 파서는 트리거 값을 설정 해야 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 때 경우 매개 변수 목록 끝 문자 \(종종 닫는 괄호\)를 찾습니다.  
  
 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 트리거 값에 대 한 호출을 시작는 <xref:Microsoft.VisualStudio.Package.Source.MethodTip%2A> 메서드를 호출 하는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 의 구문 분석 이유인 메서드 파서 <xref:Microsoft.VisualStudio.Package.ParseReason>합니다. 에 메서드 서명을 일치 하는 목록을 반환 파서는 매개 변수 목록에는 문자 시작 전에 식별자가 인식 된 메서드 이름에서 결정 된 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 개체입니다. 메서드 시그니처의 모든 발견 된 경우 목록에서 첫 번째 서명을 사용 하 여 매개 변수 정보 도구 설명 표시 됩니다. 이 도구 설명 서명의 더은 입력으로 업데이트 됩니다. 매개 변수 목록 끝 문자를 입력할 때 매개 변수 정보 도구 설명에 표시할 보기에서 제거 됩니다.  
  
> [!NOTE]
>  매개 변수 정보 도구 설명 하는 올바른 형식의 위해이 속성에서 재정의 해야는 <xref:Microsoft.VisualStudio.Package.Methods> 적절 한 문자를 제공 하는 클래스입니다. 기본 <xref:Microsoft.VisualStudio.Package.Methods> 클래스 가정 하는 C\#\-스타일 메서드 시그니처입니다. 참조는 <xref:Microsoft.VisualStudio.Package.Methods> 수 수행 방법에 대 한 세부 정보에 대 한 클래스입니다.  
  
## 매개 변수 정보에 대 한 지원을 사용 하도록 설정  
 를 지원 하기 위해 매개 변수 정보 도구 설명 설정 해야는 `ShowCompletion` 라는 매개 변수는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 를 `true`합니다. 언어 서비스에서이 레지스트리 항목의 값을 읽고는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A> 속성입니다.  
  
 또한는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.ParameterInformation%2A> 속성으로 설정 되어 있어야 `true` 매개 변수 정보 도구 설명으로 표시 됩니다.  
  
### 예제  
 매개 변수 목록 문자를 검색 하 고 적절 한 트리거를 설정 하는 간단한 예는 다음과 같습니다. 이 예는 설명 목적 으로만 제공 됩니다. 스캐너는 메서드가 포함 되어 있음을 가정 `GetNextToken` 식별 하 고 텍스트 줄에서 토큰을 반환 합니다. 예제 코드는 단순히 적합 한 종류의 문자가 발견 될 때마다 트리거를 설정 합니다.  
  
```c#  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestScanner : IScanner  
    {  
        private Lexer lex;  
        private const char parameterListStartChar = '(';  
        private const char parameterListEndChar   = ')';  
        private const char parameterNextChar      = ',';  
  
        public bool ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo,  
                                                   ref int state)  
        {  
            bool foundToken = false  
            string token = lex.GetNextToken();  
            if (token != null)  
            {  
                foundToken = true;  
                char c = token[0];  
                if (Char.IsPunctuation(c))  
                {  
                    tokenInfo.Type = TokenType.Operator;  
                    tokenInfo.Color = TokenColor.Keyword;  
                    tokenInfo.EndIndex = index;  
  
                    if (c == parameterListStartChar)  
                    {  
                        tokenInfo.Trigger |= TokenTriggers.ParameterStart;  
                    }  
                    else if (c == parameterListNextChar)  
                    {  
                        tokenInfo.Trigger |= TokenTriggers.ParameterNext;  
                    else if (c == parameterListEndChar)  
                    {  
                        tokenInfo.Trigger |= TokenTriggers.ParameterEnd;  
                    }  
                }  
            return foundToken;  
        }  
    }  
}  
```  
  
## 파서에서 매개 변수 정보 도구 설명 지원  
 <xref:Microsoft.VisualStudio.Package.Source> 클래스의 내용에 대 한 몇 가지 가정을 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 및 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 클래스가 때 매개 변수 정보 도구 설명에 표시 되 고 업데이트 합니다.  
  
-   파서는 제공할지 <xref:Microsoft.VisualStudio.Package.ParseReason> 매개 변수 목록 시작 문자를 입력 하는 경우.  
  
-   지정 된 위치는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체는 매개 변수 목록에는 문자 시작 직후입니다. 파서는 수집 하 여 이동 하 고 사용 중인 버전에서 목록에 저장 하는에서 사용할 수 있는 모든 메서드 선언의 서명에 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 개체입니다. 이 목록은 메서드 이름, 메서드 형식 \(또는 반환 형식\) 및 가능한 매개 변수 목록이 있습니다. 이 목록은 메서드 서명이 나 서명에 매개 변수 정보 도구 설명에 표시할 나중에 검색 됩니다.  
  
 파서는 지정한 줄 다음 구문 분석 해야는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 사용자 얼마나 진행 뿐만 아니라 입력 되는 메서드의 이름을 수집 하는 개체는 매개 변수를 입력 합니다. 메서드의 이름을 전달 하 여 이렇게는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartName%2A> 메서드를는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 개체와 다음 호출의 <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartParameters%2A> 메서드 매개 변수 목록 시작 문자는 구문 분석 호출는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.NextParameter%2A> 메서드는 매개 변수 목록 다음 문자를 구문 분석할 때 마지막으로 호출 하는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.EndParameters%2A> 메서드는 매개 변수 목록 끝 문자를 구문 분석할 때. 이러한 메서드 호출의 결과에서 사용 되는 <xref:Microsoft.VisualStudio.Package.Source> 매개 변수 정보 도구 설명에 적절 하 게 업데이트 하는 클래스입니다.  
  
### 예제  
 사용자가 입력 하는 텍스트의 줄은 다음과 같습니다. 선 아래 숫자 파서에서 \(구문 분석 이동 합니다. 왼쪽에서 오른쪽으로 가정\) 행에 해당 위치에 있는 단계를 수행 하는 것을 나타냅니다. 여기 가정 하는 줄 앞에 나오는 모든 이미 구문 분석 되었습니다 "testfunc" 메서드 시그니처를 포함 하는 메서드 서명에 대입니다.  
  
```  
testfunc("a string",3);  
     ^^          ^ ^  
     12          3 4  
```  
  
 파서를 사용 하는 단계는 다음과 같습니다.  
  
1.  파서를 호출 하 여 <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartName%2A> "testfunc" 텍스트와 함께 합니다.  
  
2.  파서를 호출 하 여 <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartParameters%2A>합니다.  
  
3.  파서를 호출 하 여 <xref:Microsoft.VisualStudio.Package.AuthoringSink.NextParameter%2A>합니다.  
  
4.  파서를 호출 하 여 <xref:Microsoft.VisualStudio.Package.AuthoringSink.EndParameters%2A>합니다.