---
title: "레거시 언어 서비스에서 멤버 완성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IntelliSense, 멤버 완료 도구 설명"
  - "언어 서비스 [관리 되는 패키지 프레임 워크]에서 지원 되는 멤버 완료"
  - "IntelliSense 멤버 완성 언어 서비스 [관리 되는 패키지 프레임 워크]"
ms.assetid: 500f718d-9028-49a4-8615-ba95cf47fc52
caps.latest.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 21
---
# 레거시 언어 서비스에서 멤버 완성
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

IntelliSense 멤버 완성 클래스, 구조체, 열거형 또는 네임 스페이스와 같은 특정 범위의 가능한 멤버 목록을 표시 하는 도구 설명입니다. 예를 들어 C\#에서는 입력 된 경우 "this" 뒤에 마침표, 클래스 또는 구조의 현재 범위에서의 모든 멤버 목록은 목록에 표시 됩니다는 선택할 수 있는 합니다.  
  
 관리 되는 패키지 프레임 워크 \(MPF\) 도구 팁 및 도구 설명;의 목록을 관리에 대 한 지원을 제공합니다 이 목록에 표시 되는 데이터를 제공 하는 구문 분석기에서 협력입니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 자세한 내용을 참조 하십시오 [편집기 및 언어 서비스 확장](../../extensibility/extending-the-editor-and-language-services.md)합니다.  
  
> [!NOTE]
>  새 편집기 API를 최대한 빨리 사용을 시작 하는 것이 좋습니다. 이 언어 서비스의 성능을 향상 하 고 새로운 편집기 기능을 이용할 수 있도록 합니다.  
  
## 작동 방법  
 다음은 두 가지 방법으로는 멤버 목록이 MPF 클래스를 사용 하 여 표시 됩니다.  
  
-   식별자 또는 그 멤버 완료 문자 이후에 캐럿 위치 지정 및 선택 **멤버 목록** 에서 **IntelliSense** 메뉴.  
  
-   <xref:Microsoft.VisualStudio.Package.IScanner> 스캐너 멤버 완료 문자를 검색 하 고 설정의 토큰 트리거 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 해당 문자에 대 한 합니다.  
  
 멤버 완료 문자를 수행 하는 클래스, 구조체 또는 열거형의 멤버 임을 나타냅니다. 예를 들어 C\# 또는 Visual Basic 멤버 완성 문자는 한 `.`, c \+ \+에서 문자는 반면, 한 `.` 또는 `->`합니다. 트리거 값은 멤버 선택 문자를 검사할 때 설정 됩니다.  
  
### IntelliSense 멤버 목록 표시 명령  
 <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> 명령에 대 한 호출을 시작는 <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 클래스 및 <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> 메서드를 호출 하는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 의 구문 분석 이유인 메서드 파서 <xref:Microsoft.VisualStudio.Package.ParseReason>.  
  
 파서는 컨텍스트 아래에서 또는 현재 위치 바로 앞 토큰 뿐만 아니라 현재 위치를 결정합니다. 이 토큰에 따라, 선언의 목록에 표시 됩니다. 예를 들어 C\#에서 클래스 멤버 및 선택에 캐럿을 배치 하는 경우 **멤버 목록**, 클래스의 모든 멤버 목록을 얻게 됩니다. 개체 변수 다음에 나오는 지나면 캐럿을 배치할 경우 개체가 나타내는 클래스의 모든 멤버 목록을 가져옵니다. Note 캐럿이 위치에 멤버인 멤버 목록이 표시 될 때, 캐럿이 목록에서 하나를 사용 하는 멤버 대체 목록에서 구성원을 선택 합니다.  
  
