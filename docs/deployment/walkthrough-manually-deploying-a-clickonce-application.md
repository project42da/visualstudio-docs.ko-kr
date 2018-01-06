---
title: "연습: ClickOnce 응용 프로그램을 수동으로 배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Mage.exe, manual ClickOnce deployments
- MageUI.exe, manual ClickOnce deployments
- deploying applications [ClickOnce], manual ClickOnce deployments
- ClickOnce deployment, manually
- ClickOnce deployment, SDK tools
- manual ClickOnce deployments
- manifests [ClickOnce]
ms.assetid: ccee6551-a1b9-4ca2-8845-9c1cf4ac2560
caps.latest.revision: "49"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 2e0035641a8ed374892060dbaabe79d808150cc2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-manually-deploying-a-clickonce-application"></a>연습: ClickOnce 응용 프로그램 수동 배포
배포 하려면 Visual Studio를 사용할 수 없는 경우 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 고급 배포 기능을 사용 해야 하는 응용 프로그램을 만드는 데 Mage.exe 명령줄 도구 사용 해야 하는 신뢰할 수 있는 응용 프로그램 배포와 같은 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트 합니다. 이 연습을 만드는 방법을 설명는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 명령줄 버전 (Mage.exe) 또는 매니페스트 생성 및 편집 도구의 그래픽 버전 (MageUI.exe) 중 하나를 사용 하 여 배포 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습에서는 일부 필수 구성 요소 및 배포를 빌드하기 전에 선택 해야 하는 옵션에 있습니다.  
  
-   Mage.exe 및 MageUI.exe를 설치 합니다.  
  
     Mage.exe 및 MageUI.exe의 일부는는 [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]합니다. 가지고 있거나는 [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] 설치 또는 버전의는 [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] Visual Studio와 함께 포함 합니다. 자세한 내용은 참조 [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=158044) msdn 합니다.  
  
-   배포할 응용 프로그램을 제공 합니다.  
  
     이 연습에서는 배포할 준비가 되어 있는 Windows 응용 프로그램이 있다고 가정 합니다. 이 응용 프로그램 AppToDeploy로 간주 됩니다.  
  
-   배포 배포 되는 방식을 결정 합니다.  
  
     배포 옵션: 웹, 파일 공유 또는 CD 합니다. 자세한 내용은 [ClickOnce Security and Deployment](../deployment/clickonce-security-and-deployment.md)을 참조하세요.  
  
-   향상된 된 신뢰 수준의 응용 프로그램에 필요한 지 여부를 결정 합니다.  
  
     응용 프로그램에 완전 신뢰가 필요한 경우-예를 들어 사용자의 시스템에 대 한 액세스를 전체-사용할 수 있습니다는 `-TrustLevel` 이 설정 하려면 Mage.exe의 옵션입니다. 사용자 지정 권한 응용 프로그램에 대 한 집합을 정의 하려는 경우 다른 매니페스트에서 인터넷 또는 인트라넷 권한 섹션을 복사 하 고, 요구 사항에 맞게 수정 하 고, 텍스트 편집기 또는 MageUI.exe를 사용 하 여 응용 프로그램 매니페스트를 추가 수 있습니다. 자세한 내용은 [Trusted Application Deployment Overview](../deployment/trusted-application-deployment-overview.md)을 참조하십시오.  
  
-   Authenticode 인증서를 가져옵니다.  
  
     Authenticode 인증서와 함께 배포에 서명 해야 합니다. Visual Studio, MageUI.exe 또는 MakeCert.exe 및 Pvk2Pfx.exe 도구를 사용 하 여 테스트 인증서를 생성할 수 있습니다 또는 인증 기관 (CA)에서 인증서를 얻을 수 있습니다. 신뢰할 수 있는 응용 프로그램 배포를 사용 하려는 모든 클라이언트 컴퓨터에 인증서를 설치 하는 한 번도 수행 해야 합니다. 자세한 내용은 [Trusted Application Deployment Overview](../deployment/trusted-application-deployment-overview.md)을 참조하십시오.  
  
    > [!NOTE]
    >  인증 기관에서 얻을 수 있는 CNG 인증서와 함께 배포를 서명할 수 있습니다.  
  
