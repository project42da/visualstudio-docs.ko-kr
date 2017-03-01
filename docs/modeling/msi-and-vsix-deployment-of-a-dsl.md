---
title: "MSI 및 VSIX 배포 하는 DSL의 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ce16f06-1978-4e19-8cdc-441ee65a3fb2
caps.latest.revision: 2
author: alancameronwills
ms.author: awills
manager: douge
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: beb505dca6f5b52046ca87e854260f4b222079c8
ms.lasthandoff: 02/22/2017

---
# <a name="msi-and-vsix-deployment-of-a-dsl"></a>DSL의 MSI 및 VSIX 배포
도메인별 언어 사용자 컴퓨터 또는 다른 컴퓨터에 설치할 수 있습니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]대상 컴퓨터에 이미 설치 되어 있어야 합니다.  
  
##  <a name="a-namewhicha-choosing-between-vsix-and-msi-deployment"></a><a name="which"></a>VSIX 및 MSI 배포 선택  
 도메인별 언어를 배포 하는 방법은 두 가지가 있습니다.  
  
|메서드|이점|  
|------------|--------------|  
|VSX ([!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 확장)|배포 하기 아주 간단: 복사 하 고 실행의 **.vsix** DslPackage 프로젝트에서 파일.<br /><br /> 자세한 내용은 참조 [를 설치 하 고는 VSX를 사용 하 여 DSL 제거](#Installing)합니다.|  
|MSI (설치 관리자 파일)|-을 열도록 허용 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] DSL 파일을 두 번 클릭 합니다.<br />-대상 컴퓨터에서 DSL 파일 형식과 아이콘을 연결합니다.<br />-DSL 파일 형식과 XSD (XML 스키마)에 연결합니다. 파일에 로드 되 면이 경고를 방지 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.<br /><br /> MSI를 만들려면 솔루션에 설치 프로젝트를 추가 해야 합니다.<br /><br /> 자세한 내용은 참조 [MSI 파일을 사용 하 여 DSL을 배포](#msi)합니다.|  
  
##  <a name="a-nameinstallinga-installing-and-uninstalling-a-dsl-by-using-the-vsx"></a><a name="Installing"></a>설치 하 고는 VSX를 사용 하 여 DSL을 제거 합니다.  
 사용자가 내에서 DSL 파일을 열 수 DSL이이 방법으로 설치 되 면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 이지만 Windows 탐색기에서 파일을 열 수 없습니다.  
  
#### <a name="to-install-a-dsl-by-using-the-vsx"></a>VSX를 사용 하 여 DSL을 설치 하려면  
  
1.  사용자의 컴퓨터에는 **.vsix** DSL 패키지 프로젝트에서 만든 파일입니다.  
  
    1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **DslPackage** 프로젝트를 마우스 클릭 한 다음 **Windows 탐색기에서 폴더 열기**합니다.  
  
    2.  Locate the file **bin\\\*\\***YourProject***. DslPackage.vsix**  
  
2.  복사는 **.vsix** DSL을 설치 하려는 대상 컴퓨터에는 파일입니다. 이 컴퓨터는 사용 중인 컴퓨터이거나 다른 컴퓨터일 수 있습니다.  
  
    -   대상 컴퓨터의 버전 중 하나가 있어야 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 런타임에 Dsl을 지 원하는 합니다. 자세한 내용은 참조 [시각화 / / 모델링 SDK에 대 한 Visual Studio 버전 지원](../modeling/supported-visual-studio-editions-for-visualization-amp-modeling-sdk.md)합니다.  
  
    -   대상 컴퓨터의 버전 중 하나가 있어야 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 에 지정 된 **DslPackage\source.extensions.manifest**합니다.  
  
3.  대상 컴퓨터에서 두 번 클릭 하 여 **.vsix** 파일입니다.  
  
     **Visual Studio 확장 설치 관리자** 에서 확장을 열고 설치합니다.  
  
4.  
          [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]를 시작하거나 다시 시작합니다.  
  
5.  DSL을 테스트 하려면 사용 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] DSL에 대해 정의 된 확장명을 가진 새 파일을 만듭니다.  
  
#### <a name="to-uninstall-a-dsl-that-was-installed-by-using-vsx"></a>VSX를 사용 하 여 설치 된 DSL을 제거 하려면  
  
1.  에 **도구** 메뉴를 클릭 하 여 **확장 관리자**합니다.  
  
2.  **설치된 확장**을 확장합니다.  
  
3.  DSL 정의 되어 있는 확장 하 고 클릭 한 다음 선택 **제거**합니다.  
  
 드물게 결함이 있는 확장은 로드되지 않고 오류 창에 보고서를 생성하지만 확장 관리자에 나타나지 않습니다. 이 경우 다음 위치에서 파일을 삭제하여 확장을 제거할 수 있습니다.  
  
 *LocalAppData* **\Microsoft\VisualStudio\10.0\Extensions**  
  
##  <a name="a-namemsia-deploying-a-dsl-in-an-msi"></a><a name="msi"></a>DSL에서 MSI 배포합니다.  
 DSL에 대 한 MSI (Windows Installer) 파일을 정의 하 여 사용자가 Windows 탐색기에서 DSL 파일을 열 수를 허용할 수 있습니다. 파일 이름 확장명이 아이콘과 간단한 설명을 연결할 수 있습니다. 또한 MSI DSL 파일 유효성을 검사 하는 데 사용할 수 있는 XSD를 설치할 수 있습니다. 원할 경우에 동시에 설치 될 MSI로 다른 구성 요소를 추가할 수 있습니다.  
  
 MSI 파일 및 다른 배포 옵션에 대 한 자세한 내용은 참조 [응용 프로그램 배포, 서비스 및 구성 요소](../deployment/deploying-applications-services-and-components.md)합니다.  
  
 설치 프로젝트를 추가 하면 MSI를 작성 하려면 프로그램 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션입니다. 설치 프로젝트를 만드는 방법을 가장 쉬운 방법은에서 다운로드할 수 있는 CreateMsiSetupProject.tt 서식 파일을 사용 하는 것은 [VMSDK 사이트](http://go.microsoft.com/fwlink/?LinkID=186128)합니다.  
  
#### <a name="to-deploy-a-dsl-in-an-msi"></a>MSI에 DSL을 배포 하려면  
  
1.  설정 `InstalledByMsi` 확장 매니페스트에서 합니다. 그러면는 설치 하 고 MSI가 제외 하 고 제거 되는 VSX를 않습니다. 이 MSI에서 다른 구성 요소를 포함 하는 경우 중요 합니다.  
  
    1.  DslPackage\source.extension.tt 열기  
  
    2.  앞에 다음 줄을 삽입 `<SupportedProducts>`:  
  
        ```  
        <InstalledByMsi>true</InstalledByMsi>  
        ```  
  
2.  만들거나 Windows 탐색기에서 DSL에 나타내는 아이콘을 편집 합니다. 예를 들어 편집 **DslPackage\Resources\File.ico**  
  
3.  DSL의 다음 특성 정확한 지 확인 합니다.  
  
    -   DSL 탐색기에서 루트 노드를 클릭 하 고 속성 창에서 검토 합니다.  
  
        -   설명  
  
        -   버전  
  
    -   클릭 하 고 **편집기** 노드 속성 창에서 클릭 하 고 **아이콘**합니다. 에 있는 아이콘 파일을 참조 하려면 값을 설정 **DslPackage\Resources**와 같은 **File.ico**  
  
    -   에 **빌드** 메뉴, 열기 **Configuration Manager**, 등을 빌드 하려는 구성을 선택 하 고 **릴리스** 또는 **디버그**합니다.  
  
4.  로 이동 [Visualization and Modeling SDK 홈 페이지](http://go.microsoft.com/fwlink/?LinkID=186128), 및에서 **다운로드** 탭, 다운로드 **CreateMsiSetupProject.tt**합니다.  
  
5.  추가 **CreateMsiSetupProject.tt** Dsl 프로젝트에 있습니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]라는 파일이 만들어집니다 **CreateMsiSetupProject.vdproj**합니다.  
  
6.  Windows 탐색기에서 Dsl 복사\\*.vdproj 새 폴더에 라는 설치 합니다.  
  
     (원하는 경우 이제에서 제외할 수 있습니다 CreateMsiSetupProject.tt을 Dsl 프로젝트입니다.)  
  
7.  **솔루션 탐색기**, 추가 **설치\\\*.vdproj** 으로 기존 프로젝트입니다.  
  
8.  에 **프로젝트** 메뉴를 클릭 하 여 **프로젝트 종속성**합니다.  
  
     에 **프로젝트 종속성** 대화 상자에서 설치 프로젝트를 선택 합니다.  
  
     옆의 상자 선택 **DslPackage**합니다.  
  
9. 솔루션을 다시 빌드합니다.  
  
10. Windows 탐색기에서 설치 프로젝트에서 빌드된 MSI 파일을 찾습니다.  
  
     DSL을 설치 하려는 컴퓨터에 MSI 파일을 복사 합니다. MSI 파일을 두 번 클릭 합니다. 설치 관리자를 실행합니다.  
  
11. 대상 컴퓨터에서 DSL의 파일 확장명을 가진 새 파일을 만듭니다. 확인 합니다.  
  
    -   Windows 탐색기 목록 보기에서 파일 아이콘 및 정의 된 설명으로 표시 됩니다.  
  
    -   파일을 두 번 클릭 하면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 시작 되 고 DSL 편집기에서 DSL 파일을 엽니다.  
  
 원하는 경우 텍스트 템플릿을 사용 하는 대신 수동으로 설치 프로젝트를 만들 수 있습니다. 이 절차를 포함 하는 연습의 5 장 참조는 [시각화 및 모델링 SDK 랩](http://go.microsoft.com/fwlink/?LinkId=208878)합니다.  
  
#### <a name="to-uninstall-a-dsl-that-was-installed-from-an-msi"></a>MSI에서 설치 된 DSL을 제거 하려면  
  
1.  Windows에서 열고는 **프로그램 및 기능** 제어판.  
  
2.  DSL을 제거 합니다.  
  
3.  Visual Studio를 다시 시작합니다.