### 토큰 트리거  
 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 트리거 호출을 시작는 <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> 메서드를는 <xref:Microsoft.VisualStudio.Package.Source> 클래스 및 <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> 메서드를 호출 하의 구문 분석 이유인 파서 <xref:Microsoft.VisualStudio.Package.ParseReason> \(토큰 트리거가 포함 하는 경우는 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 플래그를 구문 분석 하는 이유는 <xref:Microsoft.VisualStudio.Package.ParseReason> 멤버 선택 하 고 중괄호 강조 결합 하 여\).  
  
 현재 컨텍스트를 결정 하는 파서는 멤버 문자를 선택 하기 전에 입력 된 내용을 뿐만 아니라 배치 합니다. 이 정보를 파서는 요청 된 범위의 모든 멤버 목록을 만듭니다. 선언의이 목록에 저장 되는 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 에서 반환 되는 개체는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드. 선언에 반환 되는 경우 멤버 완료 도구 설명이 표시 됩니다. 도구 설명의 인스턴스에 의해 관리 되는 <xref:Microsoft.VisualStudio.Package.CompletionSet> 클래스입니다.  
  
## 멤버 완성을 지원 하도록 설정  
 있어야는 `CodeSense` 레지스트리 항목 IntelliSense 작업을 지원 하기 위해 1로 설정 합니다. 에 전달 되는 명명 된 매개 변수와 함께이 레지스트리 항목을 설정할 수는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 언어 패키지와 관련 된 사용자 특성입니다. 언어 서비스 클래스에서이 레지스트리 항목 값을 읽기는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A> 속성에는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 클래스입니다.  
  
 스캐너의 토큰 트리거를 반환 하는 경우 <xref:Microsoft.VisualStudio.Package.TokenTriggers>, 프로그램 파서 선언 목록을 반환 하 고 다음 멤버 완성 목록이 표시 됩니다.  
  
## 스캐너에서 지 원하는 멤버 완성  
 스캐너 멤버 완료 문자를 검색 하 고 토큰의 트리거를 설정 하는 일을 할 수 있어야 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 문자가 구문 분석 합니다.  
  
### 예제  
 다음은 간단한 예 멤버 완성 문자를 검색 하 고 적절 한 설정 <xref:Microsoft.VisualStudio.Package.TokenTriggers> 플래그입니다. 이 예는 설명 목적 으로만 제공 됩니다. 스캐너는 메서드가 포함 되어 있음을 가정 `GetNextToken` 식별 하 고 텍스트 줄에서 토큰을 반환 합니다. 예제 코드는 단순히 적합 한 종류의 문자가 발견 될 때마다 트리거를 설정 합니다.  
  
```c#  
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
  
## 파서에서 지원 멤버 완료  
 멤버 완료는 <xref:Microsoft.VisualStudio.Package.Source> 호출 클래스는 <xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDeclarations%2A> 메서드. 목록에서 파생 된 클래스에서 구현 해야는 <xref:Microsoft.VisualStudio.Package.Declarations> 클래스입니다. 참조는 <xref:Microsoft.VisualStudio.Package.Declarations> 클래스를 구현 해야 하는 방법에 대 한 세부 정보입니다.  
  
 파서를 호출 <xref:Microsoft.VisualStudio.Package.ParseReason> 또는 <xref:Microsoft.VisualStudio.Package.ParseReason> 멤버 선택 문자를 입력 하는 경우. 지정 된 위치는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 개체는 멤버 선택 문자 직후입니다. 파서는 소스 코드의 각 단계에서 멤버 목록에 나타날 수 있는 모든 멤버의 이름을 수집 해야 합니다. 그런 다음 파서가 사용자가 멤버 선택 문자와 관련 된 범위를 확인 하려면 현재 줄을 구문 분석 해야 합니다.  
  
 멤버 문자를 선택 하기 전에이 범위 식별자의 형식에 기반 합니다. 예를 들어 C\#에서 멤버 변수를 지정 `languageService` 의 형식을 가진를 `LanguageService`, 입력 **languageService.** 의 모든 멤버 목록을 생성는 `LanguageService` 클래스입니다. 또한 C\#에서 입력 **이.** 현재 범위에 있는 클래스의 모든 멤버 목록을 생성 합니다.  
  
### 예제  
 다음 예제에서는를 채우는 한 가지 방법은 <xref:Microsoft.VisualStudio.Package.Declarations> 목록입니다. 이 코드에서는 파서는 선언을 생성 하 고 호출 하 여 목록에 추가 `AddDeclaration` 메서드는 `TestAuthoringScope` 클래스입니다.  
  
```c#  
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