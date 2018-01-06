---
title: "레거시 언어 서비스에서 멤버 완성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliSense, Member Completion tool tip
- Member Completion, supporting in language services [managed package framework]
- language services [managed package framework], IntelliSense Member Completion
ms.assetid: 500f718d-9028-49a4-8615-ba95cf47fc52
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e77511bdaaa96dc75f5be75c175b63fcd3cc3253
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="member-completion-in-a-legacy-language-service"></a>레거시 언어 서비스에서 멤버 완성
IntelliSense 멤버 완성 클래스, 구조체, 열거형 또는 네임 스페이스와 같은 특정 범위의 가능한 멤버 목록을 표시 하는 도구 설명입니다. 예를 들어 C#에서 "this" 뒤에 마침표, 사용자가 현재 범위에서 구조체 또는 클래스의 모든 구성원의 목록이 표시 됩니다 선택할 수 있는 목록에서.  
  
 관리 패키지 프레임 워크 (MPF) 도구 설명 및 도구 설명; 목록을 관리에 대 한 지원 제공 목록에 표시 되는 데이터를 제공 하는 파서에서 협력은 필요한 모든입니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 된 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 최신 방법입니다. 자세한 내용을 알아보려면 참조 [편집기 및 언어 서비스 확장](../../extensibility/extending-the-editor-and-language-services.md)합니다.  
  
> [!NOTE]
>  편집기를 사용 하 여 새 API 가능한 한 빨리 시작 하는 것이 좋습니다. 언어 서비스의 성능이 향상 되 고 새 편집기 기능을 이용할 수 있도록 합니다.  
  
## <a name="how-it-works"></a>작동 방법  
 다음은 두 가지 방법으로는 구성원 목록이 MPF 클래스를 사용 하 여 표시 됩니다.  
  
-   식별자 또는 그 멤버 완료 문자 이후에 캐럿 위치를 지정 하 고 선택 하면 **멤버 목록** 에서 **IntelliSense** 메뉴.  
  
-   <xref:Microsoft.VisualStudio.Package.IScanner> 스캐너 멤버 완료 문자를 검색 하 고 설정 하는 토큰의 트리거 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 해당 문자에 대 한 합니다.  
  
 멤버 완료 문자를 수행 하는 클래스, 구조체 또는 열거형의 멤버 임을 나타냅니다. 예를 들어 C# 또는 Visual Basic 멤버 완성 문자는 한 `.`c + +의 문자는 반면, 한 `.` 또는 `->`합니다. 멤버 선택 문자를 검색 하는 경우 트리거 값 설정 됩니다.  
  
### <a name="the-intellisense-member-list-command"></a>IntelliSense 멤버 목록 표시 명령  
 <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> 명령에 대 한 호출을 시작는 <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 클래스 및 <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> 메서드를 호출 하는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 의 구문 분석 문제의 원인이 메서드 파서 <xref:Microsoft.VisualStudio.Package.ParseReason>합니다.  
  
 파서가으로 현재 위치에서 또는 현재 위치 바로 앞 토큰의 컨텍스트를 결정합니다. 이 토큰에 따라, 선언의 목록에 표시 됩니다. 예를 들어 C#에서 클래스 멤버 및 선택에 캐럿을 배치 하는 경우 **멤버 목록**, 클래스의 모든 멤버 목록을 가져옵니다. 개체 변수 뒤에 오는 기간 후 캐럿을 배치 하는 경우에 개체가 나타내는 클래스의 모든 멤버 목록을 가져옵니다. 멤버 목록 표시 될 때 멤버에 캐럿이 배치 되 면 캐럿이 목록에서 한 경우에 멤버 대체 목록에서 구성원을 선택 하면 note 합니다.  
  
### <a name="the-token-trigger"></a>토큰 트리거  
 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 에 호출을 시작 하는 트리거는 <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 클래스 및 <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> 의 구문 분석 문제의 원인이 파서를 차례로 호출 하는 메서드를 <xref:Microsoft.VisualStudio.Package.ParseReason> (토큰 트리거가 포함 하는 경우는 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 플래그를 구문 분석 하는 이유는 <xref:Microsoft.VisualStudio.Package.ParseReason> 멤버 선택 하 고 중괄호 강조 결합 하 여).  
  
 현재 컨텍스트를 결정 하는 파서가 멤버 문자를 선택 하기 전에 입력 된 내용을 뿐 아니라 위치를 지정 합니다. 이 정보를 파서가 요청 된 범위의 모든 구성원의 목록을 만듭니다. 이 선언의 목록에 저장 됩니다는 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 에서 반환 되는 개체는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드. 선언에 반환 되는 경우 멤버 완료 도구 설명이 표시 됩니다. 도구 설명의 인스턴스에 의해 관리 되는 <xref:Microsoft.VisualStudio.Package.CompletionSet> 클래스입니다.  
  
