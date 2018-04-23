---
title: 명령줄에서 ClickOnce 응용 프로그램을 구축 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, from command line
- publishing
- publishing, ClickOnce
ms.assetid: d9bc6212-c584-4f72-88c9-9a4b998c555e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4488f32b135d766f494bc94946fbf77d42eb1e95
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="building-clickonce-applications-from-the-command-line"></a>명령줄에서 ClickOnce 응용 프로그램 빌드
[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], 통합된 개발 환경 (IDE)에서 만들어진 경우에 명령줄에서 프로젝트를 빌드할 수 있습니다. 사용 하 여 만든 프로젝트를 다시 작성할 수는 실제로 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 만 있는 다른 컴퓨터에는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 설치 합니다. 이 자동화 된 프로세스를 사용 하 여 빌드를 재현할 수 있습니다, 그리고 예를 들어 중앙의 빌드 랩 또는 사용 하 여 고급 스크립팅 기술을 자체 프로젝트의 범위를 벗어납니다.  
  
## <a name="using-msbuild-to-reproduce-clickonce-application-deployments"></a>ClickOnce 응용 프로그램 배포를 재현 하는 MSBuild를 사용 하 여  
 프로젝트 빌드를 만들 MSBuild 시스템은 명령줄에서 msbuild /target:publish를 호출할 때 인지는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 게시 폴더에서 응용 프로그램입니다. 선택 하면 같습니다는 **게시** IDE에 명령 합니다.  
  
 이 명령은 Visual Studio 명령 프롬프트 환경에 포함 된 경로에 있는 msbuild.exe를 실행 합니다.  
  
 "대상"는 MSBuild에 명령을 처리 하는 방법을 나타냅니다. 주요 대상은 "빌드" 대상과 "게시" 대상입니다. 빌드 대상이 해당 빌드를 선택 하는 IDE에서 명령 (또는 F5 키를 눌러). 프로젝트를 빌드 하려는 입력 하 여 얻을 수 `msbuild`합니다. 이 명령은 작동 build 대상에 의해 생성 된 모든 프로젝트에 대 한 기본 대상 이므로 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]합니다. 즉, 빌드 대상을 지정 하려면 명시적으로 필요 하지 않습니다. 따라서 입력 `msbuild` 은 입력으로 동일한 작업 `msbuild /target:build`합니다.  
  
 `/target:publish` 명령은 게시 대상을 호출 하기 위해 MSBuild에 게 알려줍니다. 게시 대상이 build 대상에 따라 달라 집니다. 이 게시 작업에서 작성 작업의 상위 집합 임을 의미 합니다. 예를 들어 Visual Basic 또는 C# 소스 파일 중 하나를 변경한 경우 게시 작업에서 해당 어셈블리가 자동으로 다시 빌드됩니다.  
  
 전체 생성에 대 한 내용은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 만들려는 Mage.exe 명령줄 도구를 사용 하 여 배포 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트를 참조 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)합니다.  
  
## <a name="creating-and-building-a-basic-clickonce-application-using-msbuild"></a>만들기 및 MSBuild를 사용 하 여 기본 ClickOnce 응용 프로그램 작성  
  
#### <a name="to-create-and-publish-a-clickonce-project"></a>만들어 ClickOnce 프로젝트를 게시 하려면  
  
1.  클릭 **새 프로젝트** 에서 **파일** 메뉴. **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  선택 **Windows 응용 프로그램** 하 고 이름을 `CmdLineDemo`합니다.  
  
3.  **빌드** 메뉴를 클릭 하 여는 **게시** 명령입니다.  
  
     이 단계를 수행 하면 프로젝트가 생성 하기 위해 제대로 구성 되는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 배포.  
  
     게시 마법사가 나타납니다.  
  
4.  게시 마법사에서 **마침**합니다.  
  
     Visual Studio는 생성 하 고 Publish.htm 이라는 기본 웹 페이지를 표시 합니다.  
  
5.  프로젝트를 저장 하 고 저장 된 폴더 위치를 기록 합니다.  
  
 위의 단계를 만듭니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 처음으로 게시 된 프로젝트입니다. 이제 IDE 외부에서 빌드를 재현할 수 있습니다.  
  
#### <a name="to-reproduce-the-build-from-the-command-line"></a>명령줄에서 빌드를 재현 하려면  
  
1.  [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]을 종료합니다.  
  
2.  Windows에서 **시작** 메뉴를 클릭 **모든 프로그램**, 다음 **Microsoft Visual Studio**, 다음 **Visual Studio Tools**, 다음 **Visual Studio 명령 프롬프트**합니다. 이 현재 사용자의 루트 폴더에 명령 프롬프트를 열어야 합니다.  
  
3.  에 **Visual Studio 명령 프롬프트**, 현재 디렉터리 위에 빌드한 프로젝트의 위치를 변경 합니다. 예를 들어 입력 `chdir My Documents\Visual Studio\Projects\CmdLineDemo`합니다.  
  
