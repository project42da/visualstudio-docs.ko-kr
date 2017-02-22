---
title: "연습: 사용자 지정 부트스트래퍼를 만들어 개인 정보 취급 방침 프롬프트 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포, 필수 구성 요소"
  - "종속성[.NET Framework], 사용자 지정 부트스트래퍼 패키지"
  - "응용 프로그램 배포[Visual Studio], 사용자 지정 필수 구성 요소"
  - "필수 구성 요소[.NET Framework], 사용자 지정 부트스트래퍼 패키지"
  - "Windows Installer 배포, 필수 구성 요소"
ms.assetid: 2f3edd6a-84d1-4864-a1ae-6a13c5732aae
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연습: 사용자 지정 부트스트래퍼를 만들어 개인 정보 취급 방침 프롬프트 표시
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

더 새로운 파일 버전 및 어셈블리 버전의 어셈블리를 사용할 수 있게 되면 자동으로 업데이트하도록 ClickOnce 응용 프로그램을 구성할 수 있습니다.  고객이 이러한 동작에 동의하도록 고객에게 개인 정보 취급 방침 프롬프트를 표시할 수 있습니다.  그러면 고객은 응용 프로그램에 자동 업데이트 권한을 부여할 것인지 여부를 선택할 수 있습니다.  고객이 자동 업데이트를 허용하지 않으면 응용 프로그램이 설치되지 않습니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   Visual Studio 2010  
  
## 업데이트 동의 대화 상자 만들기  
 개인 정보 취급 방침 프롬프트를 표시하려면 응용 프로그램의 자동 업데이트에 동의하는지 묻는 응용 프로그램을 만듭니다.  
  
#### 동의 대화 상자를 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자에서 **Windows**를 클릭한 다음 **Windows Forms 응용 프로그램**을 클릭합니다.  
  
3.  **이름**에 ConsentDialog를 입력하고 **확인**을 클릭합니다.  
  
4.  디자이너에서 폼을 클릭합니다.  
  
5.  **속성** 창에서 **Text** 속성을 업데이트 동의 대화 상자로 변경합니다.  
  
6.  **도구 상자**에서 **모든 Windows Forms**를 확장하고 **Label** 컨트롤을 폼으로 끌어서 놓습니다.  
  
7.  디자이너에서 레이블 컨트롤을 두 번 클릭합니다.  
  
8.  **속성** 창에서 **모양** 아래의 **Text** 속성을 다음으로 변경합니다.  
  
     설치하려는 응용 프로그램은 웹에서 최신 업데이트를 확인합니다.  "동의함"을 클릭하면 응용 프로그램에 인터넷에서 자동으로 업데이트를 확인 및 설치할 수 있는 권한을 부여하게 됩니다.  
  
9. **도구 상자**에서 **Checkbox** 컨트롤을 폼 중앙으로 끌어서 놓습니다.  
  
10. **속성** 창에서 **레이아웃** 아래의 **Text** 속성을 동의함으로 변경합니다.  
  
11. **도구 상자**에서 **Button** 컨트롤을 폼의 왼쪽 아래로 끌어서 놓습니다.  
  
12. **속성** 창에서 **레이아웃** 아래의 **Text** 속성을 계속으로 변경합니다.  
  
13. **속성** 창에서 **디자인** 아래의 **\(Name\)** 속성을 ProceedButton으로 변경합니다.  
  
14. **도구 상자**에서 **Button** 컨트롤을 폼의 오른쪽 아래로 끌어서 놓습니다.  
  
15. **속성** 창에서 **레이아웃** 아래의 **Text** 속성을 취소로 변경합니다.  
  
16. **속성** 창에서 **디자인** 아래의 **\(Name\)** 속성을 CancelButton으로 변경합니다.  
  
17. 디자이너에서 **동의함** 확인란을 두 번 클릭하여 CheckedChanged 이벤트 처리기를 생성합니다.  
  
