---
title: "명령줄에서 ClickOnce 응용 프로그램 빌드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포, 명령줄"
  - "게시"
  - "게시, ClickOnce"
ms.assetid: d9bc6212-c584-4f72-88c9-9a4b998c555e
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 23
---
# 명령줄에서 ClickOnce 응용 프로그램 빌드
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]에서는 IDE\(통합 개발 환경\)에서 만든 프로젝트도 명령줄에서 빌드할 수 있습니다.  실제로 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]만 설치된 다른 컴퓨터에서 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]로 만든 프로젝트를 다시 빌드할 수 있습니다.  따라서 중앙의 빌드 작업실을 활용하거나 프로젝트 자체의 빌드 범위를 넘어서는 고급 스크립팅 기술을 사용하여 자동화 프로세스를 통해 빌드를 재현할 수 있습니다.  
  
## MSBuild를 사용하여 ClickOnce 응용 프로그램 배포 재현  
 명령줄에서 호출된 msbuild \/target:publish는 프로젝트를 빌드하고 게시 폴더에 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 만들도록 MSBuild 시스템에 지시합니다.  IDE에서 **게시** 명령을 선택해도 같은 결과가 발생합니다.  
  
 이 명령은 Visual Studio 명령 프롬프트 환경의 경로에 있는 msbuild.exe를 실행합니다.  
  
 "target"은 명령 처리 방식을 MSBuild에 알려 줍니다.  주요 대상은 "빌드" 대상과 "게시" 대상입니다.  빌드 대상은 IDE에서 빌드 명령을 선택하거나 F5 키를 눌러 지정할 수 있습니다.  프로젝트를 빌드하기만 하려는 경우 `msbuild`를 입력하면 됩니다.  빌드 대상이 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]에서 생성한 모든 프로젝트의 기본 대상이 되므로 이 명령만 입력해도 됩니다.  즉, 빌드 대상을 명시적으로 지정하지 않아도 됩니다.  따라서 `msbuild`를 입력하는 경우와 `msbuild /target:build`를 입력하는 경우에 동일한 작업이 수행됩니다.  
  
 `/target:publish` 명령은 게시 대상을 호출하도록 MSBuild에 지시합니다.  게시 대상은 빌드 대상에 따라 달라집니다.  즉, 게시 작업은 빌드 작업의 상위 집합입니다.  예를 들어 Visual Basic 또는 C\# 소스 파일 중 하나를 변경하면 게시 작업에 의해 해당 어셈블리가 자동으로 다시 빌드됩니다.  
  
 Mage.exe 명령줄 도구로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트를 만들어서 전체 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 생성하는 방법에 대한 자세한 내용은 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)를 참조하십시오.  
  
## MSBuild를 사용하여 기본 ClickOnce 응용 프로그램 만들기 및 빌드  
  
#### ClickOnce 프로젝트를 만들고 게시하려면  
  
1.  **파일** 메뉴에서 **새 프로젝트**를 클릭합니다.  **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  **Windows 응용 프로그램**을 선택하고 이름을 `CmdLineDemo`로 지정합니다.  
  
3.  **빌드** 메뉴에서 **게시** 명령을 클릭합니다.  
  
     이렇게 하면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 배포를 생성할 수 있도록 프로젝트가 제대로 구성됩니다.  
  
     게시 마법사가 나타납니다.  
  
4.  게시 마법사에서 **마침**을 클릭합니다.  
  
     Visual Studio에서는 Publish.htm이라는 기본 웹 페이지를 생성하여 표시합니다.  
  
5.  프로젝트를 저장하고 프로젝트가 저장된 폴더 위치를 기록해 둡니다.  
  
 위 단계를 수행하면 처음으로 게시된 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 프로젝트가 만들어집니다.  이제 IDE 외부에서 빌드를 재현할 수 있습니다.  
  
#### 명령줄에서 빌드를 재현하려면  
  
1.  [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]을 종료합니다.  
  
2.  Windows **시작** 메뉴에서 **모든 프로그램**, **Microsoft Visual Studio**, **Visual Studio Tools**, **Visual Studio 명령 프롬프트**를 차례로 클릭합니다.  이렇게 하면 현재 사용자의 루트 폴더에서 명령 프롬프트가 열립니다.  
  
3.  **Visual Studio 명령 프롬프트**에서 현재 디렉터리를 위에서 빌드한 프로젝트의 위치로 변경합니다.  예를 들어 `chdir My Documents\Visual Studio\Projects\CmdLineDemo`를 입력합니다.  
  