4.  로 생성 된 기존 파일을 제거 하려면 "를 만들고 게시 한 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 프로젝트" 유형 `rmdir /s publish`합니다.  
  
     이 단계는 옵션 이지만 새 파일 모두에 의해 생성 된 명령줄 빌드 되도록 합니다.  
  
5.  `msbuild /target:publish`를 입력합니다.  
  
 위의 단계는 전체 생성 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] p 프로젝트의 하위 폴더에 응용 프로그램 배포**ublish**합니다. CmdLineDemo.application는는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트 합니다. 폴더 CmdLineDemo_1.0.0.0 CmdLineDemo.exe 및 CmdLineDemo.exe.manifest의 파일이 포함 된 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트 합니다. Setup.exe는 기본적으로 설치 하도록 구성 된 부트스트래퍼는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다. DotNetFX 폴더에 대 한 재배포 가능 패키지에 포함 된 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다. 웹을 통해 또는 UNC 또는 CD/DVD를 통해 응용 프로그램을 배포 하는 데 필요한 파일의 전체 집합입니다.  
  
## <a name="publishing-properties"></a>게시 속성  
 위의 절차에서 응용 프로그램을 게시할 때 게시 마법사가 다음과 같은 속성이 프로젝트 파일에 삽입 됩니다. 이러한 속성에 직접 영향을 방법을 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램의 생성 합니다.  
  
 CmdLineDemo.vbproj에서 / CmdLineDemo.csproj:  
  
```  
<AssemblyOriginatorKeyFile>WindowsApplication3.snk</AssemblyOriginatorKeyFile>  
<GenerateManifests>true</GenerateManifests>  
<TargetZone>LocalIntranet</TargetZone>  
<PublisherName>Microsoft</PublisherName>  
<ProductName>CmdLineDemo</ProductName>  
<PublishUrl>http://localhost/CmdLineDemo</PublishUrl>  
<Install>true</Install>  
<ApplicationVersion>1.0.0.*</ApplicationVersion>  
<ApplicationRevision>1</ApplicationRevision>  
<UpdateEnabled>true</UpdateEnabled>  
<UpdateRequired>false</UpdateRequired>  
<UpdateMode>Foreground</UpdateMode>  
<UpdateInterval>7</UpdateInterval>  
<UpdateIntervalUnits>Days</UpdateIntervalUnits>  
<UpdateUrlEnabled>false</UpdateUrlEnabled>  
<IsWebBootstrapper>true</IsWebBootstrapper>  
<BootstrapperEnabled>true</BootstrapperEnabled>  
```  
  
 프로젝트 파일 자체를 변경 하지 않고 명령줄에서 이러한 속성을 재정의할 수 있습니다. 예를 들어 다음 작성 됩니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 부트스트래퍼 없이 응용 프로그램 배포:  
  
```  
msbuild /target:publish /property:BootstrapperEnabled=false  
```  
  
 게시 속성은에서 제어 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 에서 **게시**, **보안**, 및 **서명** 의 속성 페이지는 **프로젝트 디자이너** . 다음은 응용 프로그램 디자이너의 다양 한 속성 페이지에 설정 되어 각 방법의 표시와 함께 게시 속성에 대 한 설명을입니다.  
  
-   `AssemblyOriginatorKeyFile` 서명에 사용 되는 키 파일을 결정 하면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트 합니다. 어셈블리에 강력한 이름을 지정 하려면이 동일한 키를 사용할 수도 있습니다. 이 속성에 **서명** 의 페이지는 **프로젝트 디자이너**합니다.  
  
 에 다음 속성이 설정 된는 **보안** 페이지:  
  
-   **ClickOnce 보안 설정 사용** 결정 여부 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트를 생성 합니다. 프로젝트 처음 만들어질 때 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 기본적으로 해제 되어 매니페스트를 생성 합니다. 마법사는이 플래그를 처음으로 게시 하는 경우 자동으로 바뀝니다.  
  
-   **TargetZone** 에 공개 될 신뢰 수준을 결정 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트 합니다. 가능한 값은 "Internet", "LocalIntranet" 및 "Custom"입니다. 인터넷 및 LocalIntranet 기본 권한 집합을 데이터로 내보낼 수를 기준으로 하면 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트 합니다. LocalIntranet는 기본 템플릿이 고 기본적으로 완전 신뢰를 의미 합니다. 사용자 지정 하는 기본 app.manifest 파일에 명시적으로 지정 된 사용 권한만을 지정 데이터로 내보낼 수는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트 합니다. App.manifest 파일은 부분 신뢰 정보 정의 포함 된 매니페스트 파일. 사용 권한을 구성 하는 경우 프로젝트에 자동으로 추가 하는 숨겨진 파일의 **보안** 페이지.  
  
 에 다음 속성이 설정 된는 **게시** 페이지:  
  
-   `PublishUrl` IDE에서에 응용 프로그램이 게시 될 위치가입니다. 에 삽입 됩니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 모두 없으면 응용 프로그램 매니페스트는 `InstallUrl` 또는 `UpdateUrl` 속성을 지정 합니다.  
  
