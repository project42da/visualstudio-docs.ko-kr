---
title: "방법: 비주얼 스타일을 사용하여 WPF 응용 프로그램 게시 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 73b22b02-fc75-42aa-82d3-51fdcaf8e5c8
caps.latest.revision: 3
caps.handback.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
---
# 방법: 비주얼 스타일을 사용하여 WPF 응용 프로그램 게시
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

비주얼 스타일은 공용 컨트롤의 모양이 사용자가 선택한 테마에 따라 변경할 수 있도록 합니다.  기본적으로 WPF\(Windows Presentation Foundation\) 응용 프로그램의 경우 가상 스타일이 사용되지 않으므로 수동으로 사용하도록 설정해야 합니다.  하지만 WPF 응용 프로그램에 비주얼 스타일을 사용하도록 설정하면 솔루션을 게시할 때 오류가 발생합니다.  이 토픽에서는 사용하고 있는 시각적 스타일을 가지고 있는 WPF 애플리케이션을 게시하기 위하여 이 오류와 프로세스를 해결하는 방법에 관하여 설명하고 있습니다.  비주얼 스타일에 대한 자세한 내용은 [Visual Styles Overview](http://msdn.microsoft.com/ko-kr/5b5d7bb6-684f-478d-bf5f-b8d18bbcff2e)을 참조하십시오.  오류 메시지에 대한 자세한 내용은 [ClickOnce 배포 관련 오류 문제 해결](../deployment/troubleshooting-specific-errors-in-clickonce-deployments.md)를 참조하십시오.  
  
 이 오류를 해결하고 솔루션을 게시하려면 다음 작업을 수행해야 합니다.  
  
-   [사용가능한 비주얼 스타일 없이 솔루션을 게시하려면](#BKMK_publishsolwovs)  
  
-   [매니페스트 파일을 생성하려면.](#BKMK_CreateManifest).  
  
-   [게시된 솔루션의 실행 파일에 매니페스트 파일을 포함하려면](#BKMK_embedmanifest)  
  
-   [응용 프로그램 및 배포 매니페스트에 서명하려면](#BKMK_signappdeplyman).  
  
 이어 발행된 파일들을 여러분이 최종 사용자들이 그 애플리케이션을 설치하기를 원하는 곳으로부터 해당 장소까지 이동시킬 수 있습니다.  
  
##  <a name="BKMK_publishsolwovs"></a> 사용가능한 비주얼 스타일 없이 솔루션을 게시하려면  
  
1.  프로젝트에 비주얼 스타일을 사용하도록 설정하지 않았는지 확인합니다.  먼저 프로젝트의 매니페스트 파일에서 다음 XML을 확인합니다.  그런 다음 XML이 있는 경우 XML을 주석 태그로 묶습니다.  
  
     비주얼 스타일은 기본적으로 사용되지 않습니다.  
  
    ```  
    <dependency>    <dependentAssembly>      <assemblyIdentity          type="win32"          name="Microsoft.Windows.Common-Controls"          version="6.0.0.0"          processorArchitecture="*"          publicKeyToken="6595b64144ccf1df"          language="*"        />    </dependentAssembly>  </dependency>  
    ```  
  
     다음 절차에서는 프로젝트와 관련된 매니페스트 파일을 여는 방법을 보여 줍니다.  
  
    ###### Visual Basic 프로젝트에서 매니페스트 파일을 열려면  
  
    1.  메뉴 모음에서 **프로젝트**, *ProjectName***속성** 을 선택합니다. 여기서 *ProjectName* 은 WPF 프로젝트의 이름입니다.  
  
         WPF 프로젝트에 대한 속성 페이지가 나타납니다.  
  
    2.  **응용 프로그램** 탭에서 **Windows 설정 보기**를 선택합니다.  
  
         app.manifest 파일이 **코드 편집기**에서 열립니다.  
  
    ###### C\# 프로젝트에서 매니페스트 파일을 열려면  
  
    1.  메뉴 모음에서 **프로젝트**, *ProjectName***속성** 을 선택합니다. 여기서 *ProjectName* 은 WPF 프로젝트의 이름입니다.  
  
         WPF 프로젝트에 대한 속성 페이지가 나타납니다.  
  
    2.  **응용 프로그램** 탭에서 매니페스트 필드에 나타나는 이름을 적어 둡니다.  이것은 프로젝트와 연관된 매니페스트 이름입니다.  
  
        > [!NOTE]
        >  매니페스트 필드에 **기본 설정으로 구성된 매니페스트 포함** 또는 **매니페스트 없이 응용 프로그램 만들기**가 나타날 경우 비주얼 스타일을 사용할 수 없습니다.  매니페스트 필드에 매니페스트 파일 이름이 나타나는 경우 이 절차에서 다음 단계를 진행합니다.  
  
    3.  **솔루션 탐색기**에서 **모든 파일 표시** 를 선택합니다.  
  
         이 버튼은 제외된 항목과 보통 감추어진 항목들을 포함하여 모든 프로젝트 항목들을 보여줍니다.  매니페스트 파일은 프로젝트 항목으로 표시됩니다.  
  
2.  솔루션을 빌드하고 게시합니다.  솔루션을 게시하는 방법에 대한 자세한 내용은 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)을 참조하십시오.  
  
##  <a name="BKMK_CreateManifest"></a> 매니페스트 파일을 생성하려면.  
  
1.  다음 XML을 메모장 파일에 붙여넣습니다.  
  
     이 XML은 비주얼 스타일을 지원하는 컨트롤을 포함한 어셈블리를 설명합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?><asmv1:assembly manifestVersion="1.0"                xmlns="urn:schemas-microsoft-com:asm.v1"                xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"                xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"                xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  <dependency>    <dependentAssembly>      <assemblyIdentity        type="win32"        name="Microsoft.Windows.Common-Controls"        version="6.0.0.0"        processorArchitecture="*"        publicKeyToken="6595b64144ccf1df"        language="*"        />    </dependentAssembly>  </dependency></asmv1:assembly>  
    ```  
  
2.  메모장에서 **파일**을 클릭한 다음 **다른 이름으로 저장**을 클릭합니다.  
  
3.  **다른 이름으로 저장** 대화 상자의 **파일 형식** 드롭다운 목록에서 **모든 파일**을 선택합니다.  
  
4.  **파일 이름** 상자에 파일 이름을 지정하고 파일 이름 끝에 .manifest를 추가합니다.  예: themes.manifest  
  
5.  **폴더 찾아보기** 단추를 선택하여 폴더를 선택한 다음 **저장**을 클릭합니다.  
  
    > [!NOTE]
    >  나머지 절차는 이 파일의 이름은 themes.manifest 이고, C:\\temp 경로에 파일이 저장된다는 가정 아래 수행됩니다.  
  
##  <a name="BKMK_embedmanifest"></a> 게시된 솔루션의 실행 파일에 매니페스트 파일을 포함하려면  
  
1.  **Visual Studio 명령 프롬프트**를 엽니다.  
  
     **Visual Studio 명령 프롬프트**를 여는 방법에 대한 자세한 내용은 [명령 프롬프트](../Topic/Developer%20Command%20Prompt%20for%20Visual%20Studio.md)를 참조하십시오.  
  
    > [!NOTE]
    >  나머지 단계는 솔루션에 대해 다음과 같은 가정을 합니다.  
    >   
    >  -   솔루션 이름은 MyWPFProject입니다.  
    > -   솔루션은 `%UserProfile%\Documents\Visual Studio 2010\Projects\` 디렉터리에 있습니다.  
    >   
    >      솔루션은 `%UserProfile%\Documents\Visual Studio 2010\Projects\publish` 디렉터리에 게시됩니다.  
    > -   게시 된 응용 프로그램 파일의 최신 버전은 다음 디렉터리에 있습니다.: `%UserProfile%\Documents\Visual Studio 2010\Projects\publish\Application Files\WPFApp_1_0_0_0`  
    >   
    >  위에서 설명한 이름 또는 디렉터리 위치를 사용하지 않아도 됩니다.  위에서 설명한 위치와 이름은 솔루션을 게시 하는데 필요한 단계를 설명 하기 위해 사용 됩니다.  
  
2.  명령 프롬프트에서 게시된 응용 프로그램 파일의 최신 버전을 포함하고 있는 디렉터리 경로를 변경합니다.  다음 예제에서는 이 단계를 보여 줍니다.  
  
    ```  
    cd "%UserProfile%\Documents\Visual Studio 2010\Projects\MyWPFProject\publish\Application Files\WPFApp_1_0_0_0"  
    ```  
  
3.  명령 프롬프트에서 다음 명령을 실행하여 매니페스트 파일을 응용 프로그램의 실행 파일에 포함시킵니다.  
  
    ```  
    mt –manifest c:\temp\themes.manifest –outputresource:MyWPFApp.exe.deploy  
    ```  
  
##  <a name="BKMK_signappdeplyman"></a> 응용 프로그램 및 배포 매니페스트에 서명하려면  
  
1.  명령 프롬프트에서 다음 명령을 실행하여 현재 디렉터리의 실행 파일에서 `.deploy` 확장을 제거합니다.  
  
    ```  
    ren MyWPFApp.exe.deploy MyWPFApp.exe  
    ```  
  
    > [!NOTE]
    >  이 예제에서는 파일 한 개에만 `.deploy` 파일 확장명이 있다고 가정합니다.  이 디렉터리에서 파일 확장명이 `.deploy`인 파일 이름을 모두 바꿀지 확인합니다.  
  
2.  명령 프롬프트에서 다음 명령을 실행하여 응용 프로그램 매니페스트에 서명합니다.  
  
    ```  
    mage -u MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx  
    ```  
  
    > [!NOTE]
    >  이 예제에서는 프로젝트의 `.pfx` 파일을 사용하여 매니페스트에 서명한다고 가정합니다.  매니페스트에 서명하지 않는 경우 이 예제에 사용된 `–cf` 매개 변수를 생략할 수 있습니다.  암호가 필요한 인증서로 매니페스트에 서명하는 경우 `–password` 옵션\(`For example: mage –u MyWPFApp.exe.manifest –cf ..\..\..\MyWPFApp_TemporaryKey.pfx – password Password`\)을 지정하십시오.  
  
3.  명령 프롬프트에서 다음 명령을 실행하여 `.deploy` 확장을 이 절차의 이전 단계에서 이름을 바꾼 파일의 이름에 추가합니다.  
  
    ```  
    ren MyWPFApp.exe MyWPFApp.exe.deploy  
    ```  
  
    > [!NOTE]
    >  이 예제에서는 파일 한 개에만 `.deploy` 파일 확장명이 있다고 가정합니다.  이 디렉터리에서 이전 파일 확장명이 `.deploy`이었던 파일의 이름을 모두 바꾸었는지 확인하십시오.  
  
4.  명령 프롬프트에서 다음 명령을 실행하여 배포 매니페스트에 서명합니다.  
  
    ```  
    mage -u ..\..\MyWPFApp.application -appm MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx  
    ```  
  
    > [!NOTE]
    >  이 예제에서는 프로젝트의 `.pfx` 파일을 사용하여 매니페스트에 서명한다고 가정합니다.  매니페스트에 서명하지 않는 경우 이 예제에 사용된 `–cf` 매개 변수를 생략할 수 있습니다.  암호가 필요한 인증서로 매니페스트에 서명하는 경우 이 예\(`For example: mage –u MyWPFApp.exe.manifest –cf ..\..\..\MyWPFApp_TemporaryKey.pfx – password Password`\)와 같이 `–password` 옵션을 지정하십시오.  
  
 다음 단계를 수행한 후 게시된 파일을 최종 사용자가 응용 프로그램을 설치하려는 위치로 이동할 수 있습니다.  솔루션을 자주 업데이트하려는 경우 이러한 명령을 스크립트로 이동하고 새 버전을 게시할 때마다 스크립트를 실행할 수 있습니다.  
  
## 참고 항목  
 [ClickOnce 배포 관련 오류 문제 해결](../deployment/troubleshooting-specific-errors-in-clickonce-deployments.md)   
 [Visual Styles Overview](http://msdn.microsoft.com/ko-kr/5b5d7bb6-684f-478d-bf5f-b8d18bbcff2e)   
 [Enabling Visual Styles](VS|Controls|~\controls\userex\cookbook.htm)   
 [명령 프롬프트](../Topic/Developer%20Command%20Prompt%20for%20Visual%20Studio.md)