-   응용 프로그램에 UAC 정보로 매니페스트에 없는지 확인 합니다.  
  
     응용 프로그램와 같은 사용자 계정 컨트롤 (UAC) 정보를 사용 하 여 매니페스트를 포함 하는지 여부를 결정 하는 `<dependentAssembly>` 요소입니다. 응용 프로그램 매니페스트를 검사 하려면 Windows Sysinternals를 사용할 수 있습니다 [Sigcheck](http://go.microsoft.com/fwlink/?LinkId=158035) 유틸리티입니다.  
  
     응용 프로그램에 UAC 세부 정보를 사용 하 여 매니페스트에 있으면 다시 빌드해야 것 UAC 정보 없이 합니다. C# Visual Studio에서 프로젝트를 프로젝트 속성을 열고 응용 프로그램 탭을 선택 합니다. 에 **매니페스트** 드롭 다운 목록 **매니페스트 없이 응용 프로그램을 만들**합니다. Visual Studio에서 Visual Basic 프로젝트에 대 한 프로젝트 속성을 열고 응용 프로그램 탭을 선택 하 고 클릭 **UAC 설정 보기**합니다. 열린된 매니페스트 파일에서 단일 내에서 모든 요소를 제거 `<asmv1:assembly>` 요소입니다.  
  
-   클라이언트 컴퓨터에서 필수 구성 요소는 응용 프로그램에 필요한 지 여부를 결정 합니다.  
  
     [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]Visual Studio에서 배포 된 응용 프로그램 배포와 필수 구성 요소 설치 부트스트래퍼 (setup.exe)를 포함할 수 있습니다. 이 연습에 필요한 두 개의 매니페스트 만듭니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 합니다. 필수 부트스트래퍼를 사용 하 여 만들 수 있습니다는 [GenerateBootstrapper 작업](../msbuild/generatebootstrapper-task.md)합니다.  
  
### <a name="to-deploy-an-application-with-the-mageexe-command-line-tool"></a>Mage.exe는 명령줄 도구와 응용 프로그램을 배포 하려면  
  
1.  저장할 디렉터리를 만들 사용자 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 파일입니다.  
  
2.  방금 만든 배포 디렉터리에서 버전 하위 디렉터리를 만듭니다. 처음으로 응용 프로그램 배포 하는 경우 버전 하위 디렉터리 이름을 **1.0.0.0**합니다.  
  
    > [!NOTE]
    >  배포의 버전 응용 프로그램의 버전과 다를 수 있습니다.  
  
3.  응용 프로그램 파일의 모든 실행 파일, 어셈블리, 리소스 및 데이터 파일을 포함 하 여 버전 하위 디렉터리를 복사 합니다. 필요한 경우 추가 파일이 포함 된 하위 디렉터리를 만들 수 있습니다.  
  
4.  열기는 [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] 또는 Visual Studio 명령 프롬프트 및 버전 하위 디렉터리를 변경 합니다.  
  
5.  Mage.exe 호출 하 여 응용 프로그램 매니페스트를 만듭니다. 다음 문은 Intel x86 프로세서에서 실행 하기 위해 컴파일된 코드에 대 한 응용 프로그램 매니페스트를 만듭니다.  
  
    ```  
    mage -New Application -Processor x86 -ToFile AppToDeploy.exe.manifest -name "My App" -Version 1.0.0.0 -FromDirectory .   
    ```  
  
    > [!NOTE]
    >  뒤에 점 (.)를 포함 해야 합니다.는 `-FromDirectory` 현재 디렉터리를 나타내는 옵션을 합니다. 점, 포함 되지 않은 경우에 응용 프로그램 파일에는 경로 지정 해야 합니다.  
  
6.  Authenticode 인증서와 함께 응용 프로그램 매니페스트에 서명 합니다. 대체 *mycert.pfx* 인증서 파일의 경로를 사용 합니다. 대체 *암호* 인증서 파일에 대 한 암호를 사용 합니다.  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile mycert.pfx -Password passwd  
    ```  
  
     CNG 인증서를 사용 하 여 응용 프로그램 매니페스트에 서명 하려면 다음 절차를 사용 합니다. 대체 *cngCert.pfx* 인증서 파일의 경로를 사용 합니다.  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile cngCert.pfx  
    ```  
  
7.  배포 디렉터리의 루트를 변경 합니다.  
  
8.  Mage.exe 호출 하 여 배포 매니페스트를 생성 합니다. Mage.exe에서는 표시 기본적으로 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 한다는 수 모두 실행할 수 있도록 및 오프 라인 설치 된 응용 프로그램으로 배포 합니다. 응용 프로그램을 사용할 수 있도록는 사용자가 온라인 상태일 경우에을 사용 하 여는 `-Install` 옵션의 값 `false`합니다. 기본적으로 사용 하는 경우 사용자가 웹 사이트 또는 파일 공유에서 응용 프로그램을 설치 해야 하는 값을는 `-ProviderUrl` 웹 서버 또는 공유에 매니페스트는 응용 프로그램의 위치를 가리키는 옵션입니다.  
  
    ```  
    mage -New Deployment -Processor x86 -Install true -Publisher "My Co." -ProviderUrl "\\myServer\myShare\AppToDeploy.application" -AppManifest 1.0.0.0\AppToDeploy.exe.manifest -ToFile AppToDeploy.application  
    ```  
  
9. Authenticode 또는 CNG 인증서와 함께 배포 매니페스트에 서명 합니다.  
  
    ```  
    mage -Sign AppToDeploy.application -CertFile mycert.pfx -Password passwd  
    ```  
  
     또는  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile cngCert.pfx  
    ```  
  
10. 배포 디렉터리에서 모든 파일의 배포 대상 또는 미디어를 복사 합니다. 이 웹 사이트 또는 FTP 사이트, 파일 공유 또는 CD-ROM에서 폴더를 수 있습니다.  
  
11. URL, UNC, 또는 응용 프로그램을 설치 하는 데 필요한 실제 미디어와 사용자가 제공 합니다. URL 또는 UNC 제공 하는 경우 부여 해야 사용자가 전체 경로 배포 매니페스트를 합니다. 예를 들어 AppToDeploy http://webserver01/ AppToDeploy 디렉터리에를 배포 하는 경우 전체 URL 경로 http://webserver01/AppToDeploy/AppToDeploy.application 것입니다.  
  
### <a name="to-deploy-an-application-with-the-mageuiexe-graphical-tool"></a>MageUI.exe 그래픽 도구와 응용 프로그램을 배포 하려면  
  
1.  저장할 디렉터리를 만들 사용자 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 파일입니다.  
  
2.  방금 만든 배포 디렉터리에서 버전 하위 디렉터리를 만듭니다. 처음으로 응용 프로그램 배포 하는 경우 버전 하위 디렉터리 이름을 **1.0.0.0**합니다.  
  
    > [!NOTE]
    >  배포의 버전은 응용 프로그램의 버전을 다 합니다.  
  
3.  응용 프로그램 파일의 모든 실행 파일, 어셈블리, 리소스 및 데이터 파일을 포함 하 여 버전 하위 디렉터리를 복사 합니다. 필요한 경우 추가 파일이 포함 된 하위 디렉터리를 만들 수 있습니다.  
  
4.  MageUI.exe 그래픽 도구를 시작 합니다.  
  
    ```  
    MageUI.exe  
    ```  
  
5.  선택 하 여 새 응용 프로그램 매니페스트 만들기 **파일**, **새로**, **응용 프로그램 매니페스트** 메뉴에서 합니다.  
  
6.  기본에서 **이름** 탭에서이 배포의 이름 및 버전 번호를 입력 합니다. 지정 된 **프로세서** 응용 프로그램은 x86 등, 용으로 작성 합니다.  
  
7.  선택 된 **파일** 탭 하 고 (**...** ) 단추 옆에 **응용 프로그램 디렉터리** 입력란. 폴더 찾아보기 대화 상자가 나타납니다.  
  
8.  응용 프로그램 파일이 들어 버전 하위 디렉터리를 선택한 다음 클릭 **확인**합니다.  
  
9. 인터넷 정보 서비스 (IIS)에서 배포 하는 경우 선택 된 **때 채우기 확장명이 없는 모든 파일에.deploy 확장명이 추가** 확인란 합니다.  
  
10. 클릭는 **채우기** 파일 목록에 모든 응용 프로그램 파일을 추가 하려면 단추입니다. 응용 프로그램 실행 파일을 여러 개 있으면 선택 하 여 시작 응용 프로그램으로이 배포에 대 한 주 실행 파일을 표시할 **진입점** 에서 **파일 형식을** 드롭 다운 목록입니다. (응용 프로그램 실행 파일 하나만 있으면 MageUI.exe는 표시 드립니다.)  
  
11. 선택 된 **필요한 사용 권한** 탭 하 고 응용 프로그램에 부여 해야 신뢰 수준을 선택 합니다. 기본값은 **FullTrust**, 대부분의 응용 프로그램에 적합 한 됩니다.  
  
12. 선택 **파일**, **다른 이름으로 저장** 메뉴에서 합니다. 서명 옵션 대화 상자는 응용 프로그램 매니페스트에 서명 하 라는 메시지가 나타납니다.  
  
13. 파일 시스템에 파일로 저장 된 인증서를 사용 하도록 설정한 경우 사용 된 **인증서 파일로 서명** 옵션을 줄임표를 사용 하 여 파일 시스템에서 인증서 선택 (**...** ) 단추입니다. 인증서 암호를 입력 합니다.  
  
     또는  
  
     인증서가 컴퓨터에서 액세스할 수 있는 인증서 저장소에 보관 되어 있는 경우 선택 된 **저장 된 인증서로 서명** 옵션 제공된 된 목록에서 인증서를 선택 합니다.  
  
14. 클릭 **확인** 하 여 응용 프로그램 매니페스트에 서명 합니다. 다른 이름으로 저장 대화 상자가 나타납니다.  
  
15. 다른 이름으로 저장 대화 상자에서 버전 디렉터리를 지정 하 고 클릭 **저장**합니다.  
  
16. 선택 **파일**, **새로**, **배포 매니페스트** 배포 매니페스트를 만들려면 메뉴에서 합니다.  
  
17. 에 **이름** 탭이 배포에 대 한 이름 및 버전 번호를 지정 합니다 (**1.0.0.0** 이 예에서). 지정 된 **프로세서** 응용 프로그램은 x86 등, 용으로 작성 합니다.  
  
18. 선택 된 **설명** 탭 하 고 값을 지정 **게시자** 및 **제품 * * * t**합니다. (**제품** 오프 라인으로 사용에 대 한 클라이언트 컴퓨터에서 응용 프로그램을 설치할 때 Windows 시작 메뉴에서 응용 프로그램에 제공 된 이름입니다.)  
  
19. 선택은 **배포 옵션** 탭 및는 **시작 위치** 텍스트 상자에 웹 서버 또는 공유 응용 프로그램 매니페스트의 위치를 지정 합니다. 예를 들어 \\\myServer\myShare\AppToDeploy.application 합니다.  
  
20. 이전 단계에서.deploy 확장명을 추가 하는 경우 선택 **.deploy 파일 이름 확장명을 사용 하 여** 여기 합니다.  
  
21. 선택 된 **업데이트 옵션** 탭 하 고이 응용 프로그램을 업데이트할 빈도 지정 합니다. 응용 프로그램을 사용 하는 경우 <xref:System.Deployment.Application.UpdateCheckInfo> 업데이트 자체를 확인 하려면 선택을 취소는 **이 응용 프로그램의 업데이트 확인** 확인란 합니다.  
  
22. 선택 된 **응용 프로그램 참조** 탭을 클릭 한 다음는 **매니페스트 선택** 단추입니다. 열기 대화 상자가 나타납니다.  
  
23. 앞에서 만든 응용 프로그램 매니페스트를 선택한 다음 클릭 **열려**합니다.  
  
24. 선택 **파일**, **다른 이름으로 저장** 메뉴에서 합니다. 서명 옵션 대화 상자 배포 매니페스트에 서명 하 라는 메시지가 나타납니다.  
  
25. 파일 시스템에 파일로 저장 된 인증서를 사용 하도록 설정한 경우 사용 된 **인증서 파일로 서명** 옵션을 줄임표를 사용 하 여 파일 시스템에서 인증서 선택 (**...** ) 단추입니다. 인증서 암호를 입력 합니다.  
  
     또는  
  
     인증서가 컴퓨터에서 액세스할 수 있는 인증서 저장소에 보관 되어 있는 경우 선택 된 **저장 된 인증서로 서명** 옵션 제공된 된 목록에서 인증서를 선택 합니다.  
  
26. 클릭 **확인** 하 여 배포 매니페스트에 서명 합니다. 다른 이름으로 저장 대화 상자가 나타납니다.  
  
27. 에 **다른 이름으로 저장** 대화 상자, 배포 및 클릭 한 다음의 루트에 대 한 디렉터리 위로 이동 **저장**합니다.  
  
28. 배포 디렉터리에서 모든 파일의 배포 대상 또는 미디어를 복사 합니다. 이 웹 사이트 또는 FTP 사이트, 파일 공유 또는 CD-ROM에서 폴더를 수 있습니다.  
  
29. URL, UNC, 또는 응용 프로그램을 설치 하는 데 필요한 실제 미디어와 사용자가 제공 합니다. URL 또는 UNC 제공 하는 경우에 배포 매니페스트의 전체 경로 사용자에 게 부여 해야 합니다. 예를 들어 AppToDeploy http://webserver01/ AppToDeploy 디렉터리에를 배포 하는 경우 전체 URL 경로 http://webserver01/AppToDeploy/AppToDeploy.application 것입니다.  
  
## <a name="next-steps"></a>다음 단계  
 응용 프로그램의 새 버전을 배포 해야 할 경우 새 버전의 이름을 딴 새 디렉터리를 만들-1.0.0.1—and 새 디렉터리에 새 응용 프로그램 파일을 복사 하는 예를 들어 있습니다. 다음을 생성 하 고 새 응용 프로그램 매니페스트, 서명 및 업데이트 배포 매니페스트에 서명 하는 이전 단계를 수행 해야 합니다. Mage.exe에서 같은 더 높은 버전을 지정 해야 합니다. `-New` 및 `-Update` 호출으로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 이상 버전에서 가장 중요 한 가장 왼쪽 정수로 업데이트 합니다. MageUI.exe를 사용 하는 경우 업데이트할 수 있습니다 배포 매니페스트를 열거나을 선택 하 고 **응용 프로그램 참조** 탭을 클릭 하 고 **매니페스트 선택** 단추를 클릭 한 다음 업데이트 된 선택 하 응용 프로그램 매니페스트입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Mage.exe(매니페스트 생성 및 편집 도구)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe(매니페스트 생성 및 편집 도구, 그래픽 클라이언트)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)