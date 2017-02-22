---
title: "레거시 언어 서비스 구현 | Microsoft Docs"
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
  - "구현 언어 서비스 [관리 되는 패키지 프레임 워크]"
ms.assetid: 5bcafdc5-f922-48f6-a12e-6c8507a79a05
caps.latest.revision: 26
caps.handback.revision: 26
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 언어 서비스 구현
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

패키지 관리 프레임 워크 \(MPF\)를 사용 하 여 언어 서비스를 구현 하는 클래스에서 파생 되어야는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스 및 다음 추상 메서드 및 속성을 구현 합니다.  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A> 메서드  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> 메서드  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.Name%2A> 속성  
  
 아래 해당 섹션에 대 한 자세한 내용은 이러한 메서드 및 속성을 구현 하는 참조 하십시오.  
  
 추가 기능을 지원 하려면 언어 서비스를 MPF 언어 서비스 클래스 중 하나에서 클래스를 파생 해야 합니다. 예를 들어, 추가 메뉴 명령을 지원 하 여 한 클래스에서 파생 되어야는 <xref:Microsoft.VisualStudio.Package.ViewFilter> 클래스 및 명령 처리 메서드 중 일부를 재정의 \(참조 하십시오 <xref:Microsoft.VisualStudio.Package.ViewFilter> 세부 정보에 대 한\).  <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스는 많은 다양 한 클래스의 새 인스턴스를 생성 하기 위해 호출 되는 메서드를 제공 하 고 클래스의 인스턴스를 제공 하는 적절 한 만들기 메서드를 재정의 합니다.  재정의할 필요가 <xref:Microsoft.VisualStudio.Package.LanguageService.CreateViewFilter%2A> 메서드에서 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스 인스턴스를 직접 반환 합니다 <xref:Microsoft.VisualStudio.Package.ViewFilter> 클래스.  자세한 내용은 "사용자 지정 클래스 인스턴스화" 섹션을 참조 하십시오.  
  
 언어 서비스는 여러 위치에서 사용 되는 고유한 아이콘을 제공할 수도 있습니다.  예를 들어, IntelliSense 완성 목록에 표시 되는 경우 목록의 각 항목에는 메서드, 클래스, 네임 스페이스, 속성, 항목 표시 관련 아이콘이 있을 수 있습니다 또는 모든 언어에 대 한 필요는 있습니다.  이러한 아이콘을 사용 하는 모든 IntelliSense 목록에는  **탐색 모음**, 및는  **오류 목록** 작업 창.  자세한 내용은 아래 "언어 서비스 이미지" 절을 참조 하십시오.  
  
## GetLanguagePreferences 메서드  
 <xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A> 메서드는 항상 같은 인스턴스를 반환 된 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 클래스입니다.  해당 자료를 사용할 수 있습니다 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 모든 언어 서비스를 위한 추가 기본 설정에 필요 하지 않은 경우 클래스입니다.  MPF 언어 서비스 클래스의 최소한의 가정 자료 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 클래스입니다.  
  
### 예제  
 일반 구현을 보여 주는이 예제는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A> 메서드.  이 예제에서는 기본 사용 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 클래스입니다.  
  
```c#  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        private LanguagePreferences m_preferences;  
  
        public override LanguagePreferences GetLanguagePreferences()  
        {  
            if (m_preferences == null)  
            {  
                m_preferences = new LanguagePreferences(this.Site,  
                                                        typeof(TestLanguageService).GUID,  
                                                        this.Name );  
                m_preferences.Init();  
            }  
            return m_preferences;  
        }  
    }  
}  
```  
  
