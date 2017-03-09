---
title: "연습: 웹 컨트롤 프로젝트 템플릿 게시 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "템플릿, 웹 컨트롤"
  - "웹 컨트롤 템플릿"
ms.assetid: b56490f8-38bd-4220-a17e-5ebb30d3ac78
caps.latest.revision: 22
caps.handback.revision: 22
manager: "douge"
---
# 연습: 웹 컨트롤 프로젝트 템플릿 게시
웹 컨트롤 프로젝트 템플릿을 만들어 다른 웹 컨트롤 프로젝트의 기준으로 사용할 수 있습니다. 또한 템플릿을 VSIX 확장으로 배포할 수 있습니다.  
  
 VSIX 확장을 배포하려면 개발자가 확장 관리자를 사용하여 새 확장과 업데이트된 확장을 검색할 수 있는 Visual Studio 갤러리 웹 사이트에 이를 추가하는 것이 좋습니다. 다른 서버에 배치하거나 CD 또는 다른 미디어에 구워서 확장을 배포할 수도 있습니다.  
  
 관련된 두 연습 중 하나인 이 연습을 통해 웹 컨트롤 프로젝트 템플릿을 만든 다음 배포하는 방법을 배울 수 있습니다. 또 다른 연습인 [연습: Visual Studio 확장 게시](../extensibility/walkthrough-publishing-a-visual-studio-extension.md)을 통해서는 웹 컨트롤을 만들고 배포하는 방법을 배울 수 있습니다.  
  
 이 연습에는 다음과 같은 섹션이 있습니다.  
  
-   VSIX 확장에서 웹 컨트롤 프로젝트 템플릿 만들기  
  
-   Visual Studio 갤러리에 템플릿 게시  
  
-   Visual Studio 갤러리에서 템플릿 설치  
  
-   설치된 템플릿 테스트  
  
-   템플릿에 디버그 작업 마법사 추가  
  
## 사전 요구 사항  
 이 연습을 완료하려면 웹 컨트롤을 이해하고 프로젝트 만들기, 프로젝트 속성 설정 및 Visual Studio 실험적 인스턴스 사용에 대한 방법을 알아야 합니다. Visual Studio와 Visual Studio SDK가 컴퓨터에 설치되어 있어야 합니다. 이 연습을 시작하기 전에 [연습: Visual Studio 확장 게시](../extensibility/walkthrough-publishing-a-visual-studio-extension.md)을 완료해야 합니다.  
  
## VSIX 확장에서 웹 컨트롤 프로젝트 템플릿 만들기  
 웹 컨트롤 프로젝트 템플릿을 만들려면 먼저 웹 컨트롤 프로젝트를 만듭니다. 이 연습을 위해 [연습: Visual Studio 확장 게시](../extensibility/walkthrough-publishing-a-visual-studio-extension.md)에 만든 ColorTextControl 웹 컨트롤 프로젝트를 시작합니다.  
  
 Visual Studio 갤러리에 프로젝트 템플릿을 게시하기 전에 **VSIX로 템플릿 내보내기** 마법사를 사용하여 템플릿을 VSIX 확장으로 내보내고 **확장 관리자**에서 식별할 수 있도록 아이콘 및 수행 기능을 설명하는 이미지를 지정합니다.  
  
#### 배포용 웹 컨트롤 프로젝트를 준비하려면  
  
1.  Visual Studio에서 MyWebControls 프로젝트를 엽니다.  
  
2.  **확장 관리자**를 사용하여 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkId=194329) 웹 사이트에서 **템플릿 내보내기 마법사**를 다운로드합니다.  
  
     마법사를 설치한 후 프로젝트를 열면 **파일** 메뉴에 **VSIX로 템플릿 내보내기**가 표시됩니다.  
  
3.  **파일** 메뉴에서 **VSIX로 템플릿 내보내기**를 클릭합니다.  
  
     ![File 메뉴의 Export Project as VSIX](../misc/media/pcwc_exportasvsix.png "PCWC\_ExportAsVsix")  
  
4.  **템플릿 형식 선택** 페이지에서 **프로젝트 템플릿**을 선택한 다음 MyWebControls.csproj를 선택합니다.**다음**을 클릭합니다.  
  
     ![프로젝트 템플릿 선택](../misc/media/pcwc_choosetemplate.png "PCWC\_ChooseTemplate")  
  
