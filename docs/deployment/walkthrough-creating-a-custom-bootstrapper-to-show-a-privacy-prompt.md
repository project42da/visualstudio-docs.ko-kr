---
title: '연습: 개인 정보 보호 표시할 메시지를 사용자 지정 부트스트래퍼를 만드는 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, prerequisites
- dependencies [.NET Framework], custom bootstrapper package
- deploying applications [Visual Studio], custom prerequisites
- Windows Installer deployment, prerequisites
- prerequisites [.NET Framework], custom bootstrapper package
ms.assetid: 2f3edd6a-84d1-4864-a1ae-6a13c5732aae
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 22feab436d701124b7e3843a0e6855d2830d570d
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34816044"
---
# <a name="walkthrough-create-a-custom-bootstrapper-with-a-privacy-prompt"></a>연습: 개인정보처리방침 프롬프트가 포함된 사용자 지정 부트스트래퍼 만들기
최신 파일 버전 및 어셈블리 버전으로 어셈블리를 사용할 수 있을 때 자동으로 업데이트 하도록 ClickOnce 응용 프로그램을 구성할 수 있습니다. 을 고객에 게가이 동작에 동의 확인 하기 위해 개인 정보 프롬프트를 표시할 수 있습니다. 그런 다음는 응용 프로그램을 자동으로 업데이트할 수 있는 권한을 부여할지 여부를 선택할 수 있습니다. 응용 프로그램에 자동으로 업데이트 하도록 허용 되지 않습니다 설치 하지 않습니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   Visual Studio 2010  
  
## <a name="create-an-update-consent-dialog-box"></a>업데이트 승인 대화 상자 만들기  
 개인 정보 보호 프롬프트를 표시 하려면 응용 프로그램에 대해 자동 업데이트에 동의 하는지에 게 요청 하는 응용 프로그램을 만듭니다.  
  
#### <a name="to-create-a-consent-dialog-box"></a>동의 대화 상자를 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  에 **새 프로젝트** 대화 상자를 클릭 **Windows**, 클릭 하 고 **WindowsFormsApplication**합니다.  
  
3.  에 대 한는 **이름**, 형식 **ConsentDialog**, 클릭 하 고 **확인**합니다.  
  
4.  디자이너에서 폼을 클릭 합니다.  
  
5.  에 **속성** 창에서 변경 된 **텍스트** 속성을 **업데이트 동의 대화 상자**합니다.  
  
6.  에 **도구 상자**를 확장 하 고 **모든 Windows Forms**, 끌어서는 **레이블** 컨트롤을 폼입니다.  
  
7.  디자이너에서 레이블 컨트롤을 클릭 합니다.  
  
8.  에 **속성** 창에서 변경 된 **텍스트** 아래의 속성 **모양** 다음과:  
  
     응용 프로그램을 설치 하려고 하는 웹에서 최신 업데이트를 확인 합니다. "동의 안 함"을 클릭 하 여 응용 프로그램을 확인 하 고 인터넷에서 업데이트를 자동으로 설치 권한을 부여 합니다.  
  
9. 에 **도구 상자**를 끌어는 **확인란** 컨트롤을 폼의 중간 합니다.  
  
10. 에 **속성** 창 변경은 **텍스트** 아래의 속성 **레이아웃** 를 **동의**합니다.  
  
11. 에 **도구 상자**를 끌어 한 **단추** 컨트롤을 폼의 왼쪽 아래 합니다.  
  
12. 에 **속성** 창 변경은 **텍스트** 아래의 속성 **레이아웃** 를 **진행**합니다.  
  
13. 에 **속성** 창 변경은 **(이름)** 아래의 속성 **디자인** 를 **ProceedButton**합니다.  
  
14. 에 **도구 상자**를 끌어 한 **단추** 컨트롤을 폼의 오른쪽 아래 합니다.  
  
15. **속성** 창에서 변경 된 **텍스트** 아래의 속성 **레이아웃** 를 **취소**합니다.  
  
16. 에 **속성** 창 변경은 **(이름)** 아래의 속성 **디자인** 를 **CancelButton**합니다.  
  
17. 디자이너에서 두 번 클릭은 **동의** CheckedChanged 이벤트 처리기를 생성 하려면 확인란을 선택 합니다.  
  