## GetScanner 메서드  
 이 인스턴스를 반환 된 <xref:Microsoft.VisualStudio.Package.IScanner> 줄 지향 파서 또는 토큰 형식 및 트리거를 얻기 위해 사용 되는 스캐너를 구현 하는 개체입니다.  이 스캐너에 사용 되는 <xref:Microsoft.VisualStudio.Package.Colorizer> 토큰 형식 및 트리거는 prelude 복잡 한 구문 분석 작업에로 가져오기 위해 스캐너를 사용할 수 있지만 클래스에 대 한 색을 지정 합니다.  구현 하는 클래스를 제공 해야 해당 <xref:Microsoft.VisualStudio.Package.IScanner> 구현 인터페이스와 해야 하는 모든 방법에는 <xref:Microsoft.VisualStudio.Package.IScanner> 인터페이스입니다.  
  
### 예제  
 일반 구현을 보여 주는이 예제는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> 메서드.  `TestScanner` 구현 클래스는 <xref:Microsoft.VisualStudio.Package.IScanner> 인터페이스 \(표시 되지 않음\).  
  
```c#  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        private TestScanner m_scanner;  
  
        public override IScanner GetScanner(IVsTextLines buffer)  
        {  
            if (m_scanner == null)  
            {  
                m_scanner = new TestScanner(buffer);  
            }  
            return m_scanner;  
        }  
    }  
}  
    internal class TestScanner : IScanner  
    {  
        private IVsTextBuffer m_buffer;  
        string m_source;  
  
        public TestScanner(IVsTextBuffer buffer)  
        {  
            m_buffer = buffer;  
        }  
  
        bool IScanner.ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo, ref int state)  
        {  
            tokenInfo.Type = TokenType.Unknown;  
            tokenInfo.Color = TokenColor.Text;  
            return true;  
        }  
  
        void IScanner.SetSource(string source, int offset)  
        {  
            m_source = source.Substring(offset);  
        }  
    }  
  
```  
  
## ParseSource 메서드  
 몇 가지 이유로에 따라 원본 파일을 구문 분석 합니다.  이 메서드에 제공 되는 <xref:Microsoft.VisualStudio.Package.ParseRequest> 설명 특정 구문 분석 작업에서 예상 하는 개체입니다.  <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드 토큰 기능 및 범위를 결정 하는 보다 복잡 한 파서를 호출 합니다.  <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> IntelliSense 작업 뿐 아니라에 중괄호 일치 메서드 지원에 사용 됩니다.  와 같은 고급 작업을 지원 하지 않는 경우에에서는 여전히 잘못 된 반환 해야 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 개체 및 해당 필요한 구현 하는 클래스를 만들 수는 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 인터페이스와 해당 인터페이스의 모든 메서드를 구현 합니다.  모든 방법에서 null 값을 반환할 수 있지만 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 개체 자체는 null 값 이면 안됩니다.  
  
### 예제  
 최소 구현을 보여 주는이 예제는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드 및 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 클래스를 컴파일 및 함수를 실제로 고급 기능을 지원 하지 않고 언어 서비스 허용 하기에 충분.  
  
```c#  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        public override AuthoringScope ParseSource(ParseRequest req)  
        {  
            return new TestAuthoringScope();  
        }  
    }  
  
    internal class TestAuthoringScope : AuthoringScope  
    {  
        public override string GetDataTipText(int line, int col, out TextSpan span)  
        {  
            span = new TextSpan();  
            return null;  
        }  
  
        public override Declarations GetDeclarations(IVsTextView view,  
                                                     int line,  
                                                     int col,  
                                                     TokenInfo info,  
                                                     ParseReason reason)  
        {  
            return null;  
        }  
  
        public override string Goto(VSConstants.VSStd97CmdID cmd, IVsTextView textView, int line, int col, out TextSpan span)  
        {  
            span = new TextSpan();  
            return null;  
        }  
  
        public override Methods GetMethods(int line, int col, string name)  
        {  
            return null;  
        }  
}  
```  
  
