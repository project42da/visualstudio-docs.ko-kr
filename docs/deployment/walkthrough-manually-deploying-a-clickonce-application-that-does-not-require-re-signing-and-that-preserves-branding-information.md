---
title: "연습: 다시 서명할 필요가 없고 브랜드 정보가 유지되는 ClickOnce 응용 프로그램 수동 배포 | Microsoft Docs"
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
  - "브랜드"
  - "ClickOnce 응용 프로그램, 다른 사용자가 배포"
  - "ClickOnce 배포, 수동으로"
  - "ClickOnce 배포, SDK 도구"
  - "고객 배포"
  - "매니페스트[ClickOnce]"
  - "수동 ClickOnce 배포"
  - "여러 ClickOnce 배포 및 브랜드"
  - "유지되는 브랜드 정보"
ms.assetid: c21822fb-d4ee-42e4-b72d-41ee9786efe5
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연습: 다시 서명할 필요가 없고 브랜드 정보가 유지되는 ClickOnce 응용 프로그램 수동 배포
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

예전에는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 만들어 고객이 게시 및 배포할 수 있도록 제공하면 고객이 배포 매니페스트를 업데이트하고 다시 서명해야 했습니다. 지금도 대부분의 경우 이 방식이 사용되고 있지만, .NET Framework 3.5를 사용하면 고객이 새 배포 매니페스트를 다시 생성하지 않고도 배포할 수 있는[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 만들 수 있습니다.  자세한 내용은 [다시 서명하지 않고 테스트 및 프로덕션 서버용 ClickOnce 응용 프로그램 배포](../deployment/deploying-clickonce-applications-for-testing-and-production-servers-without-resigning.md)를 참조하십시오.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 만들어 고객에게 게시 및 배포하도록 제공하면 응용 프로그램이 고객의 브랜드를 사용하거나 사용자의 브랜드를 보관할 수 있습니다.  예를 들어 소유권이 있는 단일 응용 프로그램에 사용자의 브랜드를 포함할 수 있습니다.  그리고 각 고객에 대해 응용 프로그램을 매우 세부적으로 사용자 지정하는 경우에는 고객의 브랜드를 사용할 수 있습니다.  .NET Framework 3.5를 사용하면 응용 프로그램을 배포하도록 조직에 제공할 때 브랜드, 게시자 정보 및 보안 서명을 유지할 수 있습니다.  자세한 내용은 [다른 사용자가 배포할 수 있는 ClickOnce 응용 프로그램 만들기](../deployment/creating-clickonce-applications-for-others-to-deploy.md)를 참조하십시오.  
  
> [!NOTE]
>  이 연습에서는 명령줄 도구인 Mage.exe 또는 그래픽 도구인 MageUI.exe를 사용하여 수동으로 배포를 만들 수 있습니다.  수동 배포에 대한 자세한 내용은 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)를 참조하십시오.  
  
## 사전 요구 사항  
 이 연습의 단계를 수행하려면 다음이 필요합니다.  
  
-   배포하려는 Windows Forms 응용 프로그램.  이 응용 프로그램의 이름은 WindowsFormsAppl입니다.  
  
-   Visual Studio 또는 Windows SDK  
  
### Mage.exe를 사용하여 다중 배포 및 브랜드 지원이 포함된 ClickOnce 응용 프로그램을 배포하려면  
  
1.  Visual Studio 명령 프롬프트나 [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] 명령 프롬프트를 열고 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 파일을 저장할 디렉터리로 변경합니다.  
  
2.  현재 배포 버전에 따라 이름이 지정된 디렉터리를 만듭니다.  응용 프로그램을 처음 배포하는 경우에는 대개 1.0.0.0을 선택합니다.  
  
    > [!NOTE]
    >  배포 버전은 응용 프로그램 파일의 버전과 다를 수 있습니다.  
  
3.  bin이라는 하위 디렉터리를 만들고 실행 파일, 어셈블리, 리소스 및 데이터 파일을 비롯한 모든 응용 프로그램 파일을 이 디렉터리에 복사합니다.  
  
