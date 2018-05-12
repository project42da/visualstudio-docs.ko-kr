---
title: '연습: ClickOnce 응용 프로그램에 다시 서명 필요 하지 않은 하 고 브랜드 정보가 유지를 수동으로 배포 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- branding
- preserved branding information
- ClickOnce deployment, manually
- multiple ClickOnce deployment and branding
- ClickOnce deployment, SDK tools
- customer deployments
- manual ClickOnce deployments
- manifests [ClickOnce]
- ClickOnce applications, deployed by others
ms.assetid: c21822fb-d4ee-42e4-b72d-41ee9786efe5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0584aac376345bc508e5f2088decd45b8c64783b
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information"></a>연습: 다시 서명할 필요가 없고 브랜드 정보가 유지되는 ClickOnce 응용 프로그램 수동 배포
만들 때 한 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 및 게시 하는 고객 수 있도록 제공 및 배포, 배포 매니페스트를 업데이트 하 고 다시 서명 해야 하는 고객 전에 했습니다. .NET Framework 3.5 만들 수 있습니다 여전히 대부분의 경우에는 이러한 방식이 사용 되 고 있지만, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 새 배포 매니페스트를 다시 생성 하지 않고도 고객이 배포할 수 있는 배포입니다. 자세한 내용은 참조 [배포 ClickOnce 응용 프로그램에 대 한 테스트 및 프로덕션 서버 Resigning 없이](../deployment/deploying-clickonce-applications-for-testing-and-production-without-resigning.md)합니다.  
  
 만들 때 한 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 및 게시 하는 고객에 게 제공 및 배포, 응용 프로그램 고객의 브랜드를 사용 하거나 브랜드 보존할 수 있습니다. 예를 들어 응용 프로그램이 단일 소유 응용 프로그램이 있으면 브랜드를 보존 하는 것이 좋습니다. 응용 프로그램은 항상 각 고객에 대 한 사용자 지정한 경우에 고객의 브랜드를 사용 하는 것이 좋습니다. .NET Framework 3.5를 배포 하는 조직에 응용 프로그램에 부여 하면 브랜드를 유지할 수 있습니다, 게시자 정보 및 보안 서명 수 있습니다. 자세한 내용은 참조 [ClickOnce 응용 프로그램 만들기 다른 사용자에 대 한 배포로](../deployment/creating-clickonce-applications-for-others-to-deploy.md)합니다.  
  
> [!NOTE]
>  이 연습에서 배포 수동으로 사용 하 여 만들면 명령줄 도구인 Mage.exe 또는 MageUI.exe 그래픽 도구입니다. 수동 배포에 대 한 자세한 내용은 참조 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습 단계를 수행 하려면 다음이 필요 합니다.  
  
-   배포할 준비가 되어 있는 Windows Forms 응용 프로그램입니다. 이 응용 프로그램 WindowsFormsApp1로 간주 됩니다.  
  
-   Visual Studio 또는 Windows SDK입니다.  
  
### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageexe"></a>여러 배포 및 브랜드 지원 Mage.exe를 사용 하 여 ClickOnce 응용 프로그램을 배포 하려면  
  
1.  Visual Studio 명령 프롬프트를 열고 또는 [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] 명령 프롬프트를 하 고 저장 하는 있는 디렉터리로 변경 하면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 파일입니다.  
  
2.  배포의 현재 버전의 이름을 딴 디렉터리를 만듭니다. 선택 될 가능성이 처음으로 응용 프로그램 배포 하는 경우 **1.0.0.0**합니다.  
  
    > [!NOTE]
    >  배포의 버전 응용 프로그램 파일의 버전과 다를 수 있습니다.  
  
3.  명명 된 하위 디렉터리를 만듭니다 **bin** 실행 파일, 어셈블리, 리소스 및 데이터 파일을 포함 하 여 모든 응용 프로그램 파일을 복사 합니다.  
  
4.  Mage.exe 호출 하 여 응용 프로그램 매니페스트를 생성 합니다.  
  
    ```  
    mage -New Application -ToFile 1.0.0.0\WindowsFormsApp1.exe.manifest -Name "Windows Forms App 1" -Version 1.0.0.0 -FromDirectory 1.0.0.0\bin -UseManifestForTrust true -Publisher "A. Datum Corporation"  
    ```  
  