## Name 속성  
 이 언어 서비스의 이름을 반환합니다.  이 같은 언어 서비스를 등록 하면 지정 된 이름 이어야 합니다.  이 이름이 가장 두드러진입니다 많은 장소에서 사용 되는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 이름입니다 사용 위치는 레지스트리에 액세스 하는 클래스.  이 속성에서 반환 되는 이름에서 레지스트리 레지스트리 항목 및 키 이름에 사용 될 때 번역 되어야 합니다.  
  
### 예제  
 한 가지 가능한 구현을 보여 주는이 예제는 <xref:Microsoft.VisualStudio.Package.LanguageService.Name%2A> 속성입니다.  여기에 이름을 하드 코딩 됩니다: 언어 서비스를 등록 하는 중에 사용할 수 있도록 리소스 파일에서 실제 이름을 얻을 수 합니다 \(참조 하십시오 [언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)\).  
  
```c#  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        public override string Name  
        {  
            get { return "Test Language"; }  
        }  
    }  
}  
```  
  
## 사용자 지정 클래스 인스턴스화  
 고유한 버전의 각 클래스의 인스턴스를 제공 하는 지정 된 클래스에 다음 메서드를 재정의할 수 있습니다.  
  
### LanguageService 클래스  
  
|메서드|반환 되는 클래스|설명|  
|---------|---------------|--------|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateCodeWindowManager%2A>|<xref:Microsoft.VisualStudio.Package.CodeWindowManager>|텍스트 보기에 대 한 추가 사용자 지정을 지원.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateDocumentProperties%2A>|<xref:Microsoft.VisualStudio.Package.DocumentProperties>|사용자 지정 문서 속성을 지원.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A>|<xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars>|지원할 수 있는  **탐색 모음**.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateExpansionFunction%2A>|<xref:Microsoft.VisualStudio.Package.ExpansionFunction>|코드 조각 템플릿 함수를 지원.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateExpansionProvider%2A>|<xref:Microsoft.VisualStudio.Package.ExpansionProvider>|코드 조각 \(이 방법을 일반적으로 재정의 되지 않는\)을 지원.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateParseRequest%2A>|<xref:Microsoft.VisualStudio.Package.ParseRequest>|사용자 지정을 지 원하는 데는 <xref:Microsoft.VisualStudio.Package.ParseRequest> \(이 메서드는 일반적으로 재정의\) 구조.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateSource%2A>|<xref:Microsoft.VisualStudio.Package.Source>|주석 문자를 지정 하 고 메서드 서명에 사용자 지정 서식 소스 코드를 지원.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateViewFilter%2A>|<xref:Microsoft.VisualStudio.Package.ViewFilter>|추가 메뉴 명령을 지원.|  
|<xref:Microsoft.VisualStudio.Package.Source.GetColorizer%2A>|<xref:Microsoft.VisualStudio.Package.Colorizer>|\(이 방법을 일반적으로 재정의 되지 않는\) 구문 강조를 지원.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A>|<xref:Microsoft.VisualStudio.Package.LanguagePreferences>|언어 기본 설정에 대 한 액세스를 지원.  이 메서드를 구현 해야 하지만 기본 클래스의 인스턴스를 반환할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A>|<xref:Microsoft.VisualStudio.Package.IScanner>|토큰 줄의 종류를 식별 하는 데 사용 되는 파서를 제공.  이 메서드를 구현 하 고 <xref:Microsoft.VisualStudio.Package.IScanner> 에서 파생 되어야 합니다.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A>|<xref:Microsoft.VisualStudio.Package.AuthoringScope>|기능 및 범위에 걸쳐 전체 원본 파일을 식별 하는 데 사용 되는 파서를 제공.  이 메서드를 구현 해야 합니다 및 사용자 버전의 인스턴스를 반환 해야는 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 클래스입니다.  입니다 구문 강조를 모두 지 원하는 경우 \(요구는 <xref:Microsoft.VisualStudio.Package.IScanner> 파서가 반환 된는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> 메서드\), 아무 것도이 메서드에서 반환이 아닌 다른 버전의 수행할 수 있습니다는 <xref:Microsoft.VisualStudio.Package.AuthoringScope> 클래스 메서드가 속한 모든 null 값을 반환 합니다.|  
  