4.  Mage.exe를 호출하여 응용 프로그램 매니페스트를 생성합니다.  
  
    ```  
    mage -New Application -ToFile 1.0.0.0\WindowsFormsApp1.exe.manifest -Name "Windows Forms App 1" -Version 1.0.0.0 -FromDirectory 1.0.0.0\bin -UseManifestForTrust true -Publisher "A. Datum Corporation"  
    ```  
  
5.  디지털 인증서를 사용하여 응용 프로그램 매니페스트에 서명합니다.  
  
    ```  
    mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx  
    ```  
  
6.  Mage.exe를 호출하여 배포 매니페스트를 생성합니다.  기본적으로 Mage.exe는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 설치된 응용 프로그램으로 표시하므로 응용 프로그램을 온라인과 오프라인에서 모두 실행할 수 있습니다.  사용자가 온라인 상태일 때만 응용 프로그램을 사용할 수 있도록 하려면 값이 `f` 값인 `-i` 인수를 사용합니다.  이 응용 프로그램은 다중 배포 기능을 활용하기 때문에 Mage.exe에 대해 `-providerUrl` 인수는 제외합니다.  .NET Framework 3.5 이전 버전에서는 오프라인 응용 프로그램에 대해 `-providerUrl`을 제외하면 오류가 발생합니다.  
  
    ```  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "Windows Forms App 1" -Version 1.0.0.0 -AppManifest 1.0.0.0\WindowsFormsApp1.manifest   
    ```  
  
7.  배포 매니페스트에 서명은 하지 마십시오.  
  
8.  자신의 네트워크에 응용 프로그램을 배포할 고객에게 모든 파일을 제공합니다.  
  
