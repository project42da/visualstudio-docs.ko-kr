---
title: "Walkthrough: Creating a SharePoint Project Extension | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "projects [SharePoint development in Visual Studio], extending"
  - "SharePoint development in Visual Studio, extending projects"
  - "SharePoint projects, extending"
ms.assetid: 5547e2ed-47a3-48f1-9619-42149c03df76
caps.latest.revision: 26
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 25
---
# Walkthrough: Creating a SharePoint Project Extension
  이 연습에서는 SharePoint 프로젝트용 확장을 만드는 방법을 보여 줍니다.  프로젝트 확장 프로젝트 추가, 삭제 또는 이름이 바뀐 경우와 같은 프로젝트 수준 이벤트에 응답할 수 있습니다.  또한 사용자 지정 속성을 추가하거나 속성 값이 변경될 때 응답할 수 있습니다.  프로젝트 항목 확장과 달리 프로젝트 확장은 특정 SharePoint 프로젝트 형식에 연결할 수 없습니다.  프로젝트 확장을 만들면 종류에 관계없이 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 프로젝트를 열 때 확장이 로드됩니다.  
  
 이 연습에서는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 만든 모든 SharePoint 프로젝트에 추가되는 사용자 지정 부울 속성을 만듭니다.  이 속성이 **True**로 설정되면 새 속성이 이미지 리소스 폴더를 프로젝트에 추가하거나 매핑합니다.  **False**로 설정된 경우에는 이미지 폴더가 있으면 이 폴더가 제거됩니다.  자세한 내용은 [방법: 매핑된 폴더 추가 및 제거](../sharepoint/how-to-add-and-remove-mapped-folders.md)을 참조하십시오.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   다음을 수행하는 프로젝트용 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 확장 만들기  
  
    -   사용자 지정 프로젝트 속성을 속성 창에 추가합니다.  이 속성은 모든 SharePoint 프로젝트에 적용됩니다.  
  
    -   SharePoint 프로젝트 개체 모델을 사용하여 매핑된 폴더를 프로젝트에 추가합니다.  
  
    -   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 자동화 개체 모델\(DTE\)을 사용하여 매핑된 폴더를 프로젝트에서 삭제합니다.  
  
-   프로젝트 속성의 확장 어셈블리를 배포하기 위한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지 빌드  
  
-   프로젝트 속성 디버깅 및 테스트  
  
## 사전 요구 사항  
 이 연습을 완료하려면 개발 컴퓨터에 다음 구성 요소가 필요합니다.  
  