5.  **템플릿 옵션 선택** 페이지에서 **템플릿 이름**을 `Extensibility Color Text Web Toolbox Control`로 설정하고 **템플릿 설명**을 `Color text web control project that produces a VSIX extension.`으로 설정합니다.  
  
6.  **아이콘 이미지** 상자 옆에 **찾아보기**를 클릭합니다.**파일 이름** 상자에 `*.*`를 입력합니다. Color.bmp를 찾아 **열기**를 클릭합니다.  
  
7.  **미리 보기 이미지** 상자 옆에 **찾아보기**를 클릭합니다.**파일 이름** 상자에 `*.*`를 입력합니다. ScreenShot.bmp를 찾아 **열기**를 클릭합니다.**다음**을 클릭합니다.  
  
     ![템플릿 옵션 선택](../misc/media/pcwc_selecttemplateoptions2.png "PCWC\_SelectTemplateOptions2")  
  
8.  **VSIX 옵션 선택** 페이지에서 **제품 이름**을 `Extensibility Color Text Web Control Template`으로 변경합니다.  
  
9. 필요한 경우 **회사 이름**, **버전**, **라이선스** 및 **Getting started guide URL**\(시작 가이드 URL\)을 변경할 수 있습니다.  
  
10. **템플릿을 자동으로 Visual Studio로 가져오기** 옵션 선택을 취소합니다.**마침**을 클릭합니다.  
  
     ![자동으로 템플릿 가져오기 선택 취소](../misc/media/pcwc_.png "PCWC\_")  
  
     Windows 탐색기의 ..\\My Documents\\Visual Studio *\<버전\>*\\My Exported Templates\\ 폴더에 Extensibility Color Text Web Control Template.vsix가 있습니다.  
  
## Visual Studio 갤러리에 템플릿 게시  
 이제 프로젝트 템플릿을 Visual Studio 갤러리에 게시할 준비가 되었습니다.  
  
#### Visual Studio 갤러리에 템플릿을 게시하려면  
  
1.  웹 브라우저에서 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkId=194329) 웹 사이트를 엽니다.  
  
2.  오른쪽 위에서 **로그인**을 클릭합니다.  
  
3.  Microsoft 계정을 사용하여 로그인합니다. Microsoft 계정이 없으면 여기서 만들 수 있습니다.  
  
4.  **업로드**를 클릭합니다.  
  
5.  **1단계: 확장 형식**에서는 **프로젝트 또는 항목 템플릿**을 선택하고 **다음**을 클릭합니다.  
  
6.  **2단계: 업로드**에서는 **찾아보기**를 클릭합니다. \\My Exported Templates\\ 폴더에서 Extensibility Color Text Web Control Template.vsix를 선택합니다.**다음**을 클릭합니다.  
  
7.  **3단계: 기본 정보**에서는 **VSIX로 템플릿 내보내기 마법사**의 정보가 표시됩니다.  
  
8.  **범주**를 `ASP.NET`로 설정하고 **태그**를 `toolbox, web control, templates`로 설정합니다.  
  
9. 작성 약관을 읽고 동의한 다음 상자에 표시되는 텍스트를 입력합니다.  
  
10. **Create Contribution**\(작성 만들기\)을 클릭한 다음 **게시**를 클릭합니다.  
  
11. Visual Studio 갤러리에서 Extensibility Color Text Web Control Template을 검색합니다. 템플릿 목록이 표시됩니다.  
  
     ![새 웹 컨트롤 템플릿 목록 항목](../misc/media/pcwc_templatelisting.png "PCWC\_TemplateListing")  
  
## Visual Studio 갤러리에서 템플릿 설치  
 게시된 웹 컨트롤 프로젝트 템플릿을 Visual Studio에 설치하여 테스트합니다.  
  
#### Visual Studio에서 웹 컨트롤 프로젝트 템플릿을 설치하려면  
  
1.  Visual Studio의 **도구** 메뉴에서 **확장 관리자**를 클릭합니다.  
  
2.  **온라인 갤러리**를 클릭하고 확장성 색 텍스트 웹 컨트롤 템플릿을 검색합니다. 템플릿 목록이 표시됩니다.  
  
3.  **다운로드**를 클릭합니다. 확장을 다운로드한 후 **설치**를 클릭합니다.  
  