4.  "[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 프로젝트를 만들고 게시하려면"에서 생성한 기존 파일을 제거하려면 `rmdir /s publish`를 입력합니다.  
  
     이 단계는 실행하지 않아도 되지만 이렇게 하면 새 파일이 모두 명령줄 빌드를 통해 생성된 것임을 확인할 수 있습니다.  
  
5.  `msbuild /target:publish`를 입력합니다.  
  
 위의 단계를 수행하면 프로젝트의 하위 폴더 **Publish**에 전체 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 배포가 생성됩니다.  CmdLineDemo.application은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트입니다.  CmdLineDemo\_1.0.0.0 폴더에는 CmdLineDemo.exe 파일과 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트인 CmdLineDemo.exe.manifest가 포함되어 있습니다.  Setup.exe는 기본적으로 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 설치하도록 구성된 부트스트래퍼입니다.  DotNetFX 폴더에는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 재배포 가능 요소가 포함되어 있습니다.  이 폴더는 웹 또는 UNC나 CD\/DVD를 통해 응용 프로그램을 배포하는 데 필요한 전체 파일 집합입니다.  
  
## 게시 속성  
 위의 절차에 따라 응용 프로그램을 게시하면 게시 마법사에 의해 다음 속성이 프로젝트 파일에 삽입됩니다.  이러한 속성은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램의 생성 방식에 직접적인 영향을 줍니다.  
  
 CmdLineDemo.vbproj \/ CmdLineDemo.csproj:  
  
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
  
 프로젝트 파일 자체를 변경하지 않고도 명령줄에서 이러한 속성을 재정의할 수 있습니다.  예를 들어 다음 명령을 입력하면 부트스트래퍼 없이도 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 배포가 작성됩니다.  
  
```  
msbuild /target:publish /property:BootstrapperEnabled=false  
```  
  
 게시 속성은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 **프로젝트 디자이너**에 있는 **게시**, **보안** 및 **서명** 속성 페이지에서 제어합니다.  다음은 게시 속성에 대한 설명과 응용 프로그램 디자이너의 다양한 속성 페이지에서 이러한 각 게시 속성을 설정하는 방법입니다.  
  
-   `AssemblyOriginatorKeyFile`은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트에 서명하는 데 사용할 키 파일을 결정합니다.  어셈블리에 강력한 이름을 지정할 때도 동일한 키를 사용할 수 있습니다.  이 속성은 **프로젝트 디자이너**의 **서명** 페이지에서 설정합니다.  
  
 다음 속성은 **보안** 페이지에서 설정합니다.  
  
-   **ClickOnce 보안 설정 사용**에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트의 생성 여부를 결정합니다.  프로젝트가 처음 생성될 때 기본적으로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트 생성이 해제되어 있습니다.  사용자가 프로젝트를 처음 게시하면 마법사가 이 플래그를 자동으로 설정합니다.  
  
-   **TargetZone**은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트로 내보낼 신뢰 수준을 결정합니다.  가능한 값은 "Internet", "LocalIntranet" 및 "Custom"입니다.  Internet 및 LocalIntranet을 사용하면 기본 권한 집합을 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트로 내보냅니다.  기본값인 LocalIntranet은 기본적으로 완전 신뢰를 의미합니다.  Custom은 기본 app.manifest 파일에 명시적으로 지정된 권한만 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트로 내보내도록 지정합니다.  app.manifest 파일은 트러스트 정보 정의만을 포함하는 부분적인 매니페스트 파일입니다.  이 파일은 숨김 파일이며 **보안** 페이지에서 권한을 구성할 때 자동으로 프로젝트에 추가됩니다.  
  
 다음 속성은 **게시** 페이지에서 설정합니다.  
  
-   `PublishUrl`은 IDE에서 응용 프로그램이 게시될 위치입니다.  `InstallUrl` 및 `UpdateUrl` 속성을 지정하지 않으면 이 속성이 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트에 삽입됩니다.  
  
-   `ApplicationVersion`은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램의 버전을 지정합니다.  이 속성은 4자리 버전 번호이며  마지막 숫자가 "\*"이면 빌드 시 매니페스트에 삽입된 값 대신 `ApplicationRevision`을 사용합니다.  
  
-   `ApplicationRevision`은 수정 번호를 지정합니다.  이 속성은 IDE에 게시할 때마다 증가하는 정수입니다.  명령줄에서 수행한 빌드의 경우에는 이 값이 자동으로 증가하지 않습니다.  
  
