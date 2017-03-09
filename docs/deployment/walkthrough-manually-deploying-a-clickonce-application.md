---
title: "연습: ClickOnce 응용 프로그램 수동 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
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
  - "ClickOnce 배포, 수동으로"
  - "ClickOnce 배포, SDK 도구"
  - "응용 프로그램 배포[ClickOnce], 수동 ClickOnce 배포"
  - "Mage.exe, 수동 ClickOnce 배포"
  - "MageUI.exe, 수동 ClickOnce 배포"
  - "매니페스트[ClickOnce]"
  - "수동 ClickOnce 배포"
ms.assetid: ccee6551-a1b9-4ca2-8845-9c1cf4ac2560
caps.latest.revision: 49
caps.handback.revision: 47
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연습: ClickOnce 응용 프로그램 수동 배포
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio를 사용하여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 배포할 수 없거나 신뢰할 수 있는 응용 프로그램 배포와 같은 고급 배포 기능을 사용해야 하는 경우 Mage.exe 명령줄 도구를 사용하여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트를 만들어야 합니다.  이 연습에서는 매니페스트 생성 및 편집 도구의 명령줄 버전\(Mage.exe\) 또는 그래픽 버전\(MageUI.exe\)을 사용하여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 만드는 방법에 대해 설명합니다.  
  
## 사전 요구 사항  
 이 연습에서는 배포를 빌드하기 전에 몇 가지 필수 구성 요소와 옵션을 선택해야 합니다.  
  
-   Mage.exe 및 MageUI.exe를 설치합니다.  
  
     Mage.exe 및 MageUI.exe는 [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]에 포함되어 있습니다.  [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)]가 설치되어 있거나 Visual Studio에 포함된 [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] 버전이 있어야 합니다.  자세한 내용은 MSDN에서 [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=158044)를 참조하십시오.  
  
-   배포할 응용 프로그램을 제공합니다.  
  
     이 연습에서는 배포할 준비가 된 Windows 응용 프로그램이 있다고 가정합니다.  이 응용 프로그램의 이름은 AppToDeploy입니다.  
  
-   배포할 방법을 결정합니다.  
  
     배포 옵션으로는 웹, 파일 공유 또는 CD가 있습니다.  자세한 내용은 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)를 참조하십시오.  
  
-   응용 프로그램에 향상된 수준의 신뢰가 필요한지 여부를 확인합니다.  
  
     사용자의 시스템에 대한 모든 액세스 권한 같은 완전 신뢰가 응용 프로그램에 필요한 경우 Mage.exe의 `-TrustLevel` 옵션을 사용하여 이를 설정할 수 있습니다.  응용 프로그램에 대한 사용자 지정 권한 집합을 정의하려는 경우 텍스트 편집기나 MageUI.exe를 사용하여 다른 매니페스트에서 인터넷 또는 인트라넷 권한 섹션을 복사하고 이를 필요에 맞게 수정한 다음 응용 프로그램 매니페스트에 추가할 수 있습니다.  자세한 내용은 [신뢰할 수 있는 응용 프로그램 배포 개요](../deployment/trusted-application-deployment-overview.md)를 참조하십시오.  
  
-   Authenticode 인증서를 구합니다.  
  
     Authenticode 인증서로 배포에 서명해야 합니다.  Visual Studio, MageUI.exe, MakeCert.exe 및 Pvk2Pfx.exe 도구를 사용하여 테스트 인증서를 생성하거나 CA\(인증 기관\)에서 인증서를 구할 수 있습니다.  신뢰할 수 있는 응용 프로그램 배포를 사용하려면 모든 클라이언트 컴퓨터에 인증서를 설치하는 작업을 한 번 수행해야 합니다.  자세한 내용은 [신뢰할 수 있는 응용 프로그램 배포 개요](../deployment/trusted-application-deployment-overview.md)를 참조하십시오.  
  