18. Form1 코드 파일에서 CheckedChanged 이벤트 처리기에 다음 코드를 추가 합니다.  
  
     [!code-csharp[ConsentDialog#1](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_1.cs)]
     [!code-vb[ConsentDialog#1](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_1.vb)]  
  
19. 클래스 생성자를 사용 하지 않으려면 업데이트는 **진행** 기본적으로는 단추입니다.  
  
     [!code-csharp[ConsentDialog#6](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_2.cs)]
     [!code-vb[ConsentDialog#6](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_2.vb)]  
  
20. Form1 코드 파일에서 다음 코드에 대 한 최종 사용자가 온라인 업데이트에 동의 하는 경우에 관리 하는 부울 변수를 추가 합니다.  
  
     [!code-csharp[ConsentDialog#3](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_3.cs)]
     [!code-vb[ConsentDialog#3](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_3.vb)]  
  
21. 디자이너에서 두 번 클릭은 **진행** 단추 클릭 이벤트 처리기를 생성 합니다.  
  
22. Form1 코드 파일에서 다음 코드에 대 한 Click 이벤트 처리기를 추가 **진행** 단추입니다.  
  
     [!code-csharp[ConsentDialog#2](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_4.cs)]
     [!code-vb[ConsentDialog#2](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_4.vb)]  
  
23. 디자이너에서 두 번 클릭은 **취소** 단추 클릭 이벤트 처리기를 생성 합니다.  
  
24. Form1 코드 파일에서 다음 코드에 대 한 Click 이벤트 처리기에 대 한 추가 **취소** 단추입니다.  
  
     [!code-csharp[ConsentDialog#4](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_5.cs)]
     [!code-vb[ConsentDialog#4](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_5.vb)]  
  
25. 최종 사용자가 온라인 업데이트에 동의 하지 않을 경우 오류를 반환 하도록 응용 프로그램을 업데이트 합니다.  
  
     Visual Basic 개발자에 해당:  
  
    1.  **솔루션 탐색기**, 클릭 **ConsentDialog**합니다.  
  
    2.  에 **프로젝트** 메뉴를 클릭 하 여 **모듈 추가**, 클릭 하 고 **추가**합니다.  
  
    3.  Module1.vb 코드 파일에서 다음 코드를 추가 합니다.  
  
         [!code-vb[ConsentDialog#7](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_6.vb)]  
  
    4.  에 **프로젝트** 메뉴를 클릭 하 여 **ConsentDialog 속성**, 클릭 하 고는 **응용 프로그램** 탭 합니다.  
  
    5.  선택을 취소 **응용 프로그램 프레임 워크 사용**합니다.  
  
    6.  에 **시작 개체** 드롭 다운 메뉴 **Module1**합니다.  
  
        > [!NOTE]
        >  Windows XP 시각적 스타일, 응용 프로그램 이벤트, 시작 화면, 단일 인스턴스 응용 프로그램 등의 기능을 비활성화 응용 프로그램 프레임 워크를 사용 하지 않도록 설정 합니다. 자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)를 참조하세요.  
  
     Visual C# 개발자에 해당:  
  
     Program.cs 코드 파일을 열고 다음 코드를 추가 합니다.  
  
     [!code-csharp[ConsentDialog#5](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_7.cs)]  
  
26. 에 **빌드** 메뉴를 클릭 하 여 **솔루션 빌드**합니다.  
  
## <a name="create-the-custom-bootstrapper-package"></a>사용자 지정 부트스트래퍼 패키지 만들기  
 최종 사용자에 게 개인 정보 보호 프롬프트를 표시 하려면 업데이트 동의 대화 상자가 응용 프로그램에 대 한 사용자 지정 부트스트래퍼 패키지를 만들고 모든 ClickOnce 응용 프로그램에 필수 구성 요소로 포함 합니다.  
  
 이 절차에는 다음 문서를 만들어 사용자 지정 부트스트래퍼 패키지를 만드는 방법을 보여 줍니다.  
  
-   product.xml 매니페스트 부트스트래퍼의 내용을 설명 하기 위해 파일.  
  
-   예: 문자열 및 소프트웨어 사용 조건 패키지의 지역화 관련 항목이 나열 package.xml 매니페스트 파일.  
  
-   소프트웨어 사용 조건에 대 한 문서입니다.  
  
#### <a name="step-1-to-create-the-bootstrapper-directory"></a>1 단계: 부트스트래퍼 디렉터리를 만들려면  
  
1.  라는 디렉터리를 만들고 **UpdateConsentDialog** %PROGRAMFILES%\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages에 설치 됩니다.  
  
    > [!NOTE]
    >  이 폴더를 만들려면 관리자 권한이 필요할 수 있습니다.  
  
2.  UpdateConsentDialog 디렉터리에서 en 라는 하위 디렉터리를 만듭니다.  
  
    > [!NOTE]
    >  각 로캘에 대 한 새 디렉터리를 만듭니다. 예를 들어 fr 및 de 로캘에 대 한 하위 디렉터리를 추가할 수 있습니다. 필요한 경우이 디렉터리는 독일어 및 프랑스어 문자열 및 언어 팩을 포함 됩니다.  
  
#### <a name="step-2-to-create-the-productxml-manifest-file"></a>2 단계: product.xml 매니페스트 파일을 만들려면  
  
1.  텍스트 파일을 만들 `product.xml`합니다.  
  
2.  Product.xml 파일에 다음 XML 코드를 추가 합니다. 기존 XML 코드를 덮어쓰지 않도록 있는지 확인 합니다.  
  
    ```xml  
    <Product  
      xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
      ProductCode="Microsoft.Sample.EULA">  
      <!-- Defines the list of files to be copied on build. -->  
      <PackageFiles CopyAllPackageFiles="false">  
        <PackageFile Name="ConsentDialog.exe"/>  
      </PackageFiles>  
  
      <!-- Defines how to run the Setup package.-->  
      <Commands >  
        <Command PackageFile = "ConsentDialog.exe" Arguments=''>  
          <ExitCodes>  
            <ExitCode Value="0" Result="Success" />  
            <ExitCode Value="-1" Result="Fail" String="AU_Unaccepted" />  
            <DefaultExitCode Result="Fail"   
              FormatMessageFromSystem="true" String="GeneralFailure" />  
          </ExitCodes>  
        </Command>  
      </Commands>  
  
    </Product>  
    ```  
  
3.  UpdateConsentDialog 부트스트래퍼 디렉터리에 파일을 저장 합니다.  
  
#### <a name="step-3-to-create-the-packagexml-manifest-file-and-the-software-license-terms"></a>3 단계: package.xml 매니페스트를 만드는 파일 및 소프트웨어 사용 조건  
  
1.  텍스트 파일을 만들 `package.xml`합니다.  
  
2.  Package.xml 파일에서 정의 하는 로캘 고 소프트웨어 사용 조건이 포함 다음 XML 코드를 추가 합니다. 기존 XML 코드를 덮어쓰지 않도록 있는지 확인 합니다.  
  
    ```xml  
    <Package   
      xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
      Name="DisplayName"  
      Culture="Culture"  
      LicenseAgreement="eula.rtf">  
      <PackageFiles>  
        <PackageFile Name="eula.rtf"/>  
      </PackageFiles>  
  
      <!-- Defines a localizable string table for error messages. -->  
      <Strings>  
        <String Name="DisplayName">Update Consent Dialog</String>  
        <String Name="Culture">en</String>  
        <String Name="AU_Unaccepted">The automatic update agreement is not accepted.</String>  
        <String Name="GeneralFailure">A failure occurred attempting to launch the setup.</String>  
      </Strings>  
    </Package>  
    ```  
  
3.  UpdateConsentDialog 부트스트래퍼 디렉터리에 en 하위 디렉터리에 파일을 저장 합니다.  
  
4.  소프트웨어 사용 조건에 대 한 eula.rtf 라는 문서를 만듭니다.  
  
    > [!NOTE]
    >  소프트웨어 사용 조건 라이선스, 보증, 부채 및 지역의 법률에 대 한 정보를 포함 해야 합니다. 이러한 파일은 로캘에, 파일 MBCS 또는 유니코드 문자를 지 원하는 형식으로 저장 되 고 있는지 확인 합니다. 콘텐츠에 대 한 소프트웨어 사용 조건의 법률 자문 부서로 참조 하십시오.  
  
5.  UpdateConsentDialog 부트스트래퍼 디렉터리에 en 하위 디렉터리에 문서를 저장 합니다.  
  
6.  필요한 경우 각 로캘에 대 한 소프트웨어 사용 조건에 대 한 새 매니페스트 package.xml 파일 및 새 eula.rtf 문서를 만듭니다. 예를 들어 fr 및 de 로캘에 대 한 하위 디렉터리를 만든 경우 package.xml 별도 매니페스트 파일을 만들고 소프트웨어 사용 조건 및 fr 및 de 하위 디렉터리에 저장 합니다.  
  
## <a name="set-the-update-consent-application-as-a-prerequisite"></a>필수 구성 요소로 업데이트 동의 응용 프로그램 설정  
 Visual Studio에서 필수 구성 요소로 업데이트 동의 응용 프로그램을 설정할 수 있습니다.  
  
#### <a name="to-set-the-update-consent-application-as-a-prerequisite"></a>필수 구성 요소로 업데이트 동의 응용 프로그램을 설정 하려면  
  
1.  **솔루션 탐색기**를 배포 하려는 응용 프로그램의 이름을 클릭 합니다.  
  
2.  에 **프로젝트** 메뉴를 클릭 하 여 *p r o j* **속성**합니다.  
  
3.  클릭는 **게시** 페이지를 선택한 다음 클릭 **필수 구성 요소**합니다.  
  
4.  선택 **업데이트 동의 대화 상자**합니다.  
  
    > [!NOTE]
    >  필수 구성 요소 대화 상자에서 업데이트 동의 대화를 보려면 Visual Studio를 닫았다가 할 수 있습니다.  
  
5.  **확인**을 클릭합니다.  
  
## <a name="create-and-test-the-setup-program"></a>만들기 및 설치 프로그램을 테스트  
 필수 구성 요소 업데이트 동의 응용 프로그램을 설정한 후 응용 프로그램에 대 한 설치 관리자와 부트스트래퍼를 생성할 수 있습니다.  
  
#### <a name="to-create-and-test-the-setup-program-by-not-clicking-i-agree"></a>동의 만들고 클릭 하지 않는 경우 설치 프로그램을 테스트 하려면  
  
1.  **솔루션 탐색기**를 배포 하려는 응용 프로그램의 이름을 클릭 합니다.  
  
2.  에 **프로젝트** 메뉴를 클릭 하 여 *p r o j* **속성**합니다.  
  
3.  클릭는 **게시** 페이지를 선택한 다음 클릭 **지금 게시**합니다.  
  
4.  게시 출력 자동으로 열리지 않으면 게시 출력을 이동 합니다.  
  
5.  Setup.exe 프로그램을 실행 합니다.  
  
     설치 프로그램에서 업데이트 동의 대화 소프트웨어 사용권 계약을 보여 줍니다.  
  
6.  소프트웨어 사용권 계약을 읽은 다음를 클릭 **Accept**합니다.  
  
     업데이트 승인 대화 상자가 응용 프로그램에 표시 되 고 다음 텍스트를 보여 줍니다: 응용 프로그램을 설치 하려고 합니다. 웹에서 최신 업데이트를 확인 합니다. 동의 함을 클릭 하 여 인터넷에서 자동으로 업데이트를 확인 하려면 응용 프로그램을 인증 합니다.  
  
7.  응용 프로그램을 닫거나 취소 클릭 합니다.  
  
     응용 프로그램 오류를 보여 줍니다:에 대 한 시스템 구성 요소를 설치 하는 동안 오류가 발생 했습니다. *ApplicationName*합니다. 모든 시스템 구성 요소가 설치 될 때까지 계속할 수 없습니다.  
  
8.  다음과 같은 오류 메시지가 표시를 자세히를 클릭 합니다: 구성 요소 업데이트 동의 대화 상자는 다음과 같은 오류 메시지와 함께 설치 하지 못했습니다: "자동 업데이트 동의 허용 되지 않습니다." 다음 구성 요소를 설치 하지 못했습니다.-업데이트 동의 대화 상자  
  
9. **닫기**를 클릭합니다.  
  
#### <a name="to-create-and-test-the-setup-program-by-clicking-i-agree"></a>동의 만들고 클릭 하 여 설치 프로그램을 테스트 하려면  
  
1.  **솔루션 탐색기**를 배포 하려는 응용 프로그램의 이름을 클릭 합니다.  
  
2.  에 **프로젝트** 메뉴를 클릭 하 여 *p r o j* **속성**합니다.  
  
3.  클릭는 **게시** 페이지를 선택한 다음 클릭 **지금 게시**합니다.  
  
4.  게시 출력 자동으로 열리지 않으면 게시 출력을 이동 합니다.  
  
5.  Setup.exe 프로그램을 실행 합니다.  
  
     설치 프로그램에서 업데이트 동의 대화 소프트웨어 사용권 계약을 보여 줍니다.  
  
6.  소프트웨어 사용권 계약을 읽은 다음를 클릭 **Accept**합니다.  
  
     업데이트 승인 대화 상자가 응용 프로그램에 표시 되 고 다음 텍스트를 보여 줍니다: 응용 프로그램을 설치 하려고 합니다. 웹에서 최신 업데이트를 확인 합니다. 동의 함을 클릭 하 여 인터넷에서 자동으로 업데이트를 확인 하려면 응용 프로그램을 인증 합니다.  
  
7.  클릭 **동의**, 클릭 하 고 **진행**합니다.  
  
     응용 프로그램 설치를 시작 합니다.  
  
8.  응용 프로그램 설치 대화 상자가 나타나면 클릭 **설치**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 배포 필수 구성 요소](../deployment/application-deployment-prerequisites.md)   
 [부트스트래퍼 패키지 만들기](../deployment/creating-bootstrapper-packages.md)   
 [방법: 제품 매니페스트 만들기](../deployment/how-to-create-a-product-manifest.md)   
 [방법: 패키지 매니페스트 만들기](../deployment/how-to-create-a-package-manifest.md)   
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)