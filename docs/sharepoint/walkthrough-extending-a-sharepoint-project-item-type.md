---
title: "Walkthrough: Extending a SharePoint Project Item Type | Microsoft Docs"
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
  - "project items [SharePoint development in Visual Studio], extending"
  - "SharePoint project items, extending"
  - "SharePoint development in Visual Studio, extending project items"
ms.assetid: 1cea4e0f-ce33-4cd7-a664-800184865456
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 35
---
# Walkthrough: Extending a SharePoint Project Item Type
  **비즈니스 데이터 연결 모델** 프로젝트 항목을 사용하여 SharePoint에서 BDC\(비즈니스 데이터 연결\) 서비스의 모델을 만들 수 있습니다.  기본적으로 이 프로젝트 항목을 사용하여 모델을 만들면 모델의 데이터가 사용자에게 표시되지 않습니다.  사용자가 데이터를 볼 수 있도록 하려면 SharePoint에서 외부 목록도 만들어야 합니다.  
  
 이 연습에서는 **비즈니스 데이터 연결 모델** 프로젝트 항목의 확장을 만듭니다.  개발자는 확장을 사용하여 BDC 모델의 데이터를 표시하는 외부 목록을 프로젝트에 만들 수 있습니다.  이 연습에서는 다음 작업을 수행합니다.  
  
-   다음 두 가지 주요 작업을 수행하는 Visual Studio 확장 만들기  
  
    -   BDC 모델의 데이터를 표시하는 외부 목록을 생성합니다.  이 확장은 SharePoint 프로젝트 시스템의 개체 모델을 사용하여 목록을 정의하는 Elements.xml 파일을 생성합니다.  또한 BDC 모델과 함께 배포되도록 프로젝트에 파일을 추가합니다.  
  
    -   **솔루션 탐색기**에서 **비즈니스 데이터 연결 모델** 프로젝트 항목에 대한 바로 가기 메뉴 항목을 추가합니다.  개발자는 이 메뉴 항목을 클릭하여 BDC 모델에 대한 외부 목록을 생성할 수 있습니다.  
  
-   확장 어셈블리를 배포하기 위한 VSIX\(Visual Studio Extension\) 패키지 빌드  
  
-   확장 테스트  
  
## 사전 요구 사항  
 이 연습을 완료하려면 개발 컴퓨터에 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows, SharePoint 및 Visual Studio 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)] 이 연습에서는 SDK의 **VSIX 프로젝트** 템플릿을 사용하여 프로젝트 항목을 배포하기 위한 VSIX 패키지를 만듭니다.  자세한 내용은 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
 다음 개념을 알고 있으면 연습을 완료하는 데 도움이 되지만 반드시 필요하지는 않습니다.  
  