## 설치된 템플릿 테스트  
 이제 확장성 색 텍스트 웹 컨트롤 프로젝트 템플릿을 사용하여 사용자 지정 웹 컨트롤을 만들 수 있습니다. 각각의 웹 컨트롤을 직접 만들 필요는 없습니다. 이 섹션에서는 템플릿을 사용하여 BlueColorTextControl 웹 컨트롤을 만드는 방법을 보여 줍니다.  
  
#### 템플릿을 기반으로 웹 컨트롤을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  왼쪽 창에서 **온라인 템플릿**을 클릭하고 **템플릿**을 확장한 다음 **ASP.NET**을 클릭합니다. 가운데 창에서 **확장성 색 텍스트 웹 컨트롤 템플릿**을 클릭합니다.  
  
     ![Select the extensibility color text web template](../Image/PCWC_NewProjectTemplate.png "PCWC\_NewProjectTemplate")  
  
3.  **이름**을 `MoreWebControls`로 설정합니다.**확인**을 클릭합니다.  
  
4.  **솔루션 탐색기**에서 이름을 ColorTextControl.cs에서 BlueColorTextControl.cs로 바꿉니다.  
  
5.  편집기에서 BlueColorTextControl.cs를 두 번 클릭하여 엽니다.  
  
6.  `ToolboxData` 특성에서 `ColorTextControl`의 두 항목을 `BlueColorTextControl`로 바꿉니다.  
  
     이러한 값은 디자인 타임에 **도구 상자**에서 웹 페이지로 끌어올 때 컨트롤에 대해 생성되는 여는 태그와 닫는 태그를 지정합니다.  또한 **도구 상자**에 표시되는 컨트롤의 이름인 컨트롤 클래스의 이름과 일치해야 합니다.  
  
     이제 컨트롤 클래스 소스 코드의 시작 부분이 다음 코드와 유사해야 합니다.  
  
    ```  
    namespace MoreWebControls { [DefaultProperty("Text")] [ToolboxData("<{0}:BlueColorTextControl runat=server> </{0}:BlueColorTextControl>")] [ProvideToolboxControl("MoreWebControls", false)] public class BlueColorTextControl : WebControl {  
  
    ```  
  
7.  `get` 메서드에서 `color:green`를 `color:blue`으로 변경합니다.  
  
    ```  
    get { String s = (String)ViewState["Text"]; return "<span style='color:blue'>" + s + "</span>"; }  
    ```  
  
     이렇게 하면 span 태그에 있는 텍스트가 파란색으로 지정되고 래핑됩니다.  
  
8.  MoreWebControls 프로젝트를 빌드합니다.  
  
## 새 웹 컨트롤 테스트  
 이제 **도구 상자**에서 새 웹 컨트롤을 사용할 수 있는지 테스트할 수 있습니다. 그러나 MoreWebControls 프로젝트가 열려있을 때 F5 키를 눌러도 컨트롤을 테스트하는 Visual Studio의 실험적 인스턴스가 시작되지 않습니다. 이는 프로젝트가 아직 디버그 작업을 설정할 수 없는 확장성 색 텍스트 웹 컨트롤 템플릿을 기반으로 하므로 발생합니다. \(다음 섹션에서는 디버그 작업을 설정하는 마법사를 템플릿에 추가하는 방법을 보여 줍니다.\) 이제 컨트롤을 테스트하려면 다음 단계를 수행합니다.  
  
#### 새 웹 컨트롤을 테스트하려면  
  
1.  Visual Studio의 실험적 인스턴스를 열려면 해당 실험적 인스턴스를 시작합니다.  
  
    1.  [!INCLUDE[win7](../debugger/includes/win7_md.md)]에서 **시작** 메뉴\(**시작\/모든 프로그램\/Microsoft Visual Studio \<버전\> SDK\/도구\/Microsoft Visual Studio \<버전\> 실험적 인스턴스 시작**\)를 사용합니다.  
  
    2.  [!INCLUDE[win81](../debugger/includes/win81_md.md)]의 **시작** 화면에서 **Microsoft Visual Studio \<버전\> 실험적 인스턴스 시작**을 입력합니다.  
  
2.  웹 응용 프로그램 프로젝트를 만듭니다.  
  
3.  프로젝트에서 default.aspx를 엽니다.**원본** 뷰가 표시되는지 확인합니다.  
  