### 원본 클래스에서  
  
|메서드|반환 되는 클래스|설명|  
|---------|---------------|--------|  
|<xref:Microsoft.VisualStudio.Package.Source.CreateCompletionSet%2A>|<xref:Microsoft.VisualStudio.Package.CompletionSet>|\(이 방법을 일반적으로 재정의 되지 않는\) IntelliSense 완성 목록 표시를 사용자 지정 합니다.|  
|<xref:Microsoft.VisualStudio.Package.Source.CreateErrorTaskItem%2A>|<xref:Microsoft.VisualStudio.Package.DocumentTask>|오류 목록 작업 목록에서 마커를 지 원하는 데. 특히 지원 기능 이외의 파일을 열고 오류가 발생 한 줄으로 이동 합니다.|  
|<xref:Microsoft.VisualStudio.Package.Source.CreateMethodData%2A>|<xref:Microsoft.VisualStudio.Package.MethodData>|IntelliSense 매개 변수 정보 도구 설명의 표시를 사용자 지정 합니다.|  
|<xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A>|<xref:Microsoft.VisualStudio.Package.CommentInfo>|지원에 대 한 주석 코드입니다.|  
|<xref:Microsoft.VisualStudio.Package.Source.CreateAuthoringSink%2A>|<xref:Microsoft.VisualStudio.Package.AuthoringSink>|구문 분석 작업 시 정보를 수집 하는 데 있습니다.|  
  
### AuthoringScope 클래스  
  
|메서드|반환 되는 클래스|설명|  
|---------|---------------|--------|  
|<xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDeclarations%2A>|<xref:Microsoft.VisualStudio.Package.Declarations>|선언 형식 또는 멤버와 같은 목록을 제공합니다.  이 메서드를 구현 해야 하지만 null 값을 반환할 수 있습니다.  이 메서드는 유효한 개체를 반환 하는 경우 개체 인스턴스를 사용 중인 이어야 합니다는 <xref:Microsoft.VisualStudio.Package.Declarations> 클래스입니다.|  
|<xref:Microsoft.VisualStudio.Package.AuthoringScope.GetMethods%2A>|<xref:Microsoft.VisualStudio.Package.Methods>|메서드 시그니처 목록에 지정 된 컨텍스트를 제공합니다.  이 메서드를 구현 해야 하지만 null 값을 반환할 수 있습니다.  이 메서드는 유효한 개체를 반환 하는 경우 개체 인스턴스를 사용 중인 이어야 합니다는 <xref:Microsoft.VisualStudio.Package.Methods> 클래스입니다.|  
  
## 언어 서비스 이미지  
 언어 서비스 전체에서 사용 되는 아이콘 목록을 제공 하려면 재정의 <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> 메서드에서 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스 및 반환는 <xref:System.Windows.Forms.ImageList> 아이콘을 포함 하.  기본 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스 아이콘의 기본 집합을 로드 합니다.  아이콘을 해야 하는 해당 위치를 정확 하 게 이미지 인덱스를 지정 하므로 직접 이미지 목록을 정렬 하는 방법을 전적으로 사용자입니다.  
  