## <a name="enabling-support-for-member-completion"></a>멤버 완료에 대 한 지원을 사용 하도록 설정  
 있어야는 `CodeSense` 레지스트리 항목 모든 IntelliSense 작업을 지원 하기 위해 1로 설정 합니다. 이 레지스트리 항목에 전달 된 명명된 된 매개 변수를 설정할 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 언어 패키지와 연결 된 사용자 특성입니다. 언어 서비스 클래스에서이 레지스트리 항목의 값을 읽을 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A> 속성에는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 클래스입니다.  
  
 스캐너의 토큰 트리거를 반환 하는 경우 <xref:Microsoft.VisualStudio.Package.TokenTriggers>, 프로그램 파서 선언 목록을 반환 하 고 다음 멤버 완성 목록이 표시 됩니다.  
  
## <a name="supporting-member-completion-in-the-scanner"></a>스캐너에서 관련 멤버 완성  
 스캐너 멤버 완료 문자를 검색 하 고 토큰의 트리거를 설정 하는 작업을 할 수 있어야 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 문자가 구문 분석 합니다.  
  
### <a name="example"></a>예  
 다음은 간단한 예제 멤버 완성 문자를 검색 하 고 적절 한 설정 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 플래그입니다. 이 예제는 설명 목적 으로만. 스캐너는 메서드가 포함 되어 있음을 가정 `GetNextToken` 식별 하 고 텍스트 줄에서 토큰을 반환 합니다. 예제 코드는 단순히 적합 한 종류의 문자가 발견 될 때마다 트리거를 설정 합니다.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestScanner : IScanner  
    {  
        private Lexer lex;  
        private const char memberSelectChar = '.';  
  
        public bool ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo,  
                                                   ref int state)  
        {  
            bool foundToken = false  
            string token = lex.GetNextToken();  
            if (token != null)  
            {  
                foundToken = true;  
                char c = token[0];  
                if (c == memberSelectChar)  
                {  
                        tokenInfo.Trigger |= TokenTriggers.MemberSelect;  
                }  
            }  
            return foundToken;  
        }  
    }  
}  
```  
  
## <a name="supporting-member-completion-in-the-parser"></a>파서에 멤버 완료 지원  
 멤버 완료에 대 한는 <xref:Microsoft.VisualStudio.Package.Source> 호출 클래스는 <xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDeclarations%2A> 메서드. 목록에서 파생 된 클래스에서 구현 해야는 <xref:Microsoft.VisualStudio.Package.Declarations> 클래스입니다. 참조는 <xref:Microsoft.VisualStudio.Package.Declarations> 구현 해야 하는 방법에 대 한 세부 정보에 대 한 클래스입니다.  
  
 파서가으로 호출 <xref:Microsoft.VisualStudio.Package.ParseReason> 또는 <xref:Microsoft.VisualStudio.Package.ParseReason> 멤버 선택 문자를 입력 합니다. 지정 된 위치는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체는 멤버 선택 문자 직후 합니다. 파서가 소스 코드의 각 단계에서 멤버 목록에 표시 될 수 있는 모든 멤버의 이름을 수집 해야 합니다. 그런 다음 파서가 사용자가 연결 된 멤버 선택 문자 범위를 확인 하려면 현재 줄을 구문 분석 해야 합니다.  
  
 멤버 문자를 선택 하기 전에이 범위 식별자의 형식에 기반 합니다. 예를 들어 C#에서 멤버 변수를 지정 `languageService` 의 형식을 가진를 `LanguageService`입력 **languageService 합니다.** 모든 멤버 목록이 생성 된 `LanguageService` 클래스입니다. 또한 C#에서 입력 **이 있습니다.** 현재 범위에 있는 클래스의 모든 멤버 목록을 생성합니다.  
  
### <a name="example"></a>예  
 다음 예에서는를 채우는 한 가지 방법은 <xref:Microsoft.VisualStudio.Package.Declarations> 목록입니다. 이 코드에서는 파서에서 선언을 생성 하 고 호출 하 여 목록에 추가 가정는 `AddDeclaration` 에서 메서드는 `TestAuthoringScope` 클래스입니다.  
  
```csharp  
using System.Collections;  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    internal class TestDeclaration  
    {  
        public string Name;            // Name of declaration  
        public int     TypeImageIndex; // Glyph index  
        public string Description;     // Description of declaration  
  
        public TestDeclaration(string name, int typeImageIndex, string description)  
        {  
            this.Name = name;  
            this.TypeImageIndex = typeImageIndex;  
            this.Description = description;  
        }  
    }  
  
    //===================================================  
    internal class TestDeclarations : Declarations  
    {  
        private ArrayList declarations;  
  
        public TestDeclarations()  
            : base()  
        {  
            declarations = new ArrayList();  
        }  
  
        public void AddDeclaration(TestDeclaration declaration)  
        {  
            declarations.Add(declaration);  
        }  
  
        //////////////////////////////////////////////////////////////////////  
        // Declarations of class methods that must be implemented.  
        public override int GetCount()  
        {  
            // Return the number of declarations to show.  
            return declarations.Count;  
        }  
  
        public override string GetDescription(int index)  
        {  
            // Return the description of the specified item.  
            string description = "";  
            if (index >= 0 && index < declarations.Count)  
            {  
                description = ((TestDeclaration)declarations[index]).Description;  
            }  
            return description;  
        }  
  
        public override string GetDisplayText(int index)  
        {  
            // Determine what is displayed in the tool tip list.  
            string text = null;  
            if (index >= 0 && index < declarations.Count)  
            {  
                text = ((TestDeclaration)declarations[index]).Name;  
            }  
            return text;  
        }  
  
        public override int GetGlyph(int index)  
        {  
            // Return index of image to display next to the display text.  
            int imageIndex = -1;  
            if (index >= 0 && index < declarations.Count)  
            {  
                imageIndex = ((TestDeclaration)declarations[index]).TypeImageIndex;  
            }  
            return imageIndex;  
        }  
  
        public override string GetName(int index)  
        {  
            string name = null;  
            if (index >= 0 && index < declarations.Count)  
            {  
                name = ((TestDeclaration)declarations[index]).Name;  
            }  
            return name;  
        }  
    }  
  
    //===================================================  
    public class TestAuthoringScope : AuthoringScope  
    {  
        private TestDeclarations declarationsList;  
  
        public void AddDeclaration(TestDeclaration declaration)  
        {  
            if (declaration != null)  
            {  
                if (declarationsList == null)  
                {  
                    declarationsList = new TestDeclarations();  
                }  
                declarationsList.AddDeclaration(declaration);  
            }  
        }  
  
        public override Declarations GetDeclarations(IVsTextView view,  
                                                     int line,  
                                                     int col,  
                                                     TokenInfo info,  
                                                     ParseReason reason)  
        {  
            return declarationsList;  
        }  
  
        /////////////////////////////////////////////////  
        // Remainder of AuthoringScope methods not shown.  
        /////////////////////////////////////////////////  
    }  
  
    //===================================================  
    class TestLanguageService : LanguageService  
    {  
        public override AuthoringScope ParseSource(ParseRequest req)  
        {  
            TestAuthoringScope scope = new TestAuthoringScope();  
            if (req.Reason == ParseReason.MemberSelect ||  
                req.Reason == ParseReason.MemberSelectAndHighlightBraces)  
            {  
                // Gather list of declarations based on what the user  
                // has typed so far. In this example, this list is an array of  
                // MemberDeclaration objects (a helper class you might implement  
                // to hold member declarations).  
                // How this list is gathered is dependent on the parser  
                // and is not shown here.  
                MemberDeclarations memberDeclarations;  
                memberDeclarations = GetDeclarationsForScope();  
  
                // Now populate the Declarations list in the authoring scope.  
                // GetImageIndexBasedOnType() is a helper method you  
                // might implement to convert a member type to an index into  
                // the image list returned from the language service.  
                foreach (MemberDeclaration dec in memberDeclarations)  
                {  
                    scope.AddDeclaration(new TestDeclaration(  
                                             dec.Name,  
                                             GetImageIndexBasedOnType(dec.Type),  
                                             dec.Description));  
                }  
            }  
            return scope;  
        }  
    }  
}  
```