5.  디지털 인증서를 사용 하 여 응용 프로그램 매니페스트에 서명 합니다.  
  
    ```  
    mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx  
    ```  
  
6.  Mage.exe 호출 하 여 배포 매니페스트를 생성 합니다. Mage.exe에서는 표시 기본적으로 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 한다는 수 모두 실행할 수 있도록 및 오프 라인 설치 된 응용 프로그램으로 배포 합니다. 응용 프로그램을 사용할 수 있도록는 사용자가 온라인 상태일 경우에을 사용 하 여는 `-i` 인수 값이 `f`합니다. 이 응용 프로그램은 여러 배포 기능을 이용 하므로 제외는 `-providerUrl` Mage.exe에 대 한 인수입니다. (제외 하 고.NET Framework 버전 3.5, 이전 버전에서 `-providerUrl` 에 오프 라인 응용 프로그램에서 오류가 발생 합니다.)  
  
    ```  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "Windows Forms App 1" -Version 1.0.0.0 -AppManifest 1.0.0.0\WindowsFormsApp1.manifest   
    ```  
  
7.  배포 매니페스트를 서명 하지 않습니다.  
  
8.  자신의 네트워크에 응용 프로그램을 배포 하는 고객에 게 모든 파일을 제공 합니다.  
  
9. 이 시점에서 고객은 자신의 자동 생성된 인증서를 사용 하 여 배포 매니페스트에 서명 해야 합니다. 예를 들어 Adventure Works 라는 회사에 대 한 고객 성공 MakeCert.exe 도구를 사용 하 여 자체 서명 된 인증서를 생성할 수 그 합니다. 다음으로 Pvk2pfx.exe 도구를 사용 하 여 Mage.exe에 전달 될 수 있는 PFX 파일에 MakeCert.exe에서 생성 된 파일을 결합 합니다.  
  
    ```  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
10. 고객이 다음를 사용 하 여이 인증서 배포 매니페스트에 서명 합니다.  
  
    ```  
    mage -Sign WindowsFormsApp1.application -CertFile MyCert.pfx  
    ```  
  
11. 고객이 사용자에 게 응용 프로그램을 배포합니다.  
  
### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageuiexe"></a>여러 배포 및 브랜드 지원 MageUI.exe를 사용 하 여 ClickOnce 응용 프로그램을 배포 하려면  
  
1.  Visual Studio 명령 프롬프트를 열고 또는 [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] 명령 프롬프트를 저장 하는 있는 디렉터리로 이동 하면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 파일입니다.  
  
2.  명명 된 하위 디렉터리를 만듭니다 **bin** 실행 파일, 어셈블리, 리소스 및 데이터 파일을 포함 하 여 모든 응용 프로그램 파일을 복사 합니다.  
  
3.  배포의 현재 버전의 이름을 딴 하위 디렉터리를 만듭니다. 선택 될 가능성이 처음으로 응용 프로그램 배포 하는 경우 **1.0.0.0**합니다.  
  
    > [!NOTE]
    >  배포의 버전 응용 프로그램 파일의 버전과 다를 수 있습니다.  
  
4.  이동 된 \\ **bin** 2 단계에서 만든 디렉터리입니다.  
  
5.  그래픽 도구 MageUI.exe를 시작 합니다.  
  
    ```  
    MageUI.exe  
    ```  
  
6.  선택 하 여 새 응용 프로그램 매니페스트 만들기 **파일**, **새로**, **응용 프로그램 매니페스트** 메뉴에서 합니다.  
  
7.  기본에서 **이름** 탭에서이 배포의 이름 및 버전 번호를 입력 합니다. 또한에 값을 제공 **게시자**, 하는 응용 프로그램의 바로 가기 링크 시작 메뉴에 대 한 폴더 이름으로 배포 될 때입니다.  
  
8.  선택 된 **응용 프로그램 옵션** 탭을 클릭 **응용 프로그램 매니페스트 신뢰 정보에 대 한 사용**합니다. 이 대 한 제 3 자 브랜딩 그러면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다.  
  
9. 선택 된 **파일** 탭을 클릭는 **찾아보기** 응용 프로그램 디렉터리 입력란 옆에 있는 단추입니다.  
  
10. 2 단계에서 만든 응용 프로그램 파일을 포함 하는 디렉터리를 선택 하 고 클릭 **확인** 폴더 선택 대화 상자에서 합니다.  
  
11. 클릭는 **채우기** 파일 목록에 모든 응용 프로그램 파일을 추가 하려면 단추입니다. 응용 프로그램 실행 파일을 여러 개 있으면 선택 하 여 시작 응용 프로그램으로이 배포에 대 한 주 실행 파일을 표시할 **진입점** 에서 **파일 형식을** 드롭 다운 목록입니다. (응용 프로그램 실행 파일이 포함 된 경우 MageUI.exe는 표시 드립니다.)  
  
12. 선택 된 **필요한 사용 권한** 탭 하 고 응용 프로그램에 부여 해야 할 신뢰 수준을 선택 합니다. 기본값은 **완전 신뢰**, 대부분의 응용 프로그램에 대 한 적절 한 됩니다.  
  
13. 선택 **파일**, **저장** 메뉴에서 및 응용 프로그램 매니페스트를 저장 합니다. 저장 하면 응용 프로그램 매니페스트에 서명 하 라는 메시지가 표시 됩니다.  
  
14. 파일 시스템에 파일로 저장 된 인증서를 사용 하도록 설정한 경우 사용 된 **인증서 파일로 서명** 옵션을 줄임표를 사용 하 여 파일 시스템에서 인증서 선택 (**...** ) 단추입니다.  
  
     -또는-  
  
     인증서를 컴퓨터에서 액세스할 수 있는 인증서 저장소에 유지 한 경우 선택의 **저장 된 인증서로 서명 옵션**, 제공 된 목록에서 인증서를 선택 합니다.  
  
15. 선택 **파일**, **새로 만들기**, **배포 매니페스트** 배포 매니페스트를 만들려는 메뉴에서를 선택한 다음는 **이름** 탭에서 제공 된 이름 및 버전 번호 (**1.0.0.0** 이 예에서).  
  
16. 전환 하는 **업데이트** 탭 하 고이 응용 프로그램을 업데이트할 빈도 지정 합니다. 응용 프로그램을 사용 하는 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 자체에 업데이트를 확인 하려면 배포 API 레이블이 있는 확인란의 선택을 취소 **이 응용 프로그램의 업데이트 확인**합니다.  
  
17. 전환 하는 **응용 프로그램 참조** 탭 합니다. 클릭 하 여이 탭에서 값을 모두 미리 채울 수는 **매니페스트 선택** 이전 단계에서 만든 단추와 응용 프로그램 매니페스트를 선택 합니다.  
  
18. 선택 **저장** 디스크에 배포 매니페스트를 저장 합니다. 저장 하면 응용 프로그램 매니페스트에 서명 하 라는 메시지가 표시 됩니다. 클릭 **취소** 매니페스트 서명 되지 않은 상태로 저장 합니다.  
  
19. 고객에 게 모든 응용 프로그램 파일을 제공 합니다.  
  
20. 이 시점에서 고객은 자신의 자동 생성된 인증서를 사용 하 여 배포 매니페스트에 서명 해야 합니다. 예를 들어 Adventure Works 라는 회사에 대 한 고객 성공 MakeCert.exe 도구를 사용 하 여 자체 서명 된 인증서를 생성할 수 그 합니다. 다음으로 Pvk2pfx.exe 도구를 사용 하 여 MageUI.exe에 전달 될 수 있는 PFX 파일로 MakeCert.exe에서 생성 된 파일을 결합 합니다.  
  
    ```  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
21. 생성 된 인증서와 고객 MageUI.exe에서 배포 매니페스트를 열어 다음 저장 하 여 배포 매니페스트 이제 서명 합니다. 선택 서명 대화 상자가 나타나면 **인증서 파일로 서명** 옵션을 디스크에 저장 한 PFX 파일을 선택 합니다.  
  
22. 고객이 사용자에 게 응용 프로그램을 배포합니다.  
  
## <a name="next-steps"></a>다음 단계  
  
## <a name="see-also"></a>참고 항목  
 [Mage.exe(매니페스트 생성 및 편집 도구)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe(매니페스트 생성 및 편집 도구, 그래픽 클라이언트)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [MakeCert](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx)