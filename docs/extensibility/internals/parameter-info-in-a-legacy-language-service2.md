---
title: 레거시 언어 Service2에 매개 변수 정보 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense, Parameter Info tool tip
- language services [managed package framework], IntelliSense Parameter Info
- Parameter Info (IntelliSense), supporting in language services [managed package framework]
ms.assetid: a117365d-320d-4bb5-b61d-3e6457b8f6bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6aaf8ba9be9e16eeb979b0d64d3e80e8d70b564f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="parameter-info-in-a-legacy-language-service"></a>레거시 언어 서비스에 대 한 매개 변수 정보
IntelliSense 매개 변수 정보는 다음 사용자가 매개 변수 목록 메서드 시그니처를 표시 하는 도구 설명이 메서드 매개 변수 목록에 대 한 문자 (일반적으로 여는 괄호)를 시작 합니다. 각 매개 변수를 입력 하 고 매개 변수 구분 기호 (쉼표)은 입력을 도구 설명 굵게 표시 된 다음 매개 변수를 표시 하도록 업데이트 됩니다.  
  
 관리 되는 패키지 프레임 워크 (MPF) 클래스는 매개 변수 정보 도구 설명을 관리 하기 위한 지원을 제공 합니다. 매개 변수를 매개 변수 다음으로 시작한 매개 변수 끝 문자 이므로 메서드 서명 및 해당 관련된 매개 변수 목록을 제공 해야 파서가 검색 해야 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 된 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 최신 방법입니다. 자세한 내용을 알아보려면 참조 [편집기 및 언어 서비스 확장](../../extensibility/extending-the-editor-and-language-services.md)합니다.  
  
> [!NOTE]
>  편집기를 사용 하 여 새 API 가능한 한 빨리 시작 하는 것이 좋습니다. 언어 서비스의 성능이 향상 되 고 새 편집기 기능을 이용할 수 있도록 합니다.  
  
## <a name="implementation"></a>구현  
 파서가 트리거 값을 설정 해야 <xref:Microsoft.VisualStudio.Package.TokenTriggers> (종종는 여는 괄호) 매개 변수 목록 시작 문자가 있을 때 설정 됩니다. 설정 해야는 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 매개 변수 구분 기호 (쉼표 종종)를 발견 하면 발생 합니다. 이렇게 하면 업데이트 되 고 굵게 표시 된 다음 매개 변수를 표시 하는 매개 변수 정보 도구 설명 됩니다. 파서가 트리거 값을 설정 해야 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 때 경우 매개 변수 목록 끝 문자 (종종 닫는 괄호)를 찾습니다.  
  
 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 트리거 값 시작에 대 한 호출에서 <xref:Microsoft.VisualStudio.Package.Source.MethodTip%2A> 메서드를 호출 하 여는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 의 구문 분석 이유와 함께 메서드 파서 <xref:Microsoft.VisualStudio.Package.ParseReason>합니다. 에 메서드 서명을 일치 하는 목록을 반환 파서가 매개 변수 목록에는 문자 시작 전에 식별자는 인식 된 메서드 이름으로 결정는 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 개체입니다. 모든 메서드 서명이 발견 될 경우 목록에서 첫 번째 서명을 사용 하 여 매개 변수 정보 도구 설명 표시 됩니다. 이 도구 설명이 서명을 중은 입력으로 업데이트 됩니다. 매개 변수 목록 끝 문자를 입력할 때 매개 변수 정보 도구 설명 보기에서 제거 됩니다.  
  
> [!NOTE]
>  매개 변수 정보 도구 설명 하는 올바른 형식의 위해이 속성에서 재정의 해야는 <xref:Microsoft.VisualStudio.Package.Methods> 적절 한 문자를 제공 하는 클래스입니다. 기본 <xref:Microsoft.VisualStudio.Package.Methods> 클래스 가정 하는 C#-스타일 메서드 서명입니다. 참조는 <xref:Microsoft.VisualStudio.Package.Methods> 이 방법에 대 한 내용은 클래스입니다.  
  
## <a name="enabling-support-for-the-parameter-info"></a>매개 변수 정보에 대 한 지원을 사용 하도록 설정  
 도구 설명 매개 변수 정보를 지원 하려면 설정 해야 합니다는 `ShowCompletion` 명명 된의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 를 `true`합니다. 언어 서비스에서이 레지스트리 항목의 값을 읽고는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A> 속성입니다.  
  
 또한는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.ParameterInformation%2A> 속성으로 설정 되어 있어야 `true` 매개 변수 정보 도구 설명에 표시할 수 있습니다.  
  
### <a name="example"></a>예제  
 매개 변수 목록 문자를 검색 하 고 적절 한 트리거를 설정 하는 간단한 예는 다음과 같습니다. 이 예제는 설명 목적 으로만. 스캐너는 메서드가 포함 되어 있음을 가정 `GetNextToken` 식별 하 고 텍스트 줄에서 토큰을 반환 합니다. 예제 코드는 단순히 적합 한 종류의 문자가 발견 될 때마다 트리거를 설정 합니다.  
  
```csharp  
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
  
## <a name="supporting-the-parameter-info-tooltip-in-the-parser"></a>매개 변수 정보 도구 설명 파서에 지원  
 <xref:Microsoft.VisualStudio.Package.Source> 클래스의 내용에 대 한 몇 가지 가정을 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 및 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 매개 변수 정보 도구 설명에 표시 되 고 업데이트 하는 경우 클래스입니다.  
  
-   파서가 제공할지 <xref:Microsoft.VisualStudio.Package.ParseReason> 매개 변수 목록 시작 문자를 입력 합니다.  
  
-   지정 된 위치는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체는 매개 변수 목록에는 문자 시작 후에 즉시 합니다. 파서가 수집 하 여 위치를 지정 하 고 사용 중인 버전에서 목록에 저장 하는 모든 메서드 선언에서 사용할 수 있는의 시그니처는 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 개체입니다. 이 목록에 메서드 이름, 포함 됩니다. 메서드 형식 (또는 반환 형식) 및 가능한 매개 변수 목록입니다. 이 목록은 메서드 서명 또는 서명 매개 변수 정보 도구 설명에 표시할 나중에 검색 됩니다.  
  
 파서가 다음 지정한 줄을 구문 분석 해야 합니다는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 사용자 얼마나 진행 뿐 아니라 입력 되는 메서드의 이름을 수집 하는 개체는 매개 변수를 입력 합니다. 메서드의 이름을 전달 하 여 이렇게는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartName%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 개체 하 고 호출할는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartParameters%2A> 메서드 매개 변수 목록 시작 문자 구문 분석 되 면 호출는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.NextParameter%2A> 메서드 때 매개 변수 목록 다음 문자를 구문 분석 하 고 마지막으로 호출 되는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.EndParameters%2A> 매개 변수 목록 끝 문자 구문 분석 하는 메서드. 이러한 메서드 호출의 결과에서 사용 되는 <xref:Microsoft.VisualStudio.Package.Source> 클래스를 매개 변수 정보 도구 설명을 적절 하 게 업데이트 합니다.  
  
### <a name="example"></a>예제  
 사용자가 입력 텍스트의 줄은 다음과 같습니다. 선 아래 숫자 (구문 분석 이동 합니다. 왼쪽에서 오른쪽으로 가정) 줄의 해당 위치에서 파서에서 어떤 단계를 수행 하는 것을 나타냅니다. 여기에 가정 하는 줄 앞에 나오는 모든 이미 구문 분석 되었습니다 "testfunc" 메서드 시그니처를 포함 하 여 메서드 서명에입니다.  
  
```  
testfunc("a string",3);  
     ^^          ^ ^  
     12          3 4  
```  
  
 구문 분석기를 사용 하는 단계는 다음과 같습니다.  
  
1.  파서 호출 <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartName%2A> "testfunc" 텍스트를 포함 합니다.  
  
2.  파서 호출 <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartParameters%2A>합니다.  
  
3.  파서 호출 <xref:Microsoft.VisualStudio.Package.AuthoringSink.NextParameter%2A>합니다.  
  
4.  파서 호출 <xref:Microsoft.VisualStudio.Package.AuthoringSink.EndParameters%2A>합니다.