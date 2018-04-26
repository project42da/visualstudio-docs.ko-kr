---
title: DSL의 MSI 및 VSIX 배포
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: ccd26814b8a6f06f896c661f2ca9eddb0de8a90d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="msi-and-vsix-deployment-of-a-dsl"></a>DSL의 MSI 및 VSIX 배포
도메인 특정 언어 또는 다른 컴퓨터 사용자의 컴퓨터에 설치할 수 있습니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 대상 컴퓨터에 이미 설치 되어 있어야 합니다.

##  <a name="which"></a> VSIX 및 MSI 배포 중에서 선택
 도메인 특정 언어를 배포 하는 방법은 두 가지가 있습니다.

|메서드|이점|
|------------|--------------|
|VSX ([!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 확장)|배포 하기 아주 간단: 복사를 실행 하 고는 **.vsix** DslPackage 프로젝트에서 파일입니다.<br /><br /> 자세한 내용은 참조 [설치 및는 VSX를 사용 하 여 DSL 제거](#Installing)합니다.|
|MSI (설치 관리자 파일)|-을 열도록 허용 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] DSL 파일을 두 번 클릭 합니다.<br />-아이콘 대상 컴퓨터에서 DSL 파일 형식과 연결합니다.<br />-DSL 파일 형식과 XSD (XML 스키마)를 연결합니다. 이렇게 하면 경고에 파일을 로드할 때 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.<br /><br /> MSI를 만들려면 솔루션에 설치 프로젝트를 추가 해야 합니다.<br /><br /> 자세한 내용은 참조 [MSI 파일을 사용 하 여 DSL 배포](#msi)합니다.|

##  <a name="Installing"></a> 설치 하 고는 VSX를 사용 하 여 DSL 제거
 사용자가 내에서 DSL 파일을 열 수 DSL이이 방법으로 설치 되 면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 있지만 Windows 탐색기에서 파일을 열 수 없습니다.

#### <a name="to-install-a-dsl-by-using-the-vsx"></a>DSL의 VSX를 사용 하 여 설치 하려면

1.  컴퓨터를 찾습니다는 **.vsix** DSL 패키지 프로젝트에서 만든 파일입니다.

    1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **DslPackage** 프로젝트를 마우스 클릭 **Windows 탐색기에서 폴더 열기**합니다.

    2.  파일을 찾습니다 **bin\\\*\\***YourProject***합니다. DslPackage.vsix**

2.  복사는 **.vsix** DSL를 설치 하려는 대상 컴퓨터에는 파일입니다. 이 컴퓨터는 사용 중인 컴퓨터이거나 다른 컴퓨터일 수 있습니다.

    -   대상 컴퓨터의 버전 중 하나가 있어야 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 런타임 시 Dsl을 지 원하는 합니다. 자세한 내용은 참조 [시각화 및 모델링 SDK에 대 한 Visual Studio 버전 지원](../modeling/supported-visual-studio-editions-for-visualization-amp-modeling-sdk.md)합니다.

    -   대상 컴퓨터의 버전 중 하나가 있어야 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 에 지정 된 **DslPackage\source.extensions.manifest**합니다.

3.  대상 컴퓨터에 두 번 클릭 하 여 **.vsix** 파일입니다.

     **Visual Studio 확장 설치 관리자** 에서 확장을 열고 설치합니다.

4.  [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]를 시작하거나 다시 시작합니다.

5.  DSL을 테스트 하려면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] DSL에 대해 정의 된 확장명을 가진 새 파일을 만듭니다.

#### <a name="to-uninstall-a-dsl-that-was-installed-by-using-vsx"></a>VSX를 사용 하 여 설치 된 하는 DSL을 제거 하려면

1.  에 **도구** 메뉴를 클릭 하 여 **확장 관리자**합니다.

2.  **설치된 확장**을 확장합니다.

3.  DSL 정의 되어 있는 확장 하 고 클릭 한 다음 선택 **제거**합니다.

 드물게 결함이 있는 확장은 로드되지 않고 오류 창에 보고서를 생성하지만 확장 관리자에 나타나지 않습니다. 이 경우 다음 위치에서 파일을 삭제하여 확장을 제거할 수 있습니다.

 *LocalAppData* **\Microsoft\VisualStudio\10.0\Extensions**

##  <a name="msi"></a> MSI 사용 하는 DSL 배포
 DSL에 대 한 MSI (Windows Installer) 파일을 정의 하 여 사용자가을 Windows 탐색기에서 DSL 파일을 열 수 있습니다. 아이콘 및 간단한 설명 파일 이름 확장명으로 연결할 수도 있습니다. 또한 MSI DSL 파일 유효성을 검사 하는 데 사용할 수 있는 XSD를 설치할 수 있습니다. 원하는 경우에 동시에 설치할 수 있는 MSI로 다른 구성 요소를 추가할 수 있습니다.

 MSI 파일 및 기타 배포 옵션에 대 한 자세한 내용은 참조 [응용 프로그램 배포, 서비스 및 구성 요소](../deployment/deploying-applications-services-and-components.md)합니다.

 설치 프로젝트를 추가 하는 MSI를 작성 하려면 프로그램 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션입니다. 설치 프로젝트를 만드는 가장 쉬운 방법에서 다운로드할 수 있는 CreateMsiSetupProject.tt 템플릿을 사용 하는 것은 [VMSDK 사이트](http://go.microsoft.com/fwlink/?LinkID=186128)합니다.

#### <a name="to-deploy-a-dsl-in-an-msi"></a>MSI 사용 하는 DSL을 배포 하려면

1.  설정 `InstalledByMsi` 확장 매니페스트에 합니다. 이렇게 하면 않습니다는 VSX를 없도록 설치 및 제외 하 고 MSI에서 제거 됩니다. 다른 구성 요소는 MSI에 포함할 경우에 유용 합니다.

    1.  Open DslPackage\source.extension.tt

    2.  앞에 다음 행을 삽입 `<SupportedProducts>`:

        ```
        <InstalledByMsi>true</InstalledByMsi>
        ```

2.  만들거나 Windows 탐색기에서 DSL를 나타내는 아이콘을 편집 합니다. 예를 들어 편집 **DslPackage\Resources\File.ico**

3.  DSL의 다음 특성 정확한 지 확인 합니다.

    -   DSL 탐색기에서 루트 노드를 클릭 하 고 속성 창에서 검토:

        -   설명

        -   버전

    -   클릭는 **편집기** 노드 속성 창에서 클릭 하 고 **아이콘**합니다. 아이콘 파일을 참조 하도록 값을 설정할 **DslPackage\Resources**와 같은 **File.ico**

    -   에 **빌드** 메뉴를 열고 **Configuration Manager**, 등 빌드 구성을 선택 하 고 **릴리스** 또는 **디버그** .

4.  로 이동 [Visualization and Modeling SDK 홈 페이지](http://go.microsoft.com/fwlink/?LinkID=186128), 들어오고는 **다운로드** 탭, 다운로드 **CreateMsiSetupProject.tt**합니다.

5.  추가 **CreateMsiSetupProject.tt** Dsl 프로젝트에 있습니다.

     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 명명 된 파일을 만들 **CreateMsiSetupProject.vdproj**합니다.

6.  Windows 탐색기에서 복사 Dsl\\새 폴더로 *.vdproj 라는 설치 합니다.

     (원하는 경우 이제에서 제외할 수 있습니다 CreateMsiSetupProject.tt을 Dsl 프로젝트입니다.)

7.  **솔루션 탐색기**, 추가 **설치\\\*.vdproj** 기존 프로젝트로 합니다.

8.  에 **프로젝트** 메뉴를 클릭 하 여 **프로젝트 종속성**합니다.

     에 **프로젝트 종속성** 대화 상자, 설치 프로젝트를 선택 합니다.

     상자 옆에 선택 **DslPackage**합니다.

9. 솔루션을 다시 빌드합니다.

10. Windows 탐색기에서 설치 프로젝트에서 빌드된 MSI 파일을 찾습니다.

     DSL를 설치 하려는 컴퓨터에 MSI 파일을 복사 합니다. MSI 파일을 두 번 클릭 합니다. 설치 관리자를 실행합니다.

11. 대상 컴퓨터에서 DSL의 파일 확장명을 가진 새 파일을 만듭니다. 확인 합니다.

    -   Windows 탐색기 목록 뷰에서 파일 아이콘 및 정의 설명을 함께 나타납니다.

    -   파일을 두 번 클릭 하면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 시작 되 고 DSL 편집기에서 DSL 파일을 엽니다.

 원하는 경우 텍스트 템플릿을 사용 하 여 대신 설치 프로젝트를 수동으로 만들 수 있습니다. 이 절차를 포함 하는 연습의 5 장 참조는 [시각화 및 모델링 SDK 랩](http://go.microsoft.com/fwlink/?LinkId=208878)합니다.

#### <a name="to-uninstall-a-dsl-that-was-installed-from-an-msi"></a>MSI에서 설치 된 하는 DSL을 제거 하려면

1.  Windows에서 열고는 **프로그램 및 기능** 제어판 합니다.

2.  DSL를 제거 합니다.

3.  Visual Studio를 다시 시작합니다.