---
title: "연습: SharePoint 프로젝트 항목 형식 확장 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: e2f39fc15d73b2019e739d7695f40cf0e3fd0940
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-extending-a-sharepoint-project-item-type"></a>연습: SharePoint 프로젝트 항목 형식 확장
  사용할 수는 **비즈니스 데이터 연결 모델** SharePoint의 BDC 비즈니스 데이터 연결 () 서비스에 대 한 모델을 만드는 프로젝트 항목입니다. 기본적으로이 프로젝트 항목을 사용 하 여 모델을 만들 때 모델의 데이터 표시 되지 않습니다 사용자에 게. 사용자가 데이터를 볼 수 있도록 SharePoint에 외부 목록도 만들어야 합니다.  
  
 이 연습에 대 한 확장명을 만듭니다는 **비즈니스 데이터 연결 모델** 프로젝트 항목입니다. 개발자는 BDC 모델에 데이터를 표시 하는 프로젝트에 외부 목록 만들기에 확장을 사용할 수 있습니다. 이 연습에서는 다음 작업을 수행합니다.  
  
-   Visual Studio 확장을 만드는 두 가지 기본 작업을 수행 합니다.  
  
    -   BDC 모델에 데이터를 표시 하는 외부 목록을 생성 합니다. 확장은 SharePoint 프로젝트 시스템에 대 한 개체 모델을 사용 하 여 목록을 정의 하 여 Elements.xml 파일을 생성 합니다. 또한 BDC 모델을 함께 배포 되도록 프로젝트에 파일을 추가 합니다.  
  
    -   바로 가기 메뉴 항목에 추가 된 **비즈니스 데이터 연결 모델** 의 프로젝트 항목 **솔루션 탐색기**합니다. 개발자는 BDC 모델에 대 한 외부 목록을 생성 하려면이 메뉴 항목 클릭 수 있습니다.  
  
-   확장 프로그램 어셈블리를 배포 하려면 VSIX Visual Studio Extension () 패키지를 빌드하 합니다.  
  
-   확장을 테스트 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료 하려면 개발 컴퓨터에 다음 구성 요소가 필요 합니다.  
  
-   Microsoft Windows, SharePoint 및 Visual Studio의 버전을 지원 합니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)] 이 연습에서는 **VSIX 프로젝트** 프로젝트 항목을 배포 하려면 VSIX 패키지를 만드는 SDK에서 서식 파일입니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구 확장](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
 다음 개념을 이해에 도움이 되지만 필수는 아니므로 연습을 완료 하는:  
  
-   BDC 서비스에서 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]합니다. 자세한 내용은 참조 [BDC 아키텍처](http://go.microsoft.com/fwlink/?LinkId=177798)합니다.  
  
-   BDC 모델에 대 한 XML 스키마입니다. 자세한 내용은 참조 [BDC 모델 인프라](http://go.microsoft.com/fwlink/?LinkId=177799)합니다.  
  
## <a name="creating-the-projects"></a>프로젝트 만들기  
 이 연습을 완료 하려면 두 프로젝트를 만들어야 합니다.  
  
-   프로젝트 항목 확장을 배포 하려면 VSIX 패키지를 만들려면 VSIX 프로젝트.  
  
-   프로젝트 항목 확장을 구현 하는 클래스 라이브러리 프로젝트.  
  
 이 연습에서는 먼저 프로젝트를 만듭니다.  
  
#### <a name="to-create-the-vsix-project"></a>VSIX 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
3.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic** 노드를 선택한 후는 **확장성** 노드.  
  
    > [!NOTE]  
    >  **확장성** 노드를 Visual Studio SDK를 설치 하는 경우에 사용할 수 있습니다. 자세한 내용은이 항목의 앞부분에 나오는 필수 구성 요소 섹션을 참조 하십시오.  
  
4.  맨 위에 있는 목록에는 **새 프로젝트** 대화 상자에서 선택 **.NET Framework 4.5**합니다.  
  
     SharePoint 도구 확장에는이 버전의.NET Framework의 기능이 필요 합니다.  
  
5.  선택 된 **VSIX 프로젝트** 템플릿.  
  
6.  에 **이름** 상자에 입력 **GenerateExternalDataLists**, 선택한 후는 **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]추가 **GenerateExternalDataLists** 프로젝트를 **솔루션 탐색기**합니다.  
  
7.  Source.extension.vsixmanifest 파일 자동으로 열리지 GenerateExternalDataLists 프로젝트의 바로 가기 메뉴를 열고 선택한 후 **열**  
  
8.  Source.extension.vsixmanifest 파일 비어 있지 않은 항목이 있는지 확인 합니다 (입력 Contoso) 작성자 필드에 대 한 파일을 저장 한 다음 닫습니다.  
  
#### <a name="to-create-the-extension-project"></a>확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **GenerateExternalDataLists** 솔루션 노드를 선택 **추가**를 선택한 후 **새프로젝트**.  
  
2.  에 **새 프로젝트 추가** 대화 상자에서 **Visual C#** 또는 **Visual Basic** 노드를 선택한 후는 **Windows** 노드.  
  
3.  대화 상자 맨 위에 있는 목록에서 선택 **.NET Framework 4.5**합니다.  
  
4.  프로젝트 템플릿 목록에서 선택 **클래스 라이브러리**합니다.  
  
5.  에 **이름** 상자에 입력 **BdcProjectItemExtension**, 선택한 후는 **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]추가 **BdcProjectItemExtension** 프로젝트를 솔루션 기본 Class1 코드 파일을 엽니다.  
  
6.  프로젝트에서 Class1 코드 파일을 삭제 합니다.  
  
## <a name="configuring-the-extension-project"></a>확장 프로젝트 구성  
 프로젝트 항목 확장을 만드는 코드를 작성 하기 전에 코드 파일 및 확장 프로젝트에 어셈블리 참조를 추가 합니다.  
  
#### <a name="to-configure-the-project"></a>프로젝트를 구성 하려면  
  
1.  BdcProjectItemExtension 프로젝트에서 다음과 같은 이름의 두 코드 파일을 추가 합니다.  
  
    -   ProjectItemExtension  
  
    -   GenerateExternalDataLists  
  
2.  BdcProjectItemExtension 프로젝트를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **참조 추가**합니다.  
  
3.  아래는 **어셈블리** 노드를 선택는 **프레임 워크** 노드와 각 다음 어셈블리에 대 한 확인란을 선택 합니다.  
  
    -   System.ComponentModel.Composition  
  
    -   WindowsBase  
  
4.  아래는 **어셈블리** 노드를 선택는 **확장** 노드를 선택한 다음 어셈블리에 대 한 다음 선택 확인란:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
5.  **확인** 단추를 선택합니다.  
  
## <a name="defining-the-project-item-extension"></a>프로젝트 항목 확장 정의  
 확장을 정의 하는 클래스를 만듭니다는 **비즈니스 데이터 연결 모델** 프로젝트 항목입니다. 클래스가 구현 하는 확장을 정의 하려면는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 인터페이스입니다. 프로젝트 항목의 기존 형식을 확장 하려는 경우이 인터페이스를 구현 합니다.  
  
#### <a name="to-define-the-project-item-extension"></a>프로젝트 항목 확장을 정의 하려면  
  
