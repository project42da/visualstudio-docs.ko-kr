---
title: "연습: 항목 템플릿을 사용 하 여 사용자 지정 작업 프로젝트 항목 만들기, 2 부 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], creating template wizards
- SharePoint project items, creating template wizards
- SharePoint development in Visual Studio, defining new project item types
ms.assetid: 2d8165d3-4af9-4a5e-bdba-8b2a06b1dc8d
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b12a52101feebcfac08c7672834d9d7c65d41c55
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2"></a>연습: 항목 템플릿을 사용하여 사용자 지정 작업 프로젝트 항목 만들기, 2부
  사용자 지정 형식의 SharePoint 프로젝트 항목을 정의 하 고 Visual Studio에서 항목 템플릿을 사용 하 여 연결 하는 마법사를 제공 수도 있습니다. 서식 파일 프로젝트에 프로젝트 항목의 새 인스턴스를 추가 하는 데 사용할 사용자 로부터 정보를 수집 하는 마법사를 사용할 수 있습니다. 수집 하는 정보는 프로젝트 항목을 초기화 데 사용할 수 있습니다.  
  
 이 연습에서는 사용자 지정 작업 프로젝트 항목에 설명 된 마법사를 추가 합니다 [연습: 항목 템플릿, 1 부를 사용 하 여 사용자 지정 작업 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)합니다. 사용자가 사용자 지정 작업 프로젝트 항목을 SharePoint 프로젝트에 추가 마법사 (예: 위치 및 최종 사용자를 선택 하 고 때 탐색할 URL) 사용자 지정 동작에 대 한 정보를 수집 하는 새 Elements.xml 파일에이 정보를 추가 하 고 프로젝트 항목입니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   연결 된 항목 템플릿과 사용자 지정 SharePoint 프로젝트 항목 형식에 대 한 마법사 만들기  
  
-   사용자 지정 마법사 Visual Studio에서 SharePoint 프로젝트 항목에 대 한 기본 제공 마법사 유사한 UI를 정의 합니다.  
  
-   대체 가능 매개 변수를 사용 하 여 마법사에서 수집한 데이터가 포함 된 SharePoint 프로젝트 파일을 초기화 합니다.  
  
-   디버깅 하 고 마법사를 테스트 합니다.  
  
> [!NOTE]  
>  완료 된 프로젝트, 코드 및이 연습에서는 다음 위치에서 다른 파일을 포함 하는 샘플을 다운로드할 수 있습니다: [SharePoint 도구 확장성 연습에 대 한 프로젝트 파일](http://go.microsoft.com/fwlink/?LinkId=191369)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 수행 하려면 먼저 만들어야 합니다 CustomActionProjectItem 솔루션을 완료 하 여 [연습: 항목 템플릿, 1 부를 사용 하 여 사용자 지정 작업 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)합니다.  
  
 또한이 연습을 완료 하려면 개발 컴퓨터에 다음 구성 요소가 필요 합니다.  
  
-   지원 되는 Windows, SharePoint 및 Visual Studio의 버전입니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio SDK입니다. 이 연습에서는 **VSIX 프로젝트** 프로젝트 항목을 배포 하려면 VSIX 패키지를 만드는 SDK에서 서식 파일입니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구 확장](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
 다음 개념을 이해에 도움이 되지만 필수는 아니므로 연습을 완료 하는:  
  
-   Visual Studio에서 프로젝트 및 항목 템플릿에 대 한 마법사를 제공 합니다. 자세한 내용은 참조 [하는 방법: 프로젝트 템플릿이 함께 제공 마법사 사용](../extensibility/how-to-use-wizards-with-project-templates.md) 및 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스입니다.  
  
-   SharePoint에서 사용자 지정 동작입니다. 자세한 내용은 참조 [사용자 지정 작업](http://go.microsoft.com/fwlink/?LinkId=177800)합니다.  
  
## <a name="creating-the-wizard-project"></a>마법사 프로젝트 만들기  
 이 연습을 완료 하려면에서 만든 CustomActionProjectItem 솔루션에 프로젝트를 추가 해야 [연습: 항목 템플릿, 1 부를 사용 하 여 사용자 지정 작업 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)합니다. 구현 합니다는 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를이 프로젝트에서 마법사 UI를 정의 합니다.  
  
#### <a name="to-create-the-wizard-project"></a>마법사 프로젝트를 만들려면  
  
1.  Visual Studio에서 엽니다 CustomActionProjectItem 솔루션  
  
2.  **솔루션 탐색기**솔루션 노드에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 프로젝트**합니다.  
  
3.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic** 노드를 선택한 후는 **Windows** 노드.  
  
4.  맨 위에 있는 **새 프로젝트** 대화 상자에서 다음 사항을 확인 **.NET Framework 4.5** 버전의.NET Framework의 목록에서 선택 됩니다.  
  
5.  선택 된 **WPF 사용자 정의 컨트롤 라이브러리** 서식 파일 프로젝트에서 프로젝트 이름을 **ItemTemplateWizard**, 선택한 후는 **확인** 단추 합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]추가 **ItemTemplateWizard** 프로젝트를 솔루션입니다.  
  
6.  프로젝트에서 UserControl1 항목을 삭제 합니다.  
  
## <a name="configuring-the-wizard-project"></a>마법사 프로젝트 구성  
 마법사를 만들기 전에 Windows Presentation Foundation (WPF) 창, 코드 파일 및 어셈블리 참조를 프로젝트에 추가 해야 합니다.  
  
#### <a name="to-configure-the-wizard-project"></a>마법사 프로젝트를 구성 하려면  
  
1.  **솔루션 탐색기**에서 바로 가기 메뉴를 열고는 **ItemTemplateWizard** 프로젝트 노드를 선택한 후 **속성**합니다.  
  
2.  에 **프로젝트 디자이너**, 대상 프레임 워크가.NET Framework 4.5로 설정 되어 있는지 확인 합니다.  
  
     Visual C# 프로젝트의 경우에이 값을 설정할 수 있습니다는 **응용 프로그램** 탭 합니다. Visual Basic 프로젝트에서이 값을 설정할 수는 **컴파일** 탭 합니다. 자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)을 참조하세요.  
  
3.  에 **ItemTemplateWizard** 프로젝트에서 추가 **창 (WPF)** 항목의 프로젝트를 선택한 다음 항목의 이름을 **WizardWindow**합니다.  
  
4.  두 개의 코드 파일의 이름은 CustomActionWizard 및 문자열을 추가 합니다.  
  
5.  에 대 한 바로 가기 메뉴를 열고는 **ItemTemplateWizard** 프로젝트를 선택한 후 **참조 추가**합니다.  
  
6.  에 **참조 관리자-ItemTemplateWizard** 대화 상자는 **어셈블리** 노드를 선택는 **확장** 노드.  
  
7.  다음 어셈블리 옆의 확인란을 선택한 다음 선택에서 **확인** 단추:  
  
    -   EnvDTE  
  
    -   Microsoft.VisualStudio.Shell.11.0  
  
    -   Microsoft.VisualStudio.TemplateWizardInterface  
  
8.  **솔루션 탐색기**에 **참조** ItemTemplateWizard 프로젝트 폴더를 선택는 **EnvDTE** 참조 합니다.  
  
9. 에 **속성** 창의 값을 변경는 **Interop 형식 포함** 속성을 **False**합니다.  
  
## <a name="defining-the-default-location-and-id-strings-for-custom-actions"></a>사용자 지정 작업에 대 한 기본 위치 및 ID 문자열을 정의합니다.  
 위치 및 ID에 지정 된 모든 사용자 지정 작업에는 `GroupID` 및 `Location` 의 특성은 `CustomAction` Elements.xml 파일의 요소입니다. 이 단계에서는 ItemTemplateWizard 프로젝트에서 이러한 특성에 대 한 올바른 문자열의 일부를 정의합니다. 이 연습을 완료 하면 마법사에서 위치 및 ID를 지정 하는 사용자가 이러한 문자열 Elements.xml 파일에 사용자 지정 작업 프로젝트 항목에 기록 됩니다.  
  
 간단한 설명을 위해이 샘플에 사용 가능한 기본 위치 및 Id의 하위 집합만을 지원합니다. 전체 목록을 보려면 참조 [기본 사용자 지정 작업 위치 및 Id](http://go.microsoft.com/fwlink/?LinkId=181964)합니다.  
  
#### <a name="to-define-the-default-location-and-id-strings"></a>기본 위치 및 ID 문자열을 정의 하려면  
  
1.  엽니다.  
  
2.  에 **ItemTemplateWizard** 프로젝트, 문자열 코드 파일의 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#6](../sharepoint/codesnippet/CSharp/customactionprojectitem/itemtemplatewizard/strings.cs#6)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#6](../sharepoint/codesnippet/VisualBasic/customactionprojectitem/itemtemplatewizard/strings.vb#6)]  
  
## <a name="creating-the-wizard-ui"></a>마법사 UI 만들기  
 마법사의 UI를 정의 하는 XAML을 추가 하 고 ID 문자열을 마법사의 일부 컨트롤 바인딩하는 코드를 추가 합니다. 마법사를 만들면 Visual Studio에서 SharePoint 프로젝트에 대 한 기본 제공 마법사와 유사 합니다.  
  
#### <a name="to-create-the-wizard-ui"></a>마법사 UI를 만들려면  
  
1.  에 **ItemTemplateWizard** 프로젝트에 대 한 바로 가기 메뉴를 열고는 **WizardWindow.xaml** 파일을 선택한 다음 선택 **열** 디자이너에서 창을 엽니다.  
  
2.  XAML 뷰에서 현재 XAML을 다음 XAML로 바꿉니다. XAML은 사용자 지정 작업 및 탐색 단추 창의 맨 아래에 동작을 지정 하기 위한 컨트롤, 머리글을 포함 하는 UI를 정의 합니다.  
  
    > [!NOTE]  
    >  프로젝트에이 코드를 추가 하면 컴파일 오류가 발생 해야 합니다. 이러한 오류는 사라집니다 이후 단계에서 코드를 추가 합니다.  
  
     [!code-xml[SPExtensibility.ProjectItem.CustomAction#9](../sharepoint/codesnippet/Xaml/customactionprojectitem/itemtemplatewizard/wizardwindow.xaml#9)]  
  
    > [!NOTE]  
    >  이 XAML에서 생성 된 창에서 파생 되는 <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow> 기본 클래스입니다. Visual Studio에 사용자 지정 WPF 대화 상자를 추가 하면 Visual Studio에서 다른 대화 상자와 일관 된 스타일 고 모달 대화 상자를 사용 하 여 발생할 수 있는 문제를 방지 하려면이 클래스에서 대화 상자를 파생 하는 것이 좋습니다. 자세한 내용은 참조 [만들기 및 모달 대화 상자 관리](/visualstudio/extensibility/creating-and-managing-modal-dialog-boxes)합니다.  
  
3.  Visual Basic 프로젝트를 개발 하는 경우 제거는 `ItemTemplateWizard` 에서 네임 스페이스는 `WizardWindow` 클래스 이름에는 `x:Class` 특성은 `Window` 요소입니다. XAML의 첫 번째 줄에 있는이 요소가입니다. 완료 되 면 첫 번째 줄에 다음 코드는 유사 합니다.  
  
    ```  
    <Window x:Class="WizardWindow"  
    ```  
  
4.  WizardWindow.xaml 파일에 대 한 코드 숨김 파일에 현재 코드를 다음 코드로 바꿉니다.  
  
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#7](../sharepoint/codesnippet/VisualBasic/customactionprojectitem/itemtemplatewizard/wizardwindow.xaml.vb#7)]
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#7](../sharepoint/codesnippet/CSharp/customactionprojectitem/itemtemplatewizard/wizardwindow.xaml.cs#7)]  
  
## <a name="implementing-the-wizard"></a>마법사를 구현합니다.  
 마법사의 기능을 구현 하 여 정의 된 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스입니다.  
  
#### <a name="to-implement-the-wizard"></a>마법사를 구현 하려면  
  
1.  에 **ItemTemplateWizard** 프로젝트, 열기는 **CustomActionWizard** 코드 파일을 마우스 다음이 파일에 현재 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#8](../sharepoint/codesnippet/CSharp/customactionprojectitem/itemtemplatewizard/customactionwizard.cs#8)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#8](../sharepoint/codesnippet/VisualBasic/customactionprojectitem/itemtemplatewizard/customactionwizard.vb#8)]  
  
## <a name="checkpoint"></a>검사점  
 이 연습에서는 마법사에 대 한 모든 코드 프로젝트에 포함 되었습니다. 오류 없이 컴파일되는지 확인 하려면 프로젝트를 빌드하십시오.  
  
#### <a name="to-build-your-project"></a>프로젝트를 빌드하려면  
  
1.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
## <a name="associating-the-wizard-with-the-item-template"></a>마법사 항목 템플릿을 사용 하 여 연결  
 마법사를 구현 했으므로 사용 하 여 연결 해야 하는 **사용자 지정 작업** 세 가지 주요 단계를 완료 하 여 항목 템플릿을:  
  
1.  강력한 이름의 마법사 어셈블리에 서명 합니다.  
  
2.  마법사 어셈블리에 대 한 공개 키를 토큰을 가져옵니다.  
  
3.  마법사 어셈블리에 대 한 참조에 대 한.vstemplate 파일에 추가 된 **사용자 지정 작업** 항목 템플릿을 합니다.  
  
#### <a name="to-sign-the-wizard-assembly-with-a-strong-name"></a>강력한 이름의 마법사 어셈블리에 서명 하려면  
  
1.  **솔루션 탐색기**에서 바로 가기 메뉴를 열고는 **ItemTemplateWizard** 프로젝트 노드를 선택한 후 **속성**합니다.  
  
2.  에 **서명** 탭을는 **어셈블리에 서명** 확인란 합니다.  
  
3.  에 **강력한 이름 키 파일 선택** 목록에서 선택  **\<새로 만들기 … >**합니다.  
  
4.  에 **강력한 이름 키 만들기** 대화 상자 선택을 취소 한 이름을 입력 합니다는 **암호로 내 키 파일 보호** 확인란을 선택한 후는 **확인** 단추입니다.  
  
5.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
#### <a name="to-get-the-public-key-token-for-the-wizard-assembly"></a>마법사 어셈블리에 대 한 공개 키 토큰 가져오려는  
  
1.  Visual Studio 명령 프롬프트 창에서 다음 실행 명령을 *PathToWizardAssembly* ItemTemplateWizard 프로젝트 개발에 빌드된 ItemTemplateWizard.dll 어셈블리의 전체 경로와 컴퓨터입니다.  
  
    ```  
    sn.exe -T PathToWizardAssembly  
    ```  
  
     ItemTemplateWizard.dll 어셈블리에 대 한 공개 키 토큰은 Visual Studio 명령 프롬프트 창에 기록 됩니다.  
  
2.  Visual Studio 명령 프롬프트 창을 계속 열어둡니다. 다음 절차를 완료 하려면 공개 키 토큰이 필요 합니다.  
  
#### <a name="to-add-a-reference-to-the-wizard-assembly-in-the-vstemplate-file"></a>.Vstemplate 파일에 마법사 어셈블리에 대 한 참조를 추가 하려면  
  
1.  **솔루션 탐색기**를 확장 하 고는 **ItemTemplate** 프로젝트 노드를 마우스 ItemTemplate.vstemplate 파일을 엽니다.  
  
2.  파일의 끝에 다음 추가 `WizardExtension` 사이 요소는 `</TemplateContent>` 및 `</VSTemplate>` 태그입니다. 대체는 *YourToken* 의 값은 `PublicKeyToken` 이전 절차에서 가져온 공개 키 토큰을 사용 하 여 특성입니다.  
  
    ```  
    <WizardExtension>  
      <Assembly>ItemTemplateWizard, Version=1.0.0.0, Culture=neutral, PublicKeyToken=YourToken</Assembly>  
      <FullClassName>ItemTemplateWizard.CustomActionWizard</FullClassName>  
    </WizardExtension>  
    ```  
  
     에 대 한 자세한 내용은 `WizardExtension` 요소 참조 [WizardExtension 요소 &#40; Visual Studio 서식 파일 &#41; ](/visualstudio/extensibility/wizardextension-element-visual-studio-templates).  
  
3.  파일을 저장한 후 닫습니다.  
  
## <a name="adding-replaceable-parameters-to-the-elementsxml-file-in-the-item-template"></a>항목 템플릿에서 Elements.xml 파일에 대체 가능 매개 변수를 추가합니다.  
 Elements.xml 파일 ItemTemplate 프로젝트에 여러 개의 대체 가능 매개 변수를 추가 합니다. 이러한 매개 변수에서 초기화 되는 `PopulateReplacementDictionary` 에서 메서드는 `CustomActionWizard` 앞에서 정의한 클래스입니다. 사용자가 사용자 지정 작업 프로젝트 항목을 프로젝트에 추가 하는 경우 Visual Studio는 자동으로 새 프로젝트 항목에 대 한 Elements.xml 파일에서 이러한 매개 변수를 마법사에서 지정한 값으로 바꿉니다.  
  
 대체 가능 매개 변수는 시작 하 고 달러 기호 ($) 문자로 끝나는 토큰입니다. 사용자 고유의 대체 가능 매개 변수를 정의 하는 것 외에도 SharePoint 프로젝트 시스템을 정의 하 고 초기화 하는 기본 제공 매개 변수를 사용할 수 있습니다. 자세한 내용은 참조 [대체 가능 매개 변수](../sharepoint/replaceable-parameters.md)합니다.  
  
#### <a name="to-add-replaceable-parameters-to-the-elementsxml-file"></a>Elements.xml 파일에 대체 가능 매개 변수를 추가 하려면  
  
1.  ItemTemplate 프로젝트에서 Elements.xml 파일의 내용을 다음 XML로 대체 합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Elements Id="$guid8$" xmlns="http://schemas.microsoft.com/sharepoint/">  
      <CustomAction Id="$IdValue$"  
                    GroupId="$GroupIdValue$"  
                    Location="$LocationValue$"  
                    Sequence="1000"  
                    Title="$TitleValue$"  
                    Description="$DescriptionValue$" >  
        <UrlAction Url="$UrlValue$"/>  
      </CustomAction>  
    </Elements>  
    ```  
  
     값을 변경 하는 새 XML는 `Id`, `GroupId`, `Location`, `Description`, 및 `Url` 특성을 대체 가능 매개 변수입니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
## <a name="adding-the-wizard-to-the-vsix-package"></a>VSIX 패키지를 마법사 추가  
 VSIX 프로젝트에서 source.extension.vsixmanifest 파일에서 프로젝트 항목을 포함 하는 VSIX 패키지 배포 될 수 있도록 마법사 프로젝트에 대 한 참조를 추가 합니다.  
  
#### <a name="to-add-the-wizard-to-the-vsix-package"></a>마법사는 VSIX 패키지를 추가 하려면  
  
1.  **솔루션 탐색기**에서 바로 가기 메뉴를 열고는 **source.extension.vsixmanifest** CustomActionProjectItem 프로젝트에서 파일을 선택한 후 **열고** 를 열려면 매니페스트 편집기에서 파일입니다.  
  
2.  매니페스트 편집기에서 선택는 **자산** 탭 한 다음 선택에서 **새로** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 나타납니다.  
  
3.  에 **형식** 목록에서 선택 **Microsoft.VisualStudio.Assembly**합니다.  
  
4.  에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
5.  에 **프로젝트** 목록에서 선택 **ItemTemplateWizard**를 선택한 후는 **확인** 단추입니다.  
  
6.  메뉴 모음에서 **빌드**, **솔루션 빌드**, 솔루션이 오류 없이 컴파일되는지 확인 합니다.  
  
## <a name="testing-the-wizard"></a>마법사를 테스트합니다.  
 이제 마법사를 테스트할 준비가 되었습니다. 먼저, Visual Studio의 실험적 인스턴스에서 CustomActionProjectItem 솔루션을 디버깅을 시작 합니다. 그런 다음 마법사 사용자 지정 작업 프로젝트 항목에 대 한 실험적 인스턴스의 Visual Studio에서 SharePoint 프로젝트의 테스트. 마지막으로, 빌드 및 사용자 지정 작업 예상 대로 작동 하는지 확인 하기 위해 SharePoint 프로젝트를 실행 합니다.  
  
#### <a name="to-start-to-debug-the-solution"></a>솔루션을 디버깅을 시작 하려면  
  
1.  관리 자격 증명으로 Visual Studio를 다시 시작 하 고 CustomActionProjectItem 솔루션을 엽니다.  
  
2.  ItemTemplateWizard 프로젝트에서 CustomActionWizard 코드 파일을 열고 다음 코드의 첫 번째 줄에 중단점을 추가 `RunStarted` 메서드.  
  
3.  메뉴 모음에서 **디버그**, **예외**합니다.  
  
4.  에 **예외** 대화 상자에서 다음 사항을 확인는 **throw 됨** 및 **사용자가 처리** 에 대 한 확인란 **공용 언어 런타임 예외**이 삭제 되 고 선택 합니다는 **확인** 단추입니다.  
  
5.  F5 키를 선택 하 여 하거나 메뉴 모음에서 디버깅, 선택 시작 **디버그**, **디버깅 시작**합니다.  
  
     Visual Studio 작업 프로젝트 Item\1.0 %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Custom에 확장을 설치 하 고 Visual Studio의 실험적 인스턴스를 시작 합니다. Visual Studio의이 인스턴스에 있는 프로젝트 항목을 테스트 합니다.  
  
#### <a name="to-test-the-wizard-in-visual-studio"></a>Visual Studio에서 마법사를 테스트 하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **파일**, **새로**, **프로젝트**합니다.  
  
2.  확장는 **Visual C#** 또는 **Visual Basic** 노드 (언어에 따라 항목 템플릿을 지원)를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
3.  프로젝트 템플릿 목록에서 선택 **SharePoint 2010 프로젝트**, 프로젝트 이름을 **CustomActionWizardTest**를 선택한 후는 **확인** 단추입니다.  
  
4.  에 **SharePoint 사용자 지정 마법사**, 디버깅을 위해 사용 하려는 사이트의 URL을 입력 한 다음 선택에서 **마침** 단추입니다.  
  
5.  **솔루션 탐색기**프로젝트 노드에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 항목**합니다.  
  
6.  에 **새 항목 추가-CustomItemWizardTest** 대화 상자에서 **SharePoint** 노드를 확장 한 후의 **2010** 노드.  
  
7.  프로젝트 항목의 목록에서 선택 된 **사용자 지정 작업** 항목을 선택한 다음 선택는 **추가** 단추입니다.  
  
8.  Visual Studio의 다른 인스턴스에서 코드에서 이전에 설정한 중단점에서 중지 확인는 `RunStarted` 메서드.  
  
9. F5 키를 선택 하 여 하거나 메뉴 모음에서 선택에서 프로젝트 디버깅을 계속 **디버그**, **계속**합니다.  
  
     SharePoint 사용자 지정 마법사가 나타납니다.  
  
10. 아래 **위치**, 선택는 **목록 편집** 옵션 단추입니다.  
  
11. 에 **그룹 ID** 목록에서 선택 **통신**합니다.  
  
12. 에 **제목** 상자에 입력 **SharePoint 개발자 센터**합니다.  
  
13. 에 **설명** 상자에 입력 **SharePoint 개발자 센터 웹 사이트를 엽니다**합니다.  
  
14. 에 **URL** 상자에 입력 **http://msdn.microsoft.com/sharepoint/default.aspx**, 선택한 후는 **마침** 단추입니다.  
  
     명명 된 항목을 추가 하는 겨냥 Studio **CustomAction1** 해당 프로젝트에는 Elements.xml 파일 편집기에서 열립니다. Elements.xml 마법사에서 지정한 값이 들어 있는지 확인 합니다.  
  
#### <a name="to-test-the-custom-action-in-sharepoint"></a>SharePoint에서 사용자 지정 작업을 테스트 하려면  
  
1.  Visual Studio의 실험적 인스턴스에서 F5 키를 선택 하거나, 메뉴 모음에서 선택 **디버그**, **디버깅 시작**합니다.  
  
     사용자 지정 작업을 하 여 지정 된 SharePoint 사이트에 배포 되 고 패키지는 **사이트 URL** 속성은 프로젝트와 웹 브라우저의이 사이트의 기본 페이지에 열립니다.  
  
    > [!NOTE]  
    >  경우는 **스크립트 디버깅 사용 안 함** 선택 대화 상자가 나타나면는 **예** 단추입니다.  
  
2.  SharePoint 사이트 목록 영역에 선택 된 **작업** 링크 합니다.  
  
     **작업-모든 작업** 페이지가 나타납니다.  
  
3.  에 **목록 도구** 탭 리본 메뉴의 선택는 **목록** 탭을 선택한 다음는 **설정** 그룹에서 선택 **목록 설정**합니다.  
  
     **목록 설정** 페이지가 나타납니다.  
  
4.  아래는 **통신** 선택 페이지의 맨 위 근처에 머리글을 **SharePoint 개발자 센터** 링크를 브라우저에 웹 사이트 http://msdn.microsoft.com/sharepoint/ 열리는지 확인 default.aspx를 닫은 후 브라우저.  
  
## <a name="cleaning-up-the-development-computer"></a>개발 컴퓨터를 정리합니다.  
 프로젝트 항목의 테스트를 마친 후에 Visual Studio의 실험적 인스턴스에서 프로젝트 항목 템플릿을 제거 합니다.  
  
#### <a name="to-clean-up-the-development-computer"></a>개발 컴퓨터를 정리 하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **도구**, **확장명 및 업데이트**합니다.  
  
     **확장명 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장의 목록에서 선택는 **사용자 지정 작업 프로젝트 항목** 확장을 선택한 후는 **제거** 단추입니다.  
  
3.  표시 되는 대화 상자에서 선택은 **예** 단추에서 확장을 제거 하 고 다음을 선택 하도록 확인할 수는 **지금 다시 시작** 단추 제거를 완료 합니다.  
  
4.  Visual Studio (실험적 인스턴스 및 CustomActionProjectItem 솔루션 열릴 Visual Studio의 인스턴스)의 두 인스턴스를 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 항목 템플릿, 1 부와 사용자 지정 작업 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [사용자 지정 SharePoint 프로젝트 항목 형식 정의](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Visual Studio 템플릿 스키마 참조](/visualstudio/extensibility/visual-studio-template-schema-reference)   
 [방법: 마법사를 사용 하 여 프로젝트 템플릿이 함께 제공](../extensibility/how-to-use-wizards-with-project-templates.md)   
 [기본 사용자 지정 작업 위치 및 Id](http://go.microsoft.com/fwlink/?LinkId=181964)  
  
  