-   [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]의 BDC 서비스.  자세한 내용은 [BDC 아키텍처](http://go.microsoft.com/fwlink/?LinkId=177798)을 참조하십시오.  
  
-   BDC 모델의 XML 스키마.  자세한 내용은 [BDC 모델 하부 구조](http://go.microsoft.com/fwlink/?LinkId=177799) 를 참조하십시오.  
  
## 프로젝트 만들기  
 이 연습을 완료하려면 두 프로젝트를 만들어야 합니다.  
  
-   VSIX 패키지를 만들어 프로젝트 항목 확장을 배포하기 위한 VSIX 프로젝트  
  
-   프로젝트 항목 확장을 구현하는 클래스 라이브러리 프로젝트  
  
 먼저 프로젝트를 만들어 연습을 시작합니다.  
  
#### VSIX 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
3.  **새 프로젝트** 대화 상자에서 **Visual C\#** 또는 **Visual Basic** 노드를 확장한 다음 **확장성** 노드를 선택합니다.  
  
    > [!NOTE]  
    >  **확장성** 노드는 Visual Studio 2010 SDK를 설치한 경우에만 사용할 수 있습니다.  자세한 내용은 이 항목의 앞부분에 나오는 사전 요구 사항 단원을 참조하십시오.  
  
4.  **새 프로젝트** 대화 상자 맨 위의 목록에서 **.NET Framework 4.5**를 선택합니다.  
  
     SharePoint 도구 확장을 사용하려면 이 .NET Framework 버전의 기능이 필요합니다.  
  
5.  **VSIX 프로젝트** 템플릿을 선택합니다.  
  
6.  **이름** 상자에서 **GenerateExternalDataLists**을 입력한 후 **확인** 단추를 선택합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 **솔루션 탐색기**에 **GenerateExternalDataLists** 프로젝트를 추가합니다.  
  
7.  Source.extension.vsixmanifest 파일이 자동으로 열리지 않으면, GenerateExternalDataLists 프로젝트에서 바로 가기 메뉴를 연 다음 **열기** 를 선택합니다.  
  
8.  Source.extension.vsixmanifest 파일에 작성자 필드에서 비어 있지 않은 항목이 있음을 확인하려면\(Contoso 입력\), 파일을 저장한 후 닫습니다.  
  
#### 확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**에서 **GenerateExternalDataLists** 솔루션 노드의 바로 가기 메뉴를 열고 **추가**를 선택한 다음 **새 프로젝트**를 선택합니다.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)에서 **솔루션 항상 표시** 확인란을 선택한 경우에만 **솔루션 탐색기**에 솔루션 노드가 표시됩니다.  
  
2.  **새 프로젝트 추가** 대화 상자에서 **Visual C\#** 또는 **Visual Basic** 노드를 확장한 다음 **Windows** 노드를 클릭합니다.  
  
3.  대화 상자 맨 위의 목록에서 **.NET Framework 4.5**를 선택합니다.  
  
4.  프로젝트 템플릿 목록에서 **클래스 라이브러리**를 선택합니다.  
  
5.  **이름** 텍스트 상자에서 **BdcProjectItemExtension**을 입력한 후 **확인** 단추를 선택합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 솔루션에 **BdcProjectItemExtension** 프로젝트를 추가하고 기본 Class1 코드 파일을 엽니다.  
  
6.  프로젝트에서 Class1 코드 파일을 삭제합니다.  
  
## 확장 프로젝트 구성  
 프로젝트 항목 확장을 만드는 코드를 작성하기 전에 코드 파일과 어셈블리 참조를 확장 프로젝트에 추가합니다.  
  
#### 프로젝트를 구성하려면  
  
1.  BdcProjectItemExtension 프로젝트에서 다음과 같이 이름이 지정된 코드 파일 두 개를 추가합니다.  
  
    -   ProjectItemExtension  
  
    -   GenerateExternalDataLists  
  
2.  BdcProjectItemExtension 프로젝트를 선택한 다음, 메뉴 표시줄에서 **프로젝트**, **참조 추가**를 선택합니다.  
  
3.  **어셈블리** 노드에서 **프레임 워크** 노드를 선택한 다음, 다음의 어셈블리에 대한 확인란을 선택합니다:  
  
    -   System.ComponentModel.Composition  
  
    -   WindowsBase  
  
4.  **어셈블리** 노드에서 **확장** 노드를 선택한 다음, 다음의 어셈블리에 대한 확인란을 선택합니다:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
5.  **확인** 단추를 선택합니다.  
  
## 프로젝트 항목 확장 정의  
 **비즈니스 데이터 연결 모델** 프로젝트 항목의 확장을 정의하는 클래스를 만듭니다.  확장을 정의하기 위해 클래스에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 인터페이스를 구현합니다.  기존 프로젝트 항목 형식을 확장하려는 경우 이 인터페이스를 구현합니다.  
  
#### 프로젝트 항목 확장을 정의하려면  
  
1.  다음 코드를 ProjectItemExtension 코드 파일에 붙여넣습니다.  
  
    > [!NOTE]  
    >  이 코드를 추가하고 나면 프로젝트에서 컴파일 오류가 발생합니다.  이러한 오류는 이후 단계에서 코드를 추가하면 사라집니다.  
  
     [!code-csharp[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitemextension.bdcgenerateexternaldatalists/cs/bdcprojectitemextension/projectitemextension.cs#1)]
     [!code-vb[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitemextension.bdcgenerateexternaldatalists/vb/bdcprojectitemextension/projectitemextension.vb#1)]  
  
## 외부 데이터 목록 만들기  
 BDC 모델의 각 엔터티에 대해 외부 데이터 목록을 만드는 `GenerateExternalDataListsExtension` 클래스의 부분 정의를 추가합니다.  외부 데이터 목록을 만들기 위해 이 코드에서는 먼저 BDC 모델 파일의 XML 데이터를 구문 분석하여 BDC 모델의 엔터티 데이터를 읽습니다.  그런 다음 BDC 모델을 기반으로 하여 목록 인스턴스를 만들고 프로젝트에 이 목록 인스턴스를 추가합니다.  
  
#### 외부 데이터 목록을 만들려면  
  
1.  다음 예제 코드 복사한 후 GenerateExternalDataLists 코드 파일에 붙여넣습니다.  
  
     [!code-csharp[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#2](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitemextension.bdcgenerateexternaldatalists/cs/bdcprojectitemextension/generateexternaldatalists.cs#2)]
     [!code-vb[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#2](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitemextension.bdcgenerateexternaldatalists/vb/bdcprojectitemextension/generateexternaldatalists.vb#2)]  
  
## 검사점  
 이 연습의 이전 단계를 통해 프로젝트 항목 확장을 위한 모든 코드가 프로젝트에 포함되었습니다.  솔루션을 빌드하여 프로젝트가 오류 없이 컴파일되는지 확인합니다.  
  
#### 솔루션을 빌드하려면  
  
1.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
## 프로젝트 항목 확장을 배포하기 위한 VSIX 패키지 만들기  
 확장을 배포하려면 솔루션에서 VSIX 프로젝트를 사용하여 VSIX 패키지를 만듭니다.  먼저 VSIX 프로젝트에 포함된 source.extension.vsixmanifest 파일을 수정하여 VSIX 패키지를 구성합니다.  그런 다음 솔루션을 빌드하여 VSIX 패키지를 만듭니다.  
  
#### VSIX 패키지를 구성하고 만들려면  
  
1.  **솔루션 탐색기**에서, GenerateExternalDataLists 프로젝트의 source.extension.vsixmanifest 파일에 대한 바로 가기 메뉴를 연 다음 **열기**를 선택합니다.  
  
     매니페스트 편집기에서 파일이 열립니다.  source.extension.vsixmanifest 파일은 모든 VSIX 패키지에 필요한 extension.vsixmanifest 파일의 기초를 제공합니다.  이 파일에 대한 자세한 내용은 [VSIX 확장 스키마 참조](http://msdn.microsoft.com/ko-kr/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)를 참조하십시오.  
  
2.  **제품 이름** 상자에 **External Data List Generator**를 입력합니다.  
  
3.  **만든 이** 상자에 **Contoso**를 입력합니다.  
  
4.  **설명** 상자에 **외부 데이터 목록을 생성하는데 사용할 수 있는 비즈니스 데이터 연결 모델 프로젝트 항목의 확장**을 입력합니다.  
  
5.  편집기의 **자산** 탭에서 **New** 버튼을 선택합니다.  
  
     **새 자산 추가** 대화 상자가 나타납니다.  
  
6.  **유형** 목록에서, **Microsoft.VisualStudio.MefComponent**를 선택합니다.  
  
    > [!NOTE]  
    >  이 값은 extension.vsixmanifest 파일의 `MefComponent` 요소에 해당합니다.  이 요소는 VSIX 패키지의 확장 어셈블리 이름을 지정합니다.  자세한 내용은 [NIB: MEFComponent Element \(VSX Schema\)](http://msdn.microsoft.com/ko-kr/8a813141-8b73-44c9-b80b-ca85bbac9551)을 참조하십시오.  
  
7.  **원본** 목록에서 **현재 솔루션의 프로젝트**를 선택합니다.  
  
8.  **프로젝트** 목록에서 **BdcProjectItemExtension**를 선택한 다음 **확인** 단추를 선택합니다.  
  
9. 메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
10. 프로젝트가 오류 없이 컴파일 및 빌드 되는지 확인합니다.  
  
11. GenerateExternalDataLists 프로젝트의 빌드 출력 폴더가 GenerateExternalDataLists.vsix 파일을 포함하는지 확인합니다.  
  
     기본적으로, 빌드 출력 폴더는 프로젝트 파일을 포함하는 폴더 아래의 폴더인 ..\\bin\\Debug 입니다.  
  
## 프로젝트 항목 확장 테스트  
 이제 프로젝트 항목 확장을 테스트할 준비가 되었습니다.  우선 실험 모드의 Visual Studio 인스턴스에서 확장 프로젝트 디버깅을 시작합니다.  그런 다음 실험 모드의 Visual Studio 인스턴스에서 확장을 사용하여 BDC 모델에 대한 외부 목록을 생성합니다.  마지막으로, SharePoint 사이트에서 외부 목록을 열어 예상대로 작동하는지 확인합니다.  
  
#### 확장 디버깅을 시작하려면  
  
1.  필요한 경우, 관리 자격 증명을 사용하여 Visual Studio 다시 시작한 다음 GenerateExternalDataLists 솔루션을 엽니다.  
  
2.  BdcProjectItemExtension 프로젝트에서 ProjectItemExtension 코드 파일을 연 다음 `Initialize` 메서드의 코드 줄에 중단점을 추가합니다.  
  
3.  GenerateExternalDataLists 코드 파일을 연 다음 `GenerateExternalDataLists_Execute` 메서드의 코드 첫째 줄에 중단점을 추가합니다.  
  
4.  F5 키를 선택하거나 메뉴 모음에서 **디버깅**, **디버깅 시작**을 선택하여 디버깅을 시작합니다.  
  
     Visual Studio에서는 확장을 %UserProfile%\\AppData\\Local\\Microsoft\\VisualStudio\\10.0Exp\\Extensions\\Contoso\\External Data List Generator\\1.0에 설치하고 실험 모드의 Visual Studio 인스턴스를 시작합니다.  이 Visual Studio 인스턴스에서 프로젝트 항목을 테스트합니다.  
  
#### 확장을 테스트하려면  
  
1.  실험 모드의 Visual Studio 인스턴스에서 메뉴 바의 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
2.  **새 프로젝트** 대화 상자에서 **템플릿** 노드를 확장하고, **Visual C\#** 노드를 확장하고, **SharePoint** 노드를 확장한 다음 **2010**을 선택합니다.  
  
3.  대화 상자 맨 위의 목록에서 **.NET Framework 3.5** 가 선택되어 있는지 확인합니다.  [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]용 프로젝트에는 이 .NET Framework 버전이 필요합니다.  
  
4.  프로젝트 템플릿 목록에서 **SharePoint 2010**을 선택합니다.  
  
5.  **이름** 상자에 **SharePointProjectTestBDC**을 입력한 후 **확인** 버튼을 선택합니다.  
  
6.  SharePoint 사용자 지정 마법사에서, 디버깅에 사용하려는 사이트의 URL을 입력하고, **팜 솔루션으로 배포**를 선택한 다음, **완료**버튼을 선택합니다.  
  
7.  SharePointProjectTestBDC 프로젝트에 대한 바로 가기 메뉴를 열고 **추가**를 선택한 다음 **새 항목**을 선택합니다.  
  
8.  **NewItem 추가 \- SharePointProjectTestBDC** 대화 상자에서, 설치 된 언어 노드를 확장한 다음 **SharePoint** 노드를 확장합니다.  
  
9. **2010** 노드를 선택한 다음 **비즈니스 데이터 연결 모델 \(팜 솔루션에서만\)** 템플릿을 선택합니다.  
  
10. **이름** 상자에 **TestBDCModel**을 입력한 다음 **추가** 버튼을 선택합니다.  
  
11. 다른 Visual Studio 인스턴스의 코드가 ProjectItemExtension 코드 파일의 `Initialize` 메서드에 이전에 설정한 중단점에서 중지하는지 확인합니다.  
  
12. Visual Studio의 중지된 인스턴스에서 **F5** 키를 누르거나 메뉴 모음에서 **디버그**, **계속** 을 눌러 프로젝트의 디버깅을 계속 합니다.  
  
13. Visual Studio 실험적 인스턴스에서 **F5** 키를 누르거나 메뉴 모음에서 **디버깅**, **디버깅 시작** 을 눌러 **TestBDCModel** 프로젝트를 빌드, 배포 및 실행합니다.  
  
     디버깅에 사용되는 SharePoint 사이트의 기본 페이지가 웹 브라우저에서 열립니다.  
  
14. 빠른 실행 영역의 **목록** 섹션에 프로젝트의 기본 BDC 모델을 기반으로 하는 목록이 아직 포함되지 않은 것을 확인합니다.  먼저 SharePoint 사용자 인터페이스를 사용하거나 프로젝트 항목 확장을 사용하여 외부 데이터 목록을 만들어야 합니다.  
  
15. 웹 브라우저를 닫습니다.  
  
16. TestBDCModel 프로젝트가 열려 있는 Visual Studio 인스턴스에서 **솔루션 탐색기**의 **BdcModel1** 노드를 연 다음 **외부 데이터 목록 생성**을 클릭합니다.  
  
17. 다른 Visual Studio 인스턴스의 코드가 이전에 `GenerateExternalDataLists_Execute` 메서드에 설정한 중단점에서 중지하는지 확인합니다.  **F5** 키를 누르거나 메뉴 모음에서 **디버깅**, **계속** 을 눌러 프로젝트에 디버깅을 계속합니다.  
  
18. Visual Studio의 실험적 인스턴스에서 **Entity1DataList** 라는 목록 인스턴스를 TestBDCModel 프로젝트에 추가하고, 목록 인스턴스에 대한 **Feature2** 라는 기능도 생성합니다.  
  
19. **F5** 키를 누르거나 메뉴 모음에서 **디버그**, **디버깅 시작** 을 눌러 TestBDCModel 프로젝트를 빌드, 배포 및 실행 합니다.  
  
     디버깅에 사용되는 SharePoint 사이트의 기본 페이지가 웹 브라우저에서 열립니다.  
  
20. 빠른 실행 영역의 **목록** 구역에서 **Entity1DataList** 목록을 클릭합니다.  
  
21. 목록에 Identifier1 및 Message 열이 있고, Identifier1 값이 0이고 Message 값이 Hello World인 하나의 항목이 포함된 것을 확인합니다.  
  
     **비즈니스 데이터 연결 모델** 프로젝트 템플릿은 이 데이터의 모든것을 제공하는 기본 BDC 모델을 생산합니다.  
  
22. 웹 브라우저를 닫습니다.  
  
## 개발 컴퓨터 정리  
 프로젝트 항목 확장의 테스트를 마쳤으면 SharePoint 사이트에서 외부 목록과 BDC 모델을 제거하고 Visual Studio에서 프로젝트 항목 확장을 제거합니다.  
  
#### SharePoint 사이트에서 외부 데이터 목록을 제거하려면  
  
1.  SharePoint 사이트의 빠른 실행 영역에서 **Entity1DataList** 목록을 선택합니다.  
  
2.  SharePoint 사이트의 리본 메뉴에서 **목록** 탭을 선택합니다.  
  
3.  **목록** 탭의 **설정** 그룹에서 **목록 설정**을 선택합니다.  
  
4.  **사용 권한 및 관리** 에서 **이 목록 삭제**를 선택한 다음 **확인** 을 선택하여 목록을 휴지통으로 보냅니다.  
  
5.  웹 브라우저를 닫습니다.  
  
#### SharePoint 사이트에서 BDC 모델을 제거하려면  
  
1.  실험 모드의 Visual Studio 인스턴스의 메뉴 모음에서 **빌드**, **제거**를 선택합니다.  
  
     Visual Studio를 통해 SharePoint 사이트에서 BDC 모델이 제거됩니다.  
  
#### Visual Studio에서 프로젝트 항목 확장을 제거하려면  
  
1.  실험 모드의 Visual Studio 인스턴스에서 **도구** 메뉴의 **확장 및 업데이트**를 선택합니다.  
  
     **확장 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장 목록에서 **External Data List Generator**을 선택한 다음 **제거** 버튼을 선택합니다.  
  
3.  나타나는 대화 상자에서 **예**를 선택하여 확장을 제거합니다.  
  
4.  **지금 다시 시작** 을 선택하여 제거를 완료합니다.  
  
5.  Visual Studio의 두 인스턴스, 즉 실험 모드의 인스턴스와 GenerateExternalDataLists 솔루션이 열려 있는 인스턴스를 모두 닫습니다.  
  
## 참고 항목  
 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)   
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  