1.  다음 코드를 붙여는 ProjectItemExtension 코드 파일.  
  
    > [!NOTE]  
    >  이 코드를 추가한 후 프로젝트 컴파일 오류가 발생 갖습니다. 이러한 오류는 사라집니다 이후 단계에서 코드를 추가 합니다.  
  
     [!code-csharp[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#1](../sharepoint/codesnippet/CSharp/generateexternaldatalists/bdcprojectitemextension/projectitemextension.cs#1)]
     [!code-vb[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#1](../sharepoint/codesnippet/VisualBasic/generateexternaldatalists/bdcprojectitemextension/projectitemextension.vb#1)]  
  
## <a name="creating-the-external-data-lists"></a>외부 데이터 목록 만들기  
 추가의 부분 정의 `GenerateExternalDataListsExtension` BDC 모델의 각 엔터티에 대 한 외부 데이터 목록을 만드는 클래스입니다. 외부 데이터 목록을 만들려면이 코드 BDC 모델 파일에서 XML 데이터를 구문 분석 하 여 BDC 모델의 엔터티 데이터를 먼저 읽습니다. 그런 다음 BDC 모델을 기반으로 하며 프로젝트에이 목록 인스턴스를 추가 하 여 목록 인스턴스를 만듭니다.  
  
#### <a name="to-create-the-external-data-lists"></a>외부 데이터 목록을 만들려면  
  
1.  GenerateExternalDataLists 코드 파일에 다음 코드를 붙여 넣습니다.  
  
     [!code-vb[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#2](../sharepoint/codesnippet/VisualBasic/generateexternaldatalists/bdcprojectitemextension/generateexternaldatalists.vb#2)]
     [!code-csharp[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#2](../sharepoint/codesnippet/CSharp/generateexternaldatalists/bdcprojectitemextension/generateexternaldatalists.cs#2)]  
  
## <a name="checkpoint"></a>검사점  
 이 연습에서는 프로젝트 항목 확장에 대 한 모든 코드 프로젝트에 포함 되었습니다. 프로젝트가 오류 없이 컴파일되는지 확인 솔루션을 빌드하십시오.  
  
#### <a name="to-build-the-solution"></a>솔루션을 빌드하려면  
  
1.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
## <a name="creating-a-vsix-package-to-deploy-the-project-item-extension"></a>프로젝트 항목 확장을 배포 하려면 VSIX 패키지 만들기  
 확장을 배포 하려면 솔루션에서 VSIX 프로젝트를 사용 하 여 VSIX 패키지를 만듭니다. 첫째, VSIX 프로젝트에 포함 된 source.extension.vsixmanifest 파일을 수정 하 여 VSIX 패키지를 구성 합니다. 그런 다음 솔루션을 구축 하 여 VSIX 패키지를 만듭니다.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>구성 하 고 VSIX 패키지를 만들려면  
  
1.  **솔루션 탐색기**, GenerateExternalDataLists 프로젝트에서 source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 선택한 후 **열고**합니다.  
  
     Visual Studio 매니페스트 편집기에서 파일을 엽니다. Source.extension.vsixmanifest 파일의 기본 extension.vsixmanifest 파일에 대 한 모든 VSIX 패키지에 필요한입니다. 이 파일에 대 한 자세한 내용은 참조 [VSIX 확장 스키마 1.0 참조](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)합니다.  
  
2.  에 **제품 이름** 상자에 입력 **외부 데이터 목록 생성기**합니다.  
  
3.  에 **작성자** 상자에 입력 **Contoso**합니다.  
  
4.  에 **설명** 상자에 입력 **외부 데이터 목록을 생성 하는 데 사용할 수 있는 비즈니스 데이터 연결 모델 프로젝트 항목에 대 한 확장**합니다.  
  
5.  에 **자산** 탭 편집기의 선택은 **새로 만들기** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 나타납니다.  
  
6.  에 **형식** 목록에서 선택 **Microsoft.VisualStudio.MefComponent**합니다.  
  
    > [!NOTE]  
    >  이 값에 해당 하는 `MefComponent` extension.vsixmanifest 파일의 요소입니다. 이 요소는 VSIX 패키지의 확장 어셈블리의 이름을 지정합니다. 자세한 내용은 참조 [MEFComponent 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551)합니다.  
  
7.  에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
8.  에 **프로젝트** 목록에서 선택 **BdcProjectItemExtension**를 선택한 후는 **확인** 단추입니다.  
  
9. 메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
10. 프로젝트 컴파일 및 빌드 오류가 있는지 확인 합니다.  
  
11. GenerateExternalDataLists 프로젝트에 대 한 빌드 출력 폴더 GenerateExternalDataLists.vsix 파일을 이제 포함 되어 있는지 확인 합니다.  
  
     빌드 출력 폴더는 기본적으로는... 프로젝트 파일에 포함 된 폴더 아래 \bin\Debug 폴더입니다.  
  
## <a name="testing-the-project-item-extension"></a>테스트 프로젝트 항목 확장  
 이제 프로젝트 항목 확장을 테스트할 준비가 되었습니다. 먼저 Visual Studio의 실험적 인스턴스에서 확장 프로젝트 디버깅을 시작 합니다. 그런 다음 Visual Studio의 실험적 인스턴스에서 확장을 사용 하 여 BDC 모델에 대 한 외부 목록을 생성 합니다. 마지막으로, 예상 대로 작동 하는지 확인 하려면 SharePoint 사이트에서 외부 목록을 엽니다.  
  
#### <a name="to-start-debugging-the-extension"></a>확장 프로그램 디버깅을 시작 하려면  
  
1.  필요한 경우 관리자 자격 증명으로 Visual Studio를 다시 시작 하 고 GenerateExternalDataLists 솔루션을 엽니다.  
  
2.  BdcProjectItemExtension 프로젝트에서 ProjectItemExtension 코드 파일을 열고 다음 코드 줄에 중단점을 추가 `Initialize` 메서드.  
  
3.  다음에 코드의 첫 번째 줄에 중단점을 추가 하 고 GenerateExternalDataLists 코드 파일을 열고는 `GenerateExternalDataLists_Execute` 메서드.  
  
4.  F5 키를 선택 하 여 하거나 메뉴 모음에서 디버깅, 선택 시작 **디버그**, **디버깅 시작**합니다.  
  
     Visual Studio 데이터 목록 Generator\1.0 %UserProfile%\AppData\Local\Microsoft\VisualStudio\10.0Exp\Extensions\Contoso\External에 확장을 설치 하 고 Visual Studio의 실험적 인스턴스를 시작 합니다. Visual Studio의이 인스턴스에 있는 프로젝트 항목을 테스트 합니다.  
  
#### <a name="to-test-the-extension"></a>확장을 테스트 하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **파일**, **새로**, **프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 **템플릿** 노드를 확장 하 고는 **Visual C#** 노드를 확장 하 고는 **SharePoint** 노드를 차례로 선택 **2010**합니다.  
  
3.  대화 상자 맨 위에 있는 목록에 있는지 확인 하는 **.NET Framework 3.5** 을 선택 합니다. 에 대 한 프로젝트 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] 이 버전의.NET Framework가 필요 합니다.  
  
4.  프로젝트 템플릿 목록에서 선택 **SharePoint 2010 프로젝트**합니다.  
  
5.  에 **이름** 상자에 입력 **SharePointProjectTestBDC**, 선택한 후는 **확인** 단추입니다.  
  
6.  SharePoint 사용자 지정 마법사에서 디버깅에 사용할 선택 하려는 사이트의 URL을 입력 **팜 솔루션으로 배포**를 선택한 후는 **마침**단추입니다.  
  
7.  SharePointProjectTestBDC 프로젝트에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 항목**합니다.  
  
8.  에 **추가 NewItem-SharePointProjectTestBDC** 대화 상자, 설치 된 언어 노드를 확장 된 **SharePoint** 노드.  
  
9. 선택 된 **2010** 노드를 선택한 후는 **비즈니스 데이터 연결 모델 (팜 솔루션에만 해당)** 서식 파일입니다.  
  
10. 에 **이름** 상자에 입력 **TestBDCModel**, 선택한 후는 **추가** 단추입니다.  
  
11. Visual Studio의 다른 인스턴스에서 코드에 설정 된 중단점에서 중지 확인는 `Initialize` ProjectItemExtension 코드 파일의 메서드.  
  
12. Visual Studio의 중지 된 인스턴스를 선택는 **F5** 키 또는 메뉴 모음에서 **디버그**, **계속** 를 계속 프로젝트를 디버깅 합니다.  
  
13. Visual Studio의 실험적 인스턴스를 선택는 **F5** 키 또는 메뉴 모음에서 **디버그**, **디버깅 시작** 빌드, 배포 및 실행 된  **TestBDCModel** 프로젝트.  
  
     웹 브라우저 디버깅에 대해 지정 된 SharePoint 사이트의 기본 페이지를 엽니다.  
  
14. 확인 하는 **나열** 빠른 실행 영역에서 섹션 프로젝트의 기본 BDC 모델을 기반으로 하는 목록을 아직 포함 하지 않습니다. SharePoint 사용자 인터페이스를 사용 하 여 또는 프로젝트 항목 확장을 사용 하 여 외부 데이터 목록을 만들어야 합니다.  
  
15. 웹 브라우저를 닫습니다.  
  
16. 인스턴스의 TestBDCModel 프로젝트가 열려 있는 Visual Studio에 대 한 바로 가기 메뉴를 열고는 **TestBDCModel** 의 노드 **솔루션 탐색기**를 선택한 후 **외부 데이터 생성 목록**합니다.  
  
17. Visual Studio의 다른 인스턴스에서 코드에 설정 된 중단점에서 중지 확인는 `GenerateExternalDataLists_Execute` 메서드. 선택의 **F5** 키 또는 메뉴 모음에서 **디버그**, **계속** 를 계속 프로젝트를 디버깅 합니다.  
  
18. 명명 된 목록 인스턴스를 추가 하는 Visual Studio의 실험적 인스턴스에서 **Entity1DataList** 는 TestBDCModel 프로젝트 및 인스턴스 생성 라고 하는 기능 **Feature2** 목록에 대 한 인스턴스입니다.  
  
19. 선택 된 **F5** 키 또는 메뉴 모음에서 **디버그**, **디버깅 시작** 빌드, 배포 및 TestBDCModel 프로젝트를 실행 합니다.  
  
     웹 브라우저 디버깅에 사용 되는 SharePoint 사이트의 기본 페이지를 엽니다.  
  
20. 에 **나열** 섹션의 빠른 실행 영역을 선택는 **Entity1DataList** 목록입니다.  
  
21. Identifier1 값이 0와의 Hello World 메시지 값을 가진 하나의 항목 외에도 Identifier1 및 메시지, 명명 된 열 목록에 포함 되어 있는지 확인 하십시오.  
  
     **비즈니스 데이터 연결 모델** 프로젝트 템플릿은 모든이 데이터를 제공 하는 기본 BDC 모델을 생성 합니다.  
  
22. 웹 브라우저를 닫습니다.  
  
## <a name="cleaning-up-the-development-computer"></a>개발 컴퓨터를 정리합니다.  
 프로젝트 항목 확장 테스트를 마친 후 SharePoint 사이트에서 외부 목록 및 BDC 모델을 제거 하 고 Visual Studio에서 프로젝트 항목 확장을 제거 합니다.  
  
#### <a name="to-remove-the-external-data-list-from-the-sharepoint-site"></a>SharePoint 사이트에서 외부 데이터 목록을 제거 하려면  
  
1.  SharePoint 사이트의 빠른 실행 영역에서 선택 된 **Entity1DataList** 목록입니다.  
  
2.  SharePoint 사이트에 대 한 리본 메뉴에서 선택 된 **목록** 탭 합니다.  
  
3.  에 **목록** 탭에 **설정** 그룹에서 선택 **목록 설정**합니다.  
  
4.  아래 **사용 권한 및 관리**, 선택 **이 목록을 삭제**를 선택한 후 **확인** 을 확인 하 여 휴지통을 활성화 하는 목록을 보냅니다.  
  
5.  웹 브라우저를 닫습니다.  
  
#### <a name="to-remove-the-bdc-model-from-the-sharepoint-site"></a>SharePoint 사이트에서 BDC 모델을 제거 하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **빌드**, **Retract**합니다.  
  
     Visual Studio는 SharePoint 사이트에서 BDC 모델을 제거합니다.  
  
#### <a name="to-remove-the-project-item-extension-from-visual-studio"></a>Visual Studio에서 프로젝트 항목 확장을 제거 하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **도구**, **확장명 및 업데이트**합니다.  
  
     **확장명 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장의 목록에서 선택 **외부 데이터 목록 생성기**를 선택한 후는 **제거** 단추입니다.  
  
3.  표시 되는 대화 상자에서 선택 **예** 확장을 제거 하도록 확인할 수 있습니다.  
  
4.  선택 **지금 다시 시작** 제거를 완료 합니다.  
  
5.  Visual Studio (실험적 인스턴스 및 GenerateExternalDataLists 솔루션 열릴 인스턴스)의 두 인스턴스를 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 시스템 확장](../sharepoint/extending-the-sharepoint-project-system.md)   
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  