### IntelliSense 완성 목록에 사용 되는 이미지  
 IntelliSense 완성 목록에 각 항목에 대 한 이미지 인덱스를 지정 하지는 <xref:Microsoft.VisualStudio.Package.Declarations.GetGlyph%2A> 메서드는 <xref:Microsoft.VisualStudio.Package.Declarations> 이미지 인덱스를 지정 하는 경우에 재정의 해야 하는 클래스.  반환 되는 값의 <xref:Microsoft.VisualStudio.Package.Declarations.GetGlyph%2A> 메서드는 이미지 목록에 제공 된 인덱스는 <xref:Microsoft.VisualStudio.Package.CompletionSet> 클래스 생성자 및 즉 같은 이미지 목록에서 반환 된는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> 메서드를는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스 \(를 사용 하 여 이미지 목록을 변경할 수 있습니다는 <xref:Microsoft.VisualStudio.Package.CompletionSet> 재정의할 경우는 <xref:Microsoft.VisualStudio.Package.Source.CreateCompletionSet%2A> 메서드를는 <xref:Microsoft.VisualStudio.Package.Source> 다른 이미지 목록을 제공 하는 클래스\).  
  
### 탐색 모음에서 사용 되는 이미지  
 해당  **탐색 모음** 형식 및 멤버 목록을 표시 하 고 사용 빠른 탐색 아이콘을 표시할 수 있습니다에 대 한.  이러한 아이콘에서 가져온는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> 메서드에서 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스 후에 대해 특별히 재정의 될 수 없습니다의  **탐색 모음**.  나타내는 콤보 상자 목록을 입력 하면 콤보 상자의 각 항목에 대해 사용 되는 인덱스를 지정한는 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> 메서드에서 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> 클래스 \(참조 하십시오 [레거시 언어 서비스에 탐색 모음에 대 한 지원](../../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)\).  이러한 이미지 인덱스를 파서 버전을 통해 일반적으로 어떤 식으로든 가져옵니다의 <xref:Microsoft.VisualStudio.Package.Declarations> 클래스입니다.  인덱스의 입수 방법을 전적으로 사용자입니다.  
  
### 오류 목록 작업 창에서 사용 되는 이미지  
 때마다는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 메서드 파서 \(참조 하십시오 [레거시 언어 서비스 파서 및 검사](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)\)에서 오류가 발생 한 오류를 전달는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.AddError%2A> 메서드에서 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 입니다 클래스에는 오류 보고에  **오류 목록** 작업 창.  아이콘은 작업 창에 나타나는 각 항목에 연결 될 수 있습니다 및 해당 아이콘 같은 이미지 목록에서 반환 되는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> 메서드에서 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스입니다.  MPF 클래스의 기본 동작은 오류 메시지와 함께 이미지를 표시 하지 않도록입니다.  그러나 클래스에서 파생 하 여이 동작을 무시할 수 있습니다의 <xref:Microsoft.VisualStudio.Package.Source> 클래스 및 재정의 하는 <xref:Microsoft.VisualStudio.Package.Source.CreateErrorTaskItem%2A> 메서드.  새로 만들기 메서드는 <xref:Microsoft.VisualStudio.Package.DocumentTask> 개체입니다.  사용할 수 있는 개체를 반환 하기 전에 <xref:Microsoft.VisualStudio.Shell.Task.ImageIndex%2A> 속성에는 <xref:Microsoft.VisualStudio.Package.DocumentTask> 이미지 인덱스를 설정할 개체입니다.  이것은 다음과 같이 표시 됩니다.  참고 `TestIconImageIndex` 모든 아이콘에 설명 하 고이 예제에 관련 되는 열거형입니다.  언어 서비스에서 아이콘을 확인 하는 다른 방법으로 해야 합니다.  
  
```c#  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    class TestSource : Source  
    {  
        public override DocumentTask CreateErrorTaskItem(  
            TextSpan          span,  
            string            filename,  
            string            message,  
            TastPriority      priority,  
            TaskCategory      category,  
            MARKERTYPE        markerType,  
            TaskErrorCategory errorCategory)  
        {  
            DocumentTask taskItem = base.CreateErrorTaskItem(  
                                           span,  
                                           filename,  
                                           message,  
                                           priority,  
                                           category,  
                                           markerType,  
                                           errorCategory);  
            if (errorCategory == TaskErrorCategory.Error)  
            {  
                taskItem.ImageIndex = TestIconImageIndex.Error;  
            }  
            return taskItem;  
        }  
    }  
}  
```  
  
## 언어 서비스에 대 한 기본 이미지 목록  
 기본 MPF 언어 서비스 클래스에 제공 되는 기본 이미지 목록에 많은 일반적인 언어 요소와 연결 된 아이콘이 포함 되어 있습니다.  이러한 아이콘의 대부분의 6 가지 변화, 내부 공개, 보호, 개인, 친구, 및 바로 가기 액세스 개념에 해당 정렬 됩니다.  예를 들어, 보호 된 public 또는 private 인지 여부에 따라 메서드에 대 한 다른 아이콘을 가질 수 있습니다.  
  
 다음 열거형 각 아이콘 집합에 대 한 일반적인 이름을 지정 하 고 연결 된 인덱스를 지정 합니다.  예를 들어, 열거형을 기반으로, 이미지 인덱스는 보호 된 메서드에 대 한 지정한 수 있습니다 `(int)IconImageIndex.Method + (int)IconImageIndex.AccessProtected`.  이 열거형에 원하는 대로 이름을 변경할 수 있습니다.  
  
```c#  
public enum IconImageIndex  
        {  
            // access types  
            AccessPublic = 0,  
            AccessInternal = 1,  
            AccessFriend = 2,  
            AccessProtected = 3,  
            AccessPrivate = 4,  
            AccessShortcut = 5,  
  
            Base = 6,  
            // Each of the following icon type has 6 versions,  
            //corresponding to the access types  
            Class = Base + 0,  
            Constant = Base + 1,  
            Delegate = Base + 2,  
            Enumeration = Base + 3,  
            EnumMember = Base + 4,  
            Event = Base + 5,  
            Exception = Base + 6,  
            Field = Base + 7,  
            Interface = Base + 8,  
            Macro = Base + 9,  
            Map = Base + 10,  
            MapItem = Base + 11,  
            Method = Base + 12,  
            OverloadedMethod = Base + 13,  
            Module = Base + 14,  
            Namespace = Base + 15,  
            Operator = Base + 16,  
            Property = Base + 17,  
            Struct = Base + 18,  
            Template = Base + 19,  
            Typedef = Base + 20,  
            Type = Base + 21,  
            Union = Base + 22,  
            Variable = Base + 23,  
            ValueType = Base + 24,  
            Intrinsic = Base + 25,  
            JavaMethod = Base + 26,  
            JavaField = Base + 27,  
            JavaClass = Base + 28,  
            JavaNamespace = Base + 29,  
            JavaInterface = Base + 30,  
            // Miscellaneous icons with one icon for each type.  
            Error = 187,  
            GreyedClass = 188,  
            GreyedPrivateMethod = 189,  
            GreyedProtectedMethod = 190,  
            GreyedPublicMethod = 191,  
            BrowseResourceFile = 192,  
            Reference = 193,  
            Library = 194,  
            VBProject = 195,  
            VBWebProject = 196,  
            CSProject = 197,  
            CSWebProject = 198,  
            VB6Project = 199,  
            CPlusProject = 200,  
            Form = 201,  
            OpenFolder = 202,  
            ClosedFolder = 203,  
            Arrow = 204,  
            CSClass = 205,  
            Snippet = 206,  
            Keyword = 207,  
            Info = 208,  
            CallBrowserCall = 209,  
            CallBrowserCallRecursive = 210,  
            XMLEditor = 211,  
            VJProject = 212,  
            VJClass = 213,  
            ForwardedType = 214,  
            CallsTo = 215,  
            CallsFrom = 216,  
            Warning = 217,  
        }  
```  
  
## 참고 항목  
 [레거시 언어 서비스 구현](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [레거시 언어 서비스 개요](../../extensibility/internals/legacy-language-service-overview.md)   
 [언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)   
 [레거시 언어 서비스 파서 및 검사](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)