9. 이때 고객이 자체 생성한 인증서를 사용하여 배포 매니페스트에 서명해야 합니다.  예를 들어 고객이 Adventure Works라는 회사에 근무하는 경우에는 MakeCert.exe 도구를 사용하여 자체 서명 인증서를 생성할 수 있습니다.  그런 다음 Pvk2pfx.exe 도구를 사용하여 MakeCert.exe로 만든 파일을 PFX 파일에 병합해 Mage.exe로 전달하면 됩니다.  
  
    ```  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
10. 그런 다음 고객이 이 인증서를 사용하여 배포 매니페스트에 서명을 하는 것입니다.  
  
    ```  
    mage -Sign WindowsFormsApp1.application -CertFile MyCert.pfx  
    ```  
  
11. 고객이 사용자에게 응용 프로그램을 배포합니다.  
  
### MageUI.exe를 사용하여 다중 배포 및 브랜드 지원이 포함된 ClickOnce 응용 프로그램을 배포하려면  
  
1.  Visual Studio 명령 프롬프트나 [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] 명령 프롬프트를 열고 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 파일을 저장할 디렉터리로 이동합니다.  
  
2.  bin이라는 하위 디렉터리를 만들고 실행 파일, 어셈블리, 리소스 및 데이터 파일을 비롯한 모든 응용 프로그램 파일을 이 디렉터리에 복사합니다.  
  
3.  현재 배포 버전에 따라 이름이 지정된 하위 디렉터리를 만듭니다.  응용 프로그램을 처음 배포하는 경우에는 대개 1.0.0.0을 선택합니다.  
  
    > [!NOTE]
    >  배포 버전은 응용 프로그램 파일의 버전과 다를 수 있습니다.  
  
4.  \\bin 디렉터리를 2단계에서 만든 디렉터리로 이동합니다.  
  
5.  그래픽 도구 MageUI.exe를 시작합니다.  
  
    ```  
    MageUI.exe  
    ```  
  
6.  메뉴에서 **파일**, **새로 만들기**, **응용 프로그램 매니페스트**를 차례로 선택하여 새 응용 프로그램 매니페스트를 만듭니다.  
  
7.  기본 **이름** 탭에 이 배포의 이름과 버전 번호를 입력합니다.  또한 응용 프로그램을 배포하면 시작 메뉴의 바로 가기 링크에서 폴더 이름으로 사용될 **게시자** 값도 입력합니다.  
  
8.  **응용 프로그램 옵션** 탭을 선택하고 **신뢰 정보에 대한 응용 프로그램 매니페스트 사용**을 클릭합니다.  이렇게 하면 해당 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 대해 타사 브랜드를 사용할 수 있습니다.  
  
9. **파일** 탭을 선택하고 응용 프로그램 디렉터리 텍스트 상자 옆에 있는 **찾아보기...** 단추를 클릭합니다.  
  
10. 2단계에서 만든 응용 프로그램 파일이 들어 있는 디렉터리를 선택하고 폴더 선택 대화 상자에서 **확인**을 클릭합니다.  
  
11. **채우기** 단추를 클릭하여 모든 응용 프로그램 파일을 파일 목록에 추가합니다.  응용 프로그램에 실행 파일이 여러 개 포함되어 있는 경우 **파일 형식** 드롭다운 목록에서 **진입점**을 선택하여 이 배포의 주 실행 파일을 시작 응용 프로그램으로 표시합니다.  응용 프로그램에 실행 파일이 하나만 포함되어 있으면 MageUI.exe에서 자동으로 해당 파일을 표시합니다.  
  
12. **권한이 필요함** 탭을 선택하고 응용 프로그램에 부여해야 할 신뢰 수준을 선택합니다.  대부분의 응용 프로그램에는 기본값인 **완전 신뢰**를 그대로 사용할 수 있습니다.  
  
13. 메뉴에서 **파일**, **저장**을 차례로 선택하고 응용 프로그램 매니페스트를 저장합니다.  응용 프로그램 매니페스트를 저장할 때 이를 서명하라는 메시지가 나타납니다.  
  
14. 인증서가 파일 시스템에 파일로 저장되어 있으면 **인증서 파일로 서명** 옵션을 선택하고 줄임표\(**...**\) 단추를 사용하여 파일 시스템에서 인증서를 선택합니다.  
  
     또는  
  
     인증서가 컴퓨터에서 액세스할 수 있는 인증서 저장소에 보관되어 있으면 **저장된 인증서로 서명** 옵션을 선택하고 제공되는 목록에서 인증서를 선택합니다.  
  
15. 메뉴에서 **파일**, **새로 만들기**, **배포 매니페스트**를 차례로 선택하고 **이름** 탭에 이름과 버전 번호\(이 예제의 경우 1.0.0.0\)를 입력합니다.  
  
16. **업데이트** 탭으로 전환하고 이 응용 프로그램을 업데이트할 빈도를 지정합니다.  응용 프로그램에서 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 API를 사용하여 업데이트를 자체 검사하는 경우 **이 응용 프로그램의 업데이트 확인** 확인란의 선택을 취소합니다.  
  
17. **응용 프로그램 참조** 탭으로 전환합니다.  **매니페스트 선택** 단추를 클릭하고 이전 단계에서 만든 응용 프로그램 매니페스트를 선택하여 이 탭의 값을 모두 미리 채울 수 있습니다.  
  
18. **저장**을 선택하고 배포 매니페스트를 디스크에 저장합니다.  응용 프로그램 매니페스트를 저장할 때 이를 서명하라는 메시지가 나타납니다.  **취소**를 클릭하여 매니페스트를 서명되지 않은 상태로 저장합니다.  
  
19. 모든 응용 프로그램 파일을 고객에게 제공합니다.  
  
20. 이때 고객이 자체 생성한 인증서를 사용하여 배포 매니페스트에 서명해야 합니다.  예를 들어 고객이 Adventure Works라는 회사에 근무하는 경우에는 MakeCert.exe 도구를 사용하여 자체 서명 인증서를 생성할 수 있습니다.  그런 다음 Pvk2pfx.exe 도구를 사용하여 MakeCert.exe로 만든 파일을 PFX 파일에 병합해 MageUI.exe로 전달하면 됩니다.  
  
    ```  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
21. 인증서가 생성되면 고객이 MageUI.exe에서 배포 매니페스트를 연 다음 저장하여 배포 매니페스트에 서명할 수 있습니다.  서명 대화 상자가 나타나면 고객이 **인증서 파일로 서명** 옵션을 선택하고 디스크에 저장한 PFX 파일을 선택합니다.  
  
22. 고객이 사용자에게 응용 프로그램을 배포합니다.  
  
## 다음 단계  
  
## 참고 항목  
 [Mage.exe\(매니페스트 생성 및 편집 도구\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)   
 [MageUI.exe \(매니페스트 생성 및 편집 도구, 그래픽 클라이언트\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)   
 [Makecert.exe\(인증서 작성 도구\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md)