-   `ApplicationVersion` 버전을 지정 된 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다. 버전 4 자리 수입니다. 마지막 자릿수가 양수인 경우는 "*"를 하면 `ApplicationRevision` 빌드 시에는 매니페스트에 삽입 되는 값을 대체 합니다.  
  
-   `ApplicationRevision` 수정 버전을 지정 합니다. 이것이 IDE에 게시할 때마다 증가 하는 정수입니다. 에 대 한 자동으로 증가 하지는 명령줄에서 수행한 빌드합니다.  
  
-   `Install` 응용 프로그램이 설치 된 응용 프로그램 또는 웹에서 실행 응용 프로그램 인지 확인 합니다.  
  
-   `InstallUrl` 사용자가 설치 하는 응용 프로그램을 위치가 됩니다 (표시 되지 않음). Setup.exe 부트스트래퍼에이 값 구워진를 지정 하는 경우는 `IsWebBootstrapper` 속성을 사용할 수 있습니다. 매니페스트 경우 응용 프로그램에 삽입 된 `UpdateUrl` 지정 되지 않았습니다.  
  
-   `SupportUrl` (표시 되지 않음)가 연결 된 위치에는 **프로그램 추가/제거** 설치 된 응용 프로그램에 대 한 대화 상자.  
  
 다음 속성에서 설정 됩니다는 **응용 프로그램 업데이트** 에서 액세스 되는 대화 상자는 **게시** 페이지.  
  
-   `UpdateEnabled` 응용 프로그램 업데이트를 확인 해야 하는지 여부를 나타냅니다.  
  
-   `UpdateMode` 포그라운드 업데이트 또는 백그라운드 업데이트를 지정합니다.  
  
-   `UpdateInterval` 응용 프로그램 업데이트를 확인 하는 빈도 지정 합니다.  
  
-   `UpdateIntervalUnits` 지정 여부는 `UpdateInterval` 값은 시간, 일 또는 주 단위로 합니다.  
  
-   `UpdateUrl` 응용 프로그램 업데이트를 받을 위치를입니다 (표시 되지 않음). 를 지정 하는 경우이 값은 응용 프로그램 매니페스트에 삽입 됩니다.  
  
-   다음 속성에서 설정 됩니다는 **게시 옵션** 에서 액세스 되는 대화 상자는 **게시** 페이지.  
  
-   `PublisherName` 설치 또는 응용 프로그램을 실행할 때 표시 되는 프롬프트에 표시 된 게시자의 이름을 지정 합니다. 설치 된 응용 프로그램의 경우에 사용 됩니다에 폴더 이름을 지정 하는 **시작** 메뉴.  
  
-   `ProductName` 설치 또는 응용 프로그램을 실행할 때 표시 되는 프롬프트에 표시 되는 제품의 이름을 지정 합니다. 설치 된 응용 프로그램의 경우에 사용 됩니다에 바로 가기 이름을 지정 하는 **시작** 메뉴.  
  
-   다음 속성에서 설정 됩니다는 **필수 구성 요소** 에서 액세스 되는 대화 상자는 **게시** 페이지.  
  
-   `BootstrapperEnabled` setup.exe 부트스트래퍼를 생성 여부를 결정 합니다.  
  
-   `IsWebBootstrapper` setup.exe 부트스트래퍼 웹을 통해 또는 디스크 기반 모드에서 작동 하는지 여부를 결정 합니다.  
  
## <a name="installurl-supporturl-publishurl-and-updateurl"></a>InstallURL, SupportUrl, PublishURL, 및 UpdateURL  
 다음 표에서 ClickOnce 배포를 위한 4 개의 URL 옵션을 보여 줍니다.  
  
|URL 옵션|설명|  
|----------------|-----------------|  
|`PublishURL`|ClickOnce 응용 프로그램 웹 사이트에 게시 하는 경우 필요 합니다.|  
|`InstallURL`|선택 사항입니다. 설치 사이트과 다른 경우이 URL 옵션을 설정 합니다.는 `PublishURL`합니다. 예를 들어 설정할 수 있습니다는 `PublishURL` 을 설정 하 고는 FTP 경로 `InstallURL` 웹 URL로 합니다.|  
|`SupportURL`|선택 사항입니다. 지원 사이트과 다른 경우이 URL 옵션을 설정 합니다.는 `PublishURL`합니다. 예를 들어 설정할 수 있습니다는 `SupportURL` 회사의 고객 지원 웹 사이트입니다.|  
|`UpdateURL`|선택 사항입니다. 업데이트 위치과 다른 경우이 URL 옵션을 설정 합니다.는 `InstallURL`합니다. 예를 들어 설정할 수 있습니다는 `PublishURL` 을 설정 하 고는 FTP 경로 `UpdateURL` 웹 URL로 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.Build.Tasks.GenerateBootstrapper>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>   
 <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest>   
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)