18. Form1 코드 파일에서 CheckedChanged 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-cs[ConsentDialog#1](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_1.cs)]
     [!code-vb[ConsentDialog#1](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_1.vb)]  
  
19. 클래스 생성자를 업데이트하여 **계속** 단추를 기본적으로 비활성화합니다.  
  
     [!code-cs[ConsentDialog#6](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_2.cs)]
     [!code-vb[ConsentDialog#6](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_2.vb)]  
  
20. Form1 코드 파일에서 Boolean 변수에 대해 다음 코드를 추가하여 최종 사용자가 온라인 업데이트에 동의했는지 여부를 추적합니다.  
  
     [!code-cs[ConsentDialog#3](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_3.cs)]
     [!code-vb[ConsentDialog#3](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_3.vb)]  
  
21. 디자이너에서 **계속** 단추를 두 번 클릭하여 Click 이벤트 처리기를 생성합니다.  
  
22. Form1 코드 파일에서 **계속** 단추의 Click 이벤트 처리기에 대해 다음 코드를 추가합니다.  
  
     [!code-cs[ConsentDialog#2](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_4.cs)]
     [!code-vb[ConsentDialog#2](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_4.vb)]  
  
23. 디자이너에서 **취소** 단추를 두 번 클릭하여 Click 이벤트 처리기를 생성합니다.  
  
24. Form1 코드 파일에서 **취소** 단추의 Click 이벤트 처리기에 대해 다음 코드를 추가합니다.  
  
     [!code-cs[ConsentDialog#4](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_5.cs)]
     [!code-vb[ConsentDialog#4](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_5.vb)]  
  
25. 응용 프로그램을 업데이트하여 최종 사용자가 온라인 업데이트에 동의하지 않을 경우 오류를 반환하도록 합니다.  
  
     Visual Basic 개발자에만 해당되는 내용:  
  
    1.  **솔루션 탐색기**에서 **ConsentDialog**를 클릭합니다.  
  
    2.  **프로젝트** 메뉴에서 **모듈 추가**를 클릭한 다음 **추가**를 클릭합니다.  
  
    3.  Module1.vb 코드 파일에서 다음 코드를 추가합니다.  
  
         [!code-vb[ConsentDialog#7](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_6.vb)]  
  
    4.  **프로젝트** 메뉴에서 **ConsentDialog 속성**을 클릭한 다음 **응용 프로그램** 탭을 클릭합니다.  
  
    5.  **응용 프로그램 프레임워크 사용** 선택을 취소합니다.  
  
    6.  **시작 개체** 드롭다운 목록에서 **Module1**을 선택합니다.  
  
        > [!NOTE]
        >  응용 프로그램 프레임워크를 사용하지 않도록 설정하면 Windows XP 비주얼 스타일, 응용 프로그램 이벤트, 시작 화면, 단일 인스턴스 응용 프로그램 등의 기능이 비활성화됩니다.  자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](../ide/reference/application-page-project-designer-visual-basic.md)를 참조하십시오.  
  
     C\# 개발자에만 해당되는 내용:  
  
     Program.cs 코드 파일을 열고 다음 코드를 추가합니다.  
  
     [!code-cs[ConsentDialog#5](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_7.cs)]  
  
26. **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
## 사용자 지정 부트스트래퍼 패키지 만들기  
 최종 사용자에게 개인 정보 취급 방침 프롬프트를 표시하려면 업데이트 동의 대화 상자 응용 프로그램을 위한 사용자 지정 부트스트래퍼 패키지를 만들어 이를 모든 ClickOnce 응용 프로그램의 필수 구성 요소로 포함하면 됩니다.  
  
 이 절차에서는 다음 문서를 만들어 사용자 지정 부트스트래퍼 패키지를 만드는 방법을 보여 줍니다.  
  
-   부트스트래퍼의 내용을 설명하는 product.xml 매니페스트 파일  
  
-   패키지의 지역화 관련 항목을 나열하는 package.xml 매니페스트 파일\(예: 문자열 및 소프트웨어 사용 약관\)  
  
-   소프트웨어 사용 약관 문서  
  
#### 1단계: 부트스트래퍼 디렉터리 만들기  
  
1.  %PROGRAMFILES%\\Microsoft SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages에 UpdateConsentDialog라는 디렉터리를 만듭니다.  
  
    > [!NOTE]
    >  이 폴더를 만들려면 관리자 권한이 필요할 수 있습니다.  
  
2.  UpdateConsentDialog 디렉터리에서 en이라는 하위 디렉터리를 만듭니다.  
  
    > [!NOTE]
    >  각 로캘에 대해 새 디렉터리를 만듭니다.  예를 들어 fr 및 de 로캘에 대한 하위 디렉터리를 추가할 수 있습니다.  필요한 경우 이러한 디렉터리에는 프랑스어 및 독일어 문자열과 언어 팩이 포함될 수 있습니다.  
  
#### 2단계: product.xml 매니페스트 파일 만들기  
  
1.  `product.xml`이라는 텍스트 파일을 만듭니다.  
  
2.  product.xml 파일에서 다음 XML 코드를 추가합니다.  기존 XML 코드를 덮어쓰지 않도록 해야 합니다.  
  
    ```  
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
  
3.  UpdateConsentDialog 부트스트래퍼 디렉터리에 파일을 저장합니다.  
  
#### 3단계: package.xml 매니페스트 파일 및 소프트웨어 사용 약관 만들기  
  
1.  `package.xml`이라는 텍스트 파일을 만듭니다.  
  
2.  package.xml 파일에서 다음 XML 코드를 추가하여 로캘을 정의하고 소프트웨어 사용 약관을 포함합니다.  기존 XML 코드를 덮어쓰지 않도록 해야 합니다.  
  
    ```  
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
  
3.  UpdateConsentDialog 부트스트래퍼 디렉터리의 en 하위 디렉터리에 파일을 저장합니다.  
  
4.  소프트웨어 사용 약관에 대한 eula.rtf라는 문서를 만듭니다.  
  
    > [!NOTE]
    >  소프트웨어 사용 약관에는 라이선스, 보증, 책임 및 지역 법에 대한 정보가 포함되어야 합니다.  이러한 파일은 로캘별 파일이어야 하므로 MBCS 또는 유니코드 문자를 지원하는 형식으로 파일을 저장해야 합니다.  소프트웨어 사용 약관의 내용에 대해서는 법무 부서와 상의하십시오.  
  
5.  UpdateConsentDialog 부트스트래퍼 디렉터리의 en 하위 디렉터리에 문서를 저장합니다.  
  
6.  필요한 경우 각 로캘에 대해 새 package.xml 매니페스트 파일과 소프트웨어 사용 약관에 대한 새 eula.rtf 문서를 만듭니다.  예를 들어 fr 및 de 로캘에 대한 하위 디렉터리를 만든 경우 별도의 package.xml 매니페스트 파일과 소프트웨어 사용 약관을 만들어 fr 및 de 하위 디렉터리에 저장합니다.  
  
## 업데이트 동의 응용 프로그램을 필수 구성 요소로 설정  
 Visual Studio에서 업데이트 동의 응용 프로그램을 필수 구성 요소로 설정할 수 있습니다.  
  
#### 업데이트 동의 응용 프로그램을 필수 구성 요소로 설정하려면  
  
1.  **솔루션 탐색기**에서 배포할 응용 프로그램의 이름을 클릭합니다.  
  
2.  **프로젝트** 메뉴에서 *ProjectName* **속성**을 클릭합니다.  
  
3.  **게시** 페이지를 클릭한 다음 **필수 구성 요소**를 클릭합니다.  
  
4.  **업데이트 동의 대화 상자**를 선택합니다.  
  
    > [!NOTE]
    >  필수 구성 요소 대화 상자에 업데이트 동의 대화 상자가 표시되도록 하려면 Visual Studio를 닫은 다음 다시 열어야 할 수 있습니다.  
  
5.  **확인**을 클릭합니다.  
  
## 설치 프로그램 만들기 및 테스트  
 업데이트 동의 응용 프로그램을 필수 구성 요소로 설정한 다음에는 응용 프로그램을 위한 설치 관리자와 부트스트래퍼를 생성할 수 있습니다.  
  
#### 설치 프로그램을 만들고 동의함을 클릭하지 않는 경우를 테스트하려면  
  
1.  **솔루션 탐색기**에서 배포할 응용 프로그램의 이름을 클릭합니다.  
  
2.  **프로젝트** 메뉴에서 *ProjectName* **속성**을 클릭합니다.  
  
3.  **게시** 페이지를 클릭한 다음 **지금 게시**를 클릭합니다.  
  
4.  게시 출력이 자동으로 열리지 않으면 게시 출력을 찾아 이동합니다.  
  
5.  Setup.exe 프로그램을 실행합니다.  
  
     업데이트 동의 대화 상자 소프트웨어 사용권 계약이 표시됩니다.  
  
6.  소프트웨어 사용권 계약을 읽은 후 **동의함**을 클릭합니다.  
  
     업데이트 동의 대화 상자 응용 프로그램이 표시되고 "설치하려는 응용 프로그램은 웹에서 최신 업데이트를 확인합니다.  동의함을 클릭하면 응용 프로그램에 인터넷에서 자동으로 업데이트를 확인 및 설치할 수 있는 권한을 부여하게 됩니다."라는 텍스트가 표시됩니다.  
  
7.  응용 프로그램을 닫거나 취소를 클릭합니다.  
  
     응용 프로그램에 "*ApplicationName*에 대한 시스템 구성 요소를 설치하는 동안 오류가 발생했습니다.  설치를 계속하려면 모든 시스템 구성 요소가 설치되어 있어야 합니다."라는 오류 메시지가 표시됩니다.  
  
8.  자세히를 클릭하면 "다음 오류가 발생하여 업데이트 동의 대화 상자 구성 요소를 설치하지 못했습니다. "자동 업데이트에 동의하지 않았습니다." 다음 구성 요소를 설치하지 못했습니다. 업데이트 동의 대화 상자"라는 오류 메시지가 표시됩니다.  
  
9. **닫기**를 클릭합니다.  
  
#### 설치 프로그램을 만들고 동의함을 클릭하는 경우를 테스트하려면  
  
1.  **솔루션 탐색기**에서 배포할 응용 프로그램의 이름을 클릭합니다.  
  
2.  **프로젝트** 메뉴에서 *ProjectName* **속성**을 클릭합니다.  
  
3.  **게시** 페이지를 클릭한 다음 **지금 게시**를 클릭합니다.  
  
4.  게시 출력이 자동으로 열리지 않으면 게시 출력을 찾아 이동합니다.  
  
5.  Setup.exe 프로그램을 실행합니다.  
  
     업데이트 동의 대화 상자 소프트웨어 사용권 계약이 표시됩니다.  
  
6.  소프트웨어 사용권 계약을 읽은 후 **동의함**을 클릭합니다.  
  
     업데이트 동의 대화 상자 응용 프로그램이 표시되고 "설치하려는 응용 프로그램은 웹에서 최신 업데이트를 확인합니다.  동의함을 클릭하면 응용 프로그램에 인터넷에서 자동으로 업데이트를 확인 및 설치할 수 있는 권한을 부여하게 됩니다."라는 텍스트가 표시됩니다.  
  
7.  **동의함**을 클릭한 다음 **계속**을 클릭합니다.  
  
     응용 프로그램 설치가 시작됩니다.  
  
8.  응용 프로그램 설치 대화 상자가 표시되면 **설치**를 클릭합니다.  
  
## 참고 항목  
 [응용 프로그램 배포 필수 구성 요소](../deployment/application-deployment-prerequisites.md)   
 [부트스트래퍼 패키지 만들기](../deployment/creating-bootstrapper-packages.md)   
 [방법: 제품 매니페스트 만들기](../deployment/how-to-create-a-product-manifest.md)   
 [방법: 패키지 매니페스트 만들기](../deployment/how-to-create-a-package-manifest.md)   
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)