-   응용 프로그램에 UAC 정보가 있는 매니페스트가 포함되어 있지 않은지 확인합니다.  
  
     응용 프로그램에 `<dependentAssembly>` 요소와 같은 UAC\(사용자 계정 컨트롤\) 정보가 있는 매니페스트가 포함되어 있는지 여부를 확인해야 합니다.  응용 프로그램 매니페스트를 검사하려면 Windows Sysinternals [Sigcheck](http://go.microsoft.com/fwlink/?LinkId=158035) 유틸리티를 사용하면 됩니다.  
  
     응용 프로그램에 UAC 정보가 있는 매니페스트가 포함되어 있으면 UAC 정보 없이 매니페스트를 다시 빌드해야 합니다.  Visual Studio의 C\# 프로젝트의 경우 프로젝트 속성을 열고 응용 프로그램 탭을 선택한 다음  **매니페스트** 드롭다운 목록에서 **매니페스트 없이 응용 프로그램 만들기**를 선택합니다.  Visual Studio의 Visual Basic 프로젝트의 경우 프로젝트 속성을 열고 응용 프로그램 탭을 선택한 다음 **UAC 설정 보기**를 클릭하고  열린 매니페스트 파일에서 단일 `<asmv1:assembly>` 요소가 있는 모든 요소를 제거합니다.  
  
-   클라이언트 컴퓨터에서 응용 프로그램에 필수 구성 요소가 필요한지 여부를 확인합니다.  
  
     Visual Studio에서 배포된 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에는 필수 구성 요소 설치 부트스트래퍼\(setup.exe\)가 포함될 수 있습니다.  이 연습에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포에 필요한 두 개의 매니페스트를 만듭니다.  [GenerateBootstrapper Task](../msbuild/generatebootstrapper-task.md)을 사용하여 필수 구성 요소 부트스트래퍼를 만들 수 있습니다.  
  
### Mage.exe 명령줄 도구를 사용하여 응용 프로그램을 배포하려면  
  
1.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 파일을 저장할 디렉터리를 만듭니다.  
  
2.  방금 만든 배포 디렉터리에서 버전 하위 디렉터리를 만듭니다.  응용 프로그램을 처음 배포하는 경우 버전 하위 디렉터리 이름을 1.0.0.0으로 지정합니다.  
  
    > [!NOTE]
    >  배포 버전은 응용 프로그램 버전과 다를 수 있습니다.  
  
3.  실행 파일, 어셈블리, 리소스 및 데이터 파일을 비롯한 모든 응용 프로그램 파일을 버전 하위 디렉터리에 복사합니다.  필요한 경우 추가 파일이 포함된 하위 디렉터리를 추가로 만들 수도 있습니다.  
  
4.  [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] 또는 Visual Studio 명령 프롬프트를 열고 버전 하위 디렉터리로 변경합니다.  
  
5.  Mage.exe를 호출하여 응용 프로그램 매니페스트를 만듭니다.  다음 문에서는 Intel x86 프로세서에서 실행되도록 컴파일된 코드의 응용 프로그램 매니페스트를 만듭니다.  
  
    ```  
    mage -New Application -Processor x86 -ToFile AppToDeploy.exe.manifest -name "My App" -Version 1.0.0.0 -FromDirectory .   
    ```  
  
    > [!NOTE]
    >  이때 `-FromDirectory` 옵션 뒤에 현재 디렉터리를 나타내는 점\(.\)도 포함해야 합니다.  점을 입력하지 않은 경우에는 응용 프로그램 파일의 경로를 지정해야 합니다.  
  
6.  Authenticode 인증서로 응용 프로그램 매니페스트에 서명합니다.  *mycert.pfx*는 인증서 파일의 경로로 바꾸고  *passwd*는 인증서 파일의 암호로 바꿉니다.  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile mycert.pfx -Password passwd  
    ```  
  
7.  배포 디렉터리의 루트로 변경합니다.  
  
8.  Mage.exe를 호출하여 배포 매니페스트를 생성합니다.  기본적으로 Mage.exe는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 설치된 응용 프로그램으로 표시하므로 응용 프로그램을 온라인과 오프라인에서 모두 실행할 수 있습니다.  사용자가 온라인 상태일 때만 응용 프로그램을 사용할 수 있도록 하려면 `false` 값과 함께 `-Install` 옵션을 사용합니다.  기본값을 적용한 상태에서 사용자가 웹 사이트나 파일 공유를 통해 응용 프로그램을 설치하는 경우 `-ProviderUrl` 옵션의 값이 웹 서버나 공유의 응용 프로그램 매니페스트 위치를 가리켜야 합니다.  
  
    ```  
    mage -New Deployment -Processor x86 -Install true -Publisher "My Co." -ProviderUrl "\\myServer\myShare\AppToDeploy.application" -AppManifest 1.0.0.0\AppToDeploy.exe.manifest -ToFile AppToDeploy.application  
    ```  
  
9. Authenticode 인증서로 배포 매니페스트에 서명합니다.  
  
    ```  
    mage -Sign AppToDeploy.application -CertFile mycert.pfx -Password passwd  
    ```  
  
10. 배포 디렉터리에 있는 모든 파일을 배포 대상이나 미디어에 복사합니다.  웹 사이트나 FTP 사이트의 폴더, 파일 공유 또는 CD\-ROM일 수 있습니다.  
  
11. 응용 프로그램을 설치하는 데 필요한 URL, UNC 또는 실제 미디어를 사용자에게 제공합니다.  URL이나 UNC를 제공하는 경우에는 배포 매니페스트의 전체 경로를 사용자에게 제공해야 합니다.  예를 들어, AppToDeploy가 AppToDeploy 디렉터리의 http:\/\/webserver01\/에 배포되는 경우 전체 URL 경로는 http:\/\/webserver01\/AppToDeploy\/AppToDeploy.application입니다.  
  
### MageUI.exe 그래픽 도구를 사용하여 응용 프로그램을 배포하려면  
  
1.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 파일을 저장할 디렉터리를 만듭니다.  
  
2.  방금 만든 배포 디렉터리에서 버전 하위 디렉터리를 만듭니다.  응용 프로그램을 처음 배포하는 경우 버전 하위 디렉터리 이름을 1.0.0.0으로 지정합니다.  
  
    > [!NOTE]
    >  배포 버전은 응용 프로그램의 버전과 다를 수 있습니다.  
  
3.  실행 파일, 어셈블리, 리소스 및 데이터 파일을 비롯한 모든 응용 프로그램 파일을 버전 하위 디렉터리에 복사합니다.  필요한 경우 추가 파일이 포함된 하위 디렉터리를 추가로 만들 수도 있습니다.  
  
4.  MageUI.exe 그래픽 도구를 시작합니다.  
  
    ```  
    MageUI.exe  
    ```  
  
5.  메뉴에서 **파일**, **새로 만들기**, **응용 프로그램 매니페스트**를 차례로 선택하여 새 응용 프로그램 매니페스트를 만듭니다.  
  
6.  기본 **이름** 탭에 이 배포의 이름과 버전 번호를 입력합니다.  또한 x86과 같이 응용 프로그램이 빌드되는 **프로세서**도 지정합니다.  
  
7.  **파일** 탭을 선택하고 **응용 프로그램 디렉터리** 텍스트 상자 옆에 있는 줄임표\(**...**\) 단추를 클릭합니다.  폴더 찾아보기 대화 상자가 나타납니다.  
  
8.  응용 프로그램 파일이 포함된 버전 하위 디렉터리를 선택한 다음 **확인**을 클릭합니다.  
  
9. IIS\(인터넷 정보 서비스\)에서 배포하는 경우 **채울 때 .deploy 확장명이 없는 모든 파일에 .deploy 확장명 추가** 확인란을 선택합니다.  
  
10. **채우기** 단추를 클릭하여 모든 응용 프로그램 파일을 파일 목록에 추가합니다.  응용 프로그램에 실행 파일이 여러 개 포함되어 있는 경우 **파일 형식** 드롭다운 목록에서 **진입점**을 선택하여 이 배포의 주 실행 파일을 시작 응용 프로그램으로 표시합니다.  응용 프로그램에 실행 파일이 하나만 포함되어 있으면 MageUI.exe에서 자동으로 해당 파일을 표시합니다.  
  
11. **권한이 필요함** 탭을 선택하고 응용 프로그램에 부여해야 할 신뢰 수준을 선택합니다.  대부분의 응용 프로그램에는 기본값인 **FullTrust**를 그대로 사용할 수 있습니다.  
  
12. **파일**을 선택하고 메뉴에서 **다른 이름으로 저장**을 선택합니다.  서명 옵션 대화 상자가 나타나면서 응용 프로그램 매니페스트에 서명하라는 메시지가 표시됩니다.  
  
13. 인증서가 파일 시스템에 파일로 저장되어 있으면 **인증서 파일로 서명** 옵션을 선택하고 줄임표\(**...**\) 단추를 사용하여 파일 시스템에서 인증서를 선택합니다.  그런 다음 인증서 암호를 입력합니다.  
  
     또는  
  
     인증서가 컴퓨터에서 액세스할 수 있는 인증서 저장소에 보관되어 있으면 **저장된 인증서로 서명** 옵션을 선택하고 제공된 목록에서 인증서를 선택합니다.  
  
14. **확인**을 클릭하여 응용 프로그램 매니페스트에 서명합니다.  다른 이름으로 저장 대화 상자가 나타납니다.  
  
15. 다른 이름으로 저장 대화 상자에서 버전 디렉터리를 지정한 다음 **저장**을 클릭합니다.  
  
16. 메뉴에서 **파일**, **새로 만들기**, **배포 매니페스트**를 차례로 선택하여 배포 매니페스트를 만듭니다.  
  
17. **이름** 탭에서 이 배포의 이름과 버전 번호\(이 예제에서 1.0.0.0\)를 지정합니다.  또한 x86과 같이 응용 프로그램이 빌드되는 **프로세서**도 지정합니다.  
  
18. **설명** 탭을 선택하고 **게시자**와 **제품**의 값을 입력합니다.  **제품**은 응용 프로그램을 오프라인으로 사용하기 위해 클라이언트 컴퓨터에 설치할 때 Windows 시작 메뉴에서 응용 프로그램에 부여되는 이름입니다.  
  
19. **배포 옵션** 탭을 선택하고 **시작 위치** 텍스트 상자에서 웹 서버나 공유의 응용 프로그램 매니페스트의 위치를 지정합니다.  예를 들어, \\\\myServer\\myShare\\AppToDeploy.application을 지정합니다.  
  
20. 이전 단계에서 .deploy 확장명을 추가한 경우 여기서 **.deploy 파일 확장명 사용**도 선택합니다.  
  
21. **업데이트 옵션** 탭을 선택하고 이 응용 프로그램을 업데이트할 빈도를 지정합니다.  응용 프로그램에서 <xref:System.Deployment.Application.UpdateCheckInfo>를 사용하여 업데이트를 자체 검사하는 경우 **이 응용 프로그램의 업데이트 확인** 확인란의 선택을 취소합니다.  
  
22. **응용 프로그램 참조** 탭을 선택한 다음 **매니페스트 선택** 단추를 클릭합니다.  열기 대화 상자가 나타납니다.  
  
23. 앞에서 만든 응용 프로그램 매니페스트를 선택한 다음 **열기**를 클릭합니다.  
  
24. **파일**을 선택하고 메뉴에서 **다른 이름으로 저장**을 선택합니다.  서명 옵션 대화 상자가 나타나면서 배포 매니페스트에 서명하라는 메시지가 표시됩니다.  
  
25. 인증서가 파일 시스템에 파일로 저장되어 있으면 **인증서 파일로 서명** 옵션을 선택하고 줄임표\(**...**\) 단추를 사용하여 파일 시스템에서 인증서를 선택합니다.  그런 다음 인증서 암호를 입력합니다.  
  
     또는  
  
     인증서가 컴퓨터에서 액세스할 수 있는 인증서 저장소에 보관되어 있으면 **저장된 인증서로 서명** 옵션을 선택하고 제공된 목록에서 인증서를 선택합니다.  
  
26. **확인**을 클릭하여 배포 매니페스트에 서명합니다.  다른 이름으로 저장 대화 상자가 나타납니다.  
  
27. **다른 이름으로 저장** 대화 상자에서 한 디렉터리 위인 배포의 루트로 이동한 다음 **저장**을 클릭합니다.  
  
28. 배포 디렉터리에 있는 모든 파일을 배포 대상이나 미디어에 복사합니다.  웹 사이트나 FTP 사이트의 폴더, 파일 공유 또는 CD\-ROM일 수 있습니다.  
  
29. 응용 프로그램을 설치하는 데 필요한 URL, UNC 또는 실제 미디어를 사용자에게 제공합니다.  URL이나 UNC를 제공하는 경우에는 배포 매니페스트의 전체 경로를 사용자에게 제공해야 합니다.  예를 들어, AppToDeploy가 AppToDeploy 디렉터리의 http:\/\/webserver01\/에 배포되는 경우 전체 URL 경로는 http:\/\/webserver01\/AppToDeploy\/AppToDeploy.application입니다.  
  
## 다음 단계  
 새 버전의 응용 프로그램을 배포해야 하는 경우 1.0.0.1 같이 버전을 따서 새 디렉터리의 이름을 만들고 새 응용 프로그램 파일을 이 새 디렉터리에 복사합니다.  그런 다음 위에 나열된 단계를 수행하여 새 응용 프로그램 매니페스트를 만든 후 이에 서명하고 배포 매니페스트를 업데이트한 후 이에 서명합니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]는 더 높은 버전\(가장 왼쪽에 있는 정수가 가장 중요\)만 업데이트하므로 Mage.exe `-New`와 `–Update`를 호출할 때는 동일한 버전을 지정해야 합니다.  MageUI.exe를 사용한 경우 배포 매니페스트를 열고 **응용 프로그램 참조** 탭을 선택한 다음 **매니페스트 선택** 단추를 클릭하고 업데이트된 응용 프로그램 매니페스트를 선택하여 해당 배포 매니페스트를 업데이트할 수 있습니다.  
  
## 참고 항목  
 [Mage.exe\(매니페스트 생성 및 편집 도구\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)   
 [MageUI.exe \(매니페스트 생성 및 편집 도구, 그래픽 클라이언트\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)