-   지원되는 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)], SharePoint 및 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)] 이 연습에서는 [!INCLUDE[TLA2#tla_sdk](../sharepoint/includes/tla2sharptla-sdk-md.md)]의 **VSIX 프로젝트** 템플릿을 사용하여 프로젝트 속성 확장을 배포하기 위한 VSIX 패키지를 만듭니다.  자세한 내용은 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
## 프로젝트 만들기  
 이 연습을 완료하려면 두 프로젝트를 만들어야 합니다.  
  
-   VSIX 패키지를 만들어 프로젝트 확장을 배포하기 위한 VSIX 프로젝트  
  
-   프로젝트 확장을 구현하는 클래스 라이브러리 프로젝트  
  
 먼저 프로젝트를 만들어 연습을 시작합니다.  
  
#### VSIX 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
3.  에  **새 프로젝트** 대화 상자에서 확장은  **C\#** 또는  **Visual Basic** 노드를 다음 선택은  **확장성** 노드.  
  
    > [!NOTE]  
    >  이 노드는 Visual Studio SDK 설치만 하면 사용할 수 있습니다.  자세한 내용은 이 항목의 앞부분에 나오는 사전 요구 사항 단원을 참조하십시오.  
  
4.  대화 상자의 맨 위에 있는 선택  **.NET Framework 4.5** .NET Framework 버전의 목록에서 다음 선택은  **VSIX 프로젝트** 템플릿.  
  
5.  에  **이름** 상자에 입력  **ProjectExtensionPackage**, 다음 선택은  **확인** 단추입니다.  
  
     **ProjectExtensionPackage** 프로젝트에 나타납니다  **솔루션 탐색기**.  
  
#### 확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**, 솔루션 노드 바로 가기 메뉴를 열고  **추가**, 다음 선택  **새 프로젝트**.  
  
    > [!NOTE]  
    >  [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 프로젝트, 솔루션 노드가 표시  **솔루션 탐색기** 만  **솔루션 항상 표시** 확인란에서 선택 되는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca).  
  
2.  에  **새 프로젝트** 대화 상자에서 확장 된  **C\#** 또는  **Visual Basic** 노드를 다음 선택  **Windows**.  
  
3.  대화 상자의 맨 위에 있는 선택  **.NET Framework 4.5** .NET Framework 버전의 목록에서 다음 선택은  **클래스 라이브러리** 프로젝트 템플릿.  
  
4.  에  **이름** 상자에 입력  **ProjectExtension**, 다음 선택은  **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 솔루션에 **ProjectExtension** 프로젝트를 추가하고 기본 Class1 코드 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제합니다.  
  
## 프로젝트 구성  
 프로젝트 확장을 만드는 코드를 작성하기 전에 코드 파일과 어셈블리 참조를 확장 프로젝트에 추가합니다.  
  
#### 프로젝트를 구성하려면  
  
1.  이름이 지정 된 코드 파일을 추가  **CustomProperty** ProjectExtension 프로젝트입니다.  
  
2.  바로 가기 메뉴를 열고를  **ProjectExtension** 프로젝트를 하 고 선택  **참조 추가**.  
  
3.  에  **참조 관리자 – CustomProperty** 대화 상자에서 선택은  **프레임 워크** 노드 및 다음 System.ComponentModel.Composition 및 System.Windows.Forms 어셈블리 옆에 있는 확인란을 선택 합니다.  
  
4.  선택은  **확장** 노드를 Microsoft.VisualStudio.SharePoint 하 고 EnvDTE 어셈블리 옆에 있는 확인란을 선택 하 고 선택 된  **확인** 단추.  
  
5.  **솔루션 탐색기**아래에서  **참조** 폴더에는  **ProjectExtension** 프로젝트를 선택  **EnvDTE**.  
  
6.  **속성** 창에서 **Interop 형식 포함** 속성을 **False**로 변경합니다.  
  
## 새 SharePoint 프로젝트 속성 정의  
 프로젝트 확장 및 새 프로젝트 속성의 동작을 정의하는 클래스를 만듭니다.  새 프로젝트 확장을 정의하기 위해 클래스에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 인터페이스를 구현합니다.  SharePoint 프로젝트용 확장을 정의하려는 경우 항상 이 인터페이스를 구현합니다.  또한 클래스에 <xref:System.ComponentModel.Composition.ExportAttribute> 메서드를 추가합니다.  이 특성을 사용하면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 구현을 찾아 로드할 수 있습니다.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 형식을 해당 특성의 생성자에 전달합니다.  
  
#### 새 SharePoint 프로젝트 속성을 정의하려면  
  
1.  CustomProperty 코드 파일에 다음 코드를 붙여 넣습니다.  
  
     [!code-csharp[SPExt_ProjectExtension#1](../snippets/csharp/VS_Snippets_OfficeSP/spext_projectextension/cs/projectextension/customproperty.cs#1)]
     [!code-vb[SPExt_ProjectExtension#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spext_projectextension/vb/projectextension/customproperty.vb#1)]  
  
## 솔루션 빌드  
 다음 단계로 솔루션을 빌드하여 솔루션이 오류 없이 컴파일되는지 확인합니다.  
  
#### 솔루션을 빌드하려면  
  
1.  메뉴 표시줄에서 선택  **빌드**,  **솔루션 빌드**.  
  
## 프로젝트 속성 확장을 배포하기 위한 VSIX 패키지 만들기  
 프로젝트 확장을 배포하려면 솔루션에서 VSIX 프로젝트를 사용하여 VSIX 패키지를 만듭니다.  먼저 VSIX 프로젝트에 포함된 source.extension.vsixmanifest 파일을 수정하여 VSIX 패키지를 구성합니다.  그런 다음 솔루션을 빌드하여 VSIX 패키지를 만듭니다.  
  
#### VSIX 패키지를 구성하고 만들려면  
  
1.  **솔루션 탐색기**source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 선택 된  **열기** 단추.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]파일 매니페스트 디자이너에서 열립니다.  에 표시 되는 정보는  **메타 데이터** 탭에도 표시는  **확장 및 업데이트**. VSIX 패키지를 모두 extension.vsixmanifest 파일이 필요합니다.  이 파일에 대한 자세한 내용은 [VSIX 확장 스키마 참조](http://msdn.microsoft.com/ko-kr/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)를 참조하십시오.  
  
2.  에 있는  **제품명** 상자에 입력  **사용자 정의 프로젝트 속성**.  
  
3.  에 있는  **작성자** 상자에 입력  **Contoso**.  
  
4.  에 있는  **설명이** 상자에 입력  **매핑 이미지 리소스 폴더로 프로젝트를 전환 하는 사용자 지정 SharePoint 프로젝트 속성**.  
  
5.  선택은  **자산** 탭을 클릭 한 다음 선택은  **New** 단추.  
  
     **를 추가 하는 새로운 자산** 대화 상자가 나타납니다.  
  
6.  에 있는  **유형** 목록에서 선택  **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  이 값은 extension.vsixmanifest 파일의 `MEFComponent` 요소에 해당합니다.  이 요소는 VSIX 패키지의 확장 어셈블리 이름을 지정합니다.  자세한 내용은 [NIB: MEFComponent Element \(VSX Schema\)](http://msdn.microsoft.com/ko-kr/8a813141-8b73-44c9-b80b-ca85bbac9551)을 참조하십시오.  
  
7.  에  **소스** 목록에서 선택 된  **현재 솔루션의 프로젝트에** 옵션 단추.  
  
8.  에 있는  **프로젝트** 목록에서 선택  **ProjectExtension**.  
  
     이 값은 프로젝트에서 빌드하는 어셈블리의 이름을 식별 합니다.  
  
9. 선택  **확인** 닫을 수 있는  **추가 새 자산** 대화 상자.  
  
10. 메뉴 표시줄에서 선택  **파일**,  **모두 저장** 마침 및 다음 매니페스트 디자이너를 닫습니다.  
  
11. 메뉴 표시줄에서 선택  **빌드**,  **솔루션 빌드**, 및 다음 프로젝트가 오류 없이 컴파일되는지 확인 합니다.  
  
12. **솔루션 탐색기**, 바로 가기 메뉴를 열고는  **ProjectExtensionPackage** 프로젝트를 하 고 선택의  **파일 탐색기에서 폴더 열기** 단추.  
  
13. **파일 탐색기**, ProjectExtensionPackage 프로젝트의 빌드 출력 폴더를 열고 ProjectExtensionPackage.vsix 이라는 파일이 있는 폴더에 있습니다 확인 합니다.  
  
     기본적으로 빌드 출력 경로는 프로젝트 파일이 포함된 폴더 아래에 있는 ..  \\bin\\Debug 폴더입니다.  
  
## 프로젝트 속성 테스트  
 이제 사용자 지정 프로젝트 속성을 테스트할 준비가 되었습니다.  실험적 인스턴스에서 새 프로젝트 속성 확장을 테스트 하 고 디버깅 하는 것이 가장 쉽습니다 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  이 인스턴스의 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 는 VSIX 또는 기타 확장성 프로젝트를 실행할 때 만들어집니다.  프로젝트를 디버깅 한 후 시스템에 확장을 설치 및 디버깅의 일반 인스턴스를 테스트 하 고 계속 수 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
#### 실험 모드의 Visual Studio 인스턴스에서 확장을 디버깅 및 테스트하려면  
  
1.  다시 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 관리 자격 증명 및 다음 열기 ProjectExtensionPackage 솔루션입니다.  
  
2.  프로젝트의 디버그 빌드를 선택 하 여 시작 된  **F5** 키 또는 메뉴 모음을 선택  **디버깅**,  **디버깅 시작**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]확장 프로젝트 Property\\1.0 %userprofile%\\appdata\\local\\microsoft\\visualstudio\\11.0exp\\extensions\\contoso\\custom을 설치 하 고 실험 인스턴스를 시작 합니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
3.  실험적 인스턴스에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]팜 솔루션에 대 한 SharePoint 프로젝트를 만들고 마법사의 다른 값에 대 한 기본값을 사용 합니다.  
  
    1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
    2.  상단에는  **새 프로젝트** 대화 상자에서 선택  **.NET Framework 3.5** .NET Framework 버전의 목록에서입니다.  
  
         SharePoint 도구 확장 기능이이 버전의 요구는 [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)].  
  
    3.  아래는  **템플릿** 노드를 확장은  **C\#** 또는  **Visual Basic** 노드를 선택의  **SharePoint** 노드를 다음 선택은  **2010** 노드.  
  
    4.  선택은  **SharePoint 2010 프로젝트** 서식 파일을 클릭 하 고 다음을 입력  **ModuleTest** 프로젝트 이름으로.  
  
4.  **솔루션 탐색기**, 선택은  **ModuleTest** 프로젝트 노드.  
  
     새 사용자 지정 속성 **Map Images Folder**가 **속성** 창에 나타나고, 이 속성의 기본값은 **False**입니다.  
  
5.  해당 속성의 값을 변경 **True**.  
  
     이미지 리소스 폴더가 SharePoint 프로젝트에 추가됩니다.  
  
6.  해당 속성의 값을 다시 변경 **False**.  
  
     선택 하는 경우는  **예** 단추는  **Images 폴더 삭제?** 대화 상자에서 리소스 폴더를 SharePoint 프로젝트에서 삭제 되는 이미지입니다.  
  
7.  실험 모드의 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 인스턴스를 닫습니다.  
  
## 참고 항목  
 [Extending SharePoint Projects](../sharepoint/extending-sharepoint-projects.md)   
 [How to: Add a Property to SharePoint Projects](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)   
 [Converting Between SharePoint Project System Types and Other Visual Studio Project Types](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)   
 [Saving Data in Extensions of the SharePoint Project System](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)   
 [Associating Custom Data with SharePoint Tools Extensions](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)  
  
  