4.  **도구 상자**의 **MoreWebControls** 범주에 **BlueColorTextControl**이 표시됩니다.  
  
     ![MoreWebControls BlueColorTextControl](../Image/PCWC_Toolbox2.png "PCWC\_Toolbox2")  
  
5.  웹 페이지의 `body` 태그의 임의 위치에 BlueColorTextControl을 끌어 놓습니다.  
  
6.  `ColorTextControl` 태그에 `Text` 특성을 추가하고 값을 `Think Blue!`로 설정합니다. 결과 태그는 다음 중 하나와 유사해야 합니다.  
  
    ```  
    <cc1:BlueColorTextControl ID="BlueColorTextControl1" Text="Think Blue!" runat="server" />  
  
    ```  
  
7.  F5 키를 눌러 ASP.NET 개발 서버를 시작합니다.  
  
     BlueColorTextControl이 다음 그림과 유사하게 표시됩니다.  
  
     ![BlueColorTextControl이 렌더링한 Think Blue](../misc/media/pcwc_thinkblue.png "PCWC\_ThinkBlue")  
  
8.  ASP.NET 개발 서버를 닫습니다.  
  
9. Visual Studio의 실험적 인스턴스를 닫습니다.  
  
## 템플릿에 디버그 작업 마법사 추가  
 이전 섹션에서 설명한 것처럼 MoreWebControls 프로젝트가 열려있을 때 F5 키를 누르면 Visual Studio의 실험적 인스턴스가 열리지 않습니다. 대신 “출력 형식이 클래스 라이브러리인 프로젝트는 직접 시작할 수 없습니다.”라는 메시지가 표시됩니다. 프로젝트에 대한 실험적 인스턴스의 위치를 알 수 없는 경우 발생합니다. 그러나 템플릿을 사용하도록 설정하여 대상 컴퓨터에서 실험적 인스턴스의 위치를 확인하고 적절한 디버그 작업을 설정할 수 있습니다. 그러면 해당 템플릿을 기반으로 하는 컴퓨터의 모든 프로젝트가 예상대로 F5 키에 응답합니다.  
  
 Visual Studio SDK에 포함되는 모든 확장성 프로젝트 템플릿에는 마법사가 포함되어 있으며, 이는 설치하는 동안 실행되어 대상 컴퓨터에서 실험적 인스턴스를 찾고 디버그 작업을 설정합니다. 마법사를 직접 만들어 이 작업을 수행할 수 있으며 배포하는 모든 템플릿에 포함할 수 있습니다.  
  
 디버그 작업 마법사를 확장성 색 텍스트 웹 컨트롤 템플릿에 추가하려면 템플릿의 첫 번째 버전을 삭제하고 마법사를 추가한 다음 다시 만들어야 합니다.  
  
#### 템플릿의 첫 번째 버전을 삭제하려면  
  
1.  Visual Studio 갤러리 웹 사이트의 왼쪽 위에서 **My Contributions**\(내 작성\)를 클릭합니다.**확장성 색 텍스트 웹 컨트롤 템플릿** 목록이 나타납니다.  
  
2.  프로젝트 템플릿을 Visual Studio 갤러리에서 영구적으로 제거하려면 **삭제**를 클릭합니다.  
  
3.  Visual Studio의 **도구** 메뉴에서 **확장 관리자**를 클릭합니다.  
  
4.  **확장성 색 텍스트 웹 컨트롤 템플릿**을 선택하고 **제거**를 클릭합니다.  
  
5.  **확장 관리자**를 닫습니다.  
  
6.  MoreWebControls 솔루션을 닫습니다.  
  
7.  Visual Studio를 닫습니다.  
  
8.  MoreWebControls 솔루션 폴더를 삭제합니다.  
  
9. 제거 프로세스를 완료하려면 Visual Studio를 다시 시작합니다.  
  
 디버그 작업 마법사는 `Microsoft.VisualStudio.TemplateWizard.IWizard`의 공용 구현이 있어야 하고 강력한 어셈블리 이름을 사용하여 서명되어야 합니다.  
  
#### 디버그 작업 마법사를 만들려면  
  
1.  **새 프로젝트** 대화 상자에 **Visual C\#**, **Windows**, **클래스 라이브러리** 프로젝트를 만들고 `MyWizard`로 이름을 지정합니다.  
  
2.  새 프로젝트에서 class1.cs의 이름을 MyWizard.cs로 바꿉니다.  
  
3.  MyWizard.cs의 내용을 다음 코드로 대체합니다.  
  
    ```  
    using System; using System.Collections.Generic; using System.Linq; using System.Text; using Microsoft.VisualStudio.TemplateWizard; using System.Globalization; using EnvDTE; namespace MyWizard { public class MyWizard : IWizard { public void BeforeOpeningFile(ProjectItem projectItem) { } public void ProjectFinishedGenerating(Project project) { foreach (Configuration config in project.ConfigurationManager) { //Set up the debug options to run "devenv /rootsuffix Exp"; config.Properties.Item("StartAction").Value = 1; //Get the full path to devenv.exe through DTE.FullName config.Properties.Item("StartProgram").Value = project.DTE.FullName; config.Properties.Item("StartArguments").Value = "/rootsuffix Exp"; } } public void ProjectItemFinishedGenerating(ProjectItem projectItem) { } public void RunFinished() { } public void RunStarted(object automationObject, Dictionary<string, string> replacementsDictionary, WizardRunKind runKind, object[] customParams) { } public bool ShouldAddProjectItem(string filePath) { return true; } } }  
  
    ```  
  
4.  프로젝트에 대한 다음 참조를 추가합니다. 하나 이상을 선택하는 경우 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]에 대한 경로가 있는 참조를 선택합니다.  
  
    -   EnvDTE  
  
    -   Microsoft.VisualStudio.TemplateWizardInterface  
  
5.  MyWizard 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.**서명** 탭에서 **어셈블리 서명** 옵션을 선택합니다.  
  
6.  **강력한 이름 키 파일 선택** 목록에서 **\<새로 만들기…\>**를 선택합니다.**강력한 이름 키 만들기** 대화 상자가 표시됩니다.  
  
7.  **키 파일 이름**을 `key.snk`로 설정하고 **암호로 키 파일 보호** 옵션 선택을 취소합니다.  
  
     ![키 파일 지정](../misc/media/pcwc_strongname.png "PCWC\_StrongName")  
  
8.  **확인**을 클릭하여 key.snk를 프로젝트에 추가합니다.  
  
9. MyWizard 프로젝트를 릴리스 빌드로 빌드합니다. 이제 마법사를 사용할 준비가 되었습니다.  
  
10. MyWizard 솔루션을 닫습니다.  
  
#### 마법사를 통합하고 템플릿을 다시 만들려면  
  
1.  이전 섹션\(VSIX 확장에서 웹 컨트롤 프로젝트 템플릿 만들기\)의 단계를 수행하면서 다음 추가 및 변경 사항을 적용합니다.  
  
    -   **VSIX로 템플릿 내보내기** 마법사를 다시 다운로드할 필요가 없습니다.  
  
    -   **VSIX로 템플릿 내보내기** 마법사에서, **VSIX 옵션 선택** 페이지의 **마법사** 상자에서 이전 단계에서 만든 \\bin\\Release\\MyWizard.dll 파일을 찾아 선택합니다.  
  
         ![마법사 어셈블리 지정](../misc/media/pcwc_wizardassembly.png "PCWC\_WizardAssembly")  
  
    -   기존 VSIX 확장 출력 파일을 덮어쓸 것인지 묻는 메시지가 나타나면 **예**를 클릭합니다.  
  
2.  새 웹 컨트롤 테스트 섹션이 나타나면 F5 키를 누릅니다. Visual Studio의 실험적 인스턴스가 시작되어야 합니다.  
  
## 다음 단계  
 이 연습에서는 **VSIX로 템플릿 내보내기** 마법사를 사용하여 프로젝트 템플릿을 만들고 배포하는 방법을 보여 줍니다. 예를 들어 **새 프로젝트** 대화 상자에 나타나는 아이콘을 선택하기 위해 더 많은 프로젝트 템플릿 컨트롤이 필요한 경우 프로젝트 템플릿을 명시적으로 만들어 VSIX 확장에서 래핑해야 합니다. 자세한 내용은 Visual Studio 블로그 웹 사이트에서 [프로젝트 및 항목 템플릿 만들기 및 공유](http://go.microsoft.com/fwlink/?LinkId=194551)를 참조하세요.  
  
## 참고 항목  
 [배송 Visual Studio 확장](../extensibility/shipping-visual-studio-extensions.md)