-   `Install`은 응용 프로그램이 설치된 응용 프로그램인지 아니면 웹에서 실행된 응용 프로그램인지를 확인합니다.  
  
-   `InstallUrl`\(표시되지 않음\)은 사용자가 응용 프로그램을 설치할 원본 위치입니다.  `IsWebBootstrapper` 속성을 활성화한 상태에서 이 속성을 지정하면 속성 값이 setup.exe 부트스트래퍼에 지정됩니다.  `UpdateUrl`을 지정하지 않은 경우 이 값은 응용 프로그램 매니페스트에도 삽입됩니다.  
  
-   `SupportUrl`\(표시되지 않음\)은 설치된 응용 프로그램에 대한 **프로그램 추가\/제거** 대화 상자에 연결된 위치입니다.  
  
 다음 속성은 **게시** 페이지에서 액세스할 수 있는 **응용 프로그램 업데이트** 대화 상자에서 설정합니다.  
  
-   `UpdateEnabled`는 응용 프로그램이 업데이트를 확인할지 여부를 나타냅니다.  
  
-   `UpdateMode`는 포그라운드 업데이트 또는 백그라운드 업데이트를 지정합니다.  
  
-   `UpdateInterval`은 응용 프로그램의 업데이트 확인 빈도를 지정합니다.  
  
-   `UpdateIntervalUnits`는 시, 일 또는 주 중에서 `UpdateInterval` 값의 단위를 지정합니다.  
  
-   `UpdateUrl`\(표시되지 않음\)은 응용 프로그램이 업데이트를 받을 위치입니다.  이 속성을 지정하면 해당 값이 응용 프로그램 매니페스트에 삽입됩니다.  
  
-   다음 속성은 **게시** 페이지에서 액세스할 수 있는 **게시 옵션** 대화 상자에서 설정합니다.  
  
-   `PublisherName`은 응용 프로그램을 설치 또는 실행할 때 표시되는 프롬프트에 나타나는 게시자의 이름을 지정합니다.  설치된 응용 프로그램의 경우 **시작** 메뉴에 표시되는 폴더 이름을 지정하는 데도 이 속성이 사용됩니다.  
  
-   `ProductName`은 응용 프로그램을 설치 또는 실행할 때 표시되는 프롬프트에 나타나는 제품의 이름을 지정합니다.  설치된 응용 프로그램의 경우 **시작** 메뉴에 표시되는 바로 가기 이름을 지정하는 데도 이 속성이 사용됩니다.  
  
-   다음 속성은 **게시** 페이지에서 액세스할 수 있는 **필수 구성 요소** 대화 상자에서 설정합니다.  
  
-   `BootstrapperEnabled`는 setup.exe 부트스트래퍼를 생성할지 여부를 결정합니다.  
  
-   `IsWebBootstrapper`는 setup.exe 부트스트래퍼가 웹을 통해 작동하는지 아니면 디스크 기반 모드로 작동하는지를 결정합니다.  
  
## InstallURL, SupportUrl, PublishURL 및 UpdateURL  
 다음 표에서는 ClickOnce 배포에 대한 URL 옵션을 보여 줍니다.  
  
|URL 옵션|설명|  
|------------|--------|  
|`PublishURL`|ClickOnce 응용 프로그램을 웹 사이트에 게시하려는 경우에 필요합니다.|  
|`InstallURL`|선택적 요소.  설치 사이트가 `PublishURL`과 다른 경우 이 URL 옵션을 설정합니다.  예를 들어 `PublishURL`을 FTP 경로로 설정하고 `InstallURL`을 웹 URL로 설정할 수 있습니다.|  
|`SupportURL`|선택적 요소.  지원 사이트가 `PublishURL`과 다른 경우 이 URL 옵션을 설정합니다.  예를 들어, `SupportURL`을 회사의 고객 지원 웹 사이트로 설정할 수 있습니다.|  
|`UpdateURL`|선택적 요소.  업데이트 위치가 `InstallURL`과 다른 경우 이 URL 옵션을 설정합니다.  예를 들어, `PublishURL`을 FTP 경로로 설정하고 `UpdateURL`을 웹 URL로 설정할 수 있습니다.|  
  
## 참고 항목  
 <xref:Microsoft.Build.Tasks.GenerateBootstrapper>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>   
 <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest>   
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)