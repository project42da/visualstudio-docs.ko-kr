---
title: '방법: 비주얼 스타일을 사용으로 WPF 응용 프로그램 게시 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
ms.assetid: 73b22b02-fc75-42aa-82d3-51fdcaf8e5c8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0111226fdd3de300265f69930b7e9e56f90876c8
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34816018"
---
# <a name="how-to-publish-a-wpf-application-with-visual-styles-enabled"></a>방법: 비주얼 스타일을 사용하여 WPF 응용 프로그램 게시
비주얼 스타일을 사용자가 선택한 테마에 따라 변경 하는 공용 컨트롤의 모양을 사용 하도록 설정 합니다. 기본적으로 비주얼 스타일은 사용 되지 Windows Presentation Foundation (WPF) 응용 프로그램에 대해 않으므로 수동으로 사용 해야 합니다. 그러나 WPF 응용 프로그램에 대 한 비주얼 스타일을 사용 하도록 설정 하 고 다음 솔루션을 게시 하면 오류가 발생 합니다. 이 항목에서는이 오류 및 사용 하도록 설정 하는 비주얼 스타일으로는 WPF 응용 프로그램을 게시 하기 위한 프로세스를 해결 하는 방법을 설명 합니다. 비주얼 스타일에 대 한 자세한 내용은 참조 [비주얼 스타일 개요](http://msdn.microsoft.com/5b5d7bb6-684f-478d-bf5f-b8d18bbcff2e)합니다. 오류 메시지에 대 한 자세한 내용은 참조 [ClickOnce 배포의 특정 오류 문제 해결](../deployment/troubleshooting-specific-errors-in-clickonce-deployments.md)합니다.  
  
 오류를 해결 하 고 솔루션을 게시 하려면 다음 작업을 수행 해야 합니다.  
  
-   [비주얼 스타일을 사용 하지 않고 솔루션을 게시할](#BKMK_publishsolwovs)합니다.  
  
-   [매니페스트 파일을 만듭니다](#BKMK_CreateManifest)합니다.  
  
-   [게시 된 솔루션의 실행 파일에 매니페스트 파일을 포함](#BKMK_embedmanifest)합니다.  
  
-   [응용 프로그램 및 배포 매니페스트에 서명](#BKMK_signappdeplyman)합니다.  
  
 그런 다음 최종 사용자가 응용 프로그램을 설치 하려는 위치에 게시 된 파일을 이동할 수 있습니다.  
  
##  <a name="BKMK_publishsolwovs"></a> 비주얼 스타일을 사용 하지 않고 솔루션을 게시 합니다.  
  
1.  프로젝트에 비주얼 스타일을 사용 하지 않았는지 확인 합니다. 첫째, 다음 XML에 대 한 프로젝트의 매니페스트 파일을 확인 합니다. 그런 다음 있으면 헤더는 XML 주석 태그를 사용 하 여 XML로 묶습니다.  
  
     기본적으로 시각적 스타일 사용 되지 않습니다.  
  
    ```xml  
    <dependency>    <dependentAssembly>      <assemblyIdentity          type="win32"          name="Microsoft.Windows.Common-Controls"          version="6.0.0.0"          processorArchitecture="*"          publicKeyToken="6595b64144ccf1df"          language="*"        />    </dependentAssembly>  </dependency>  
    ```  
  
     다음 절차에는 프로젝트와 연결 된 매니페스트 파일을 여는 방법을 보여 줍니다.  
  
    ###### <a name="to-open-the-manifest-file-in-a-visual-basic-project"></a>Visual Basic 프로젝트에서 매니페스트 파일을 열려면  
  
    1.  메뉴 모음에서 **프로젝트**, * r o j ***속성**여기서 *p r o j* WPF 프로젝트의 이름입니다.  
  
         WPF 프로젝트에 대 한 속성 페이지가 나타납니다.  
  
    2.  에 **응용 프로그램** 탭에서 선택 **Windows 설정 보기**합니다.  
  
         app.manifest 파일이 열립니다는 **코드 편집기**합니다.  
  
    ###### <a name="to-open-the-manifest-file-in-a-c-project"></a>C# 프로젝트에서 매니페스트 파일을 열려면  
  
    1.  메뉴 모음에서 **프로젝트**, * r o j ***속성**여기서 *p r o j* WPF 프로젝트의 이름입니다.  
  
         WPF 프로젝트에 대 한 속성 페이지가 나타납니다.  
  
    2.  에 **응용 프로그램** 탭에서 매니페스트 필드에 표시 되는 이름을 메모 합니다. 프로젝트와 관련 된 매니페스트의 이름입니다.  
  
        > [!NOTE]
        >  경우 **기본 설정으로 매니페스트 포함** 또는 **매니페스트 없이 응용 프로그램 만들기** 비주얼 스타일을 사용 하지 매니페스트 필드에 표시 합니다. 매니페스트 필드에 매니페스트 파일의 이름이 있는 경우,이 절차의 다음 단계로 진행 합니다.  
  
    3.  **솔루션 탐색기**, 선택 **모든 파일 표시** ().  
  
         이 단추는 모든 프로젝트 항목을 제외 되는 되 고 일반적으로 숨겨져 있는 다른를 포함 하 여 표시 됩니다. 매니페스트 파일을 프로젝트 항목으로 나타납니다.  
  
2.  빌드 및 솔루션을 게시 합니다. 솔루션을 게시 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: ClickOnce 응용 프로그램 게시 마법사를 사용 하 여 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)합니다.  
  
##  <a name="BKMK_CreateManifest"></a> 매니페스트 파일을 만듭니다  
  
1.  메모장 파일에 다음 XML을 붙여 넣습니다.  
  
     이 XML에 비주얼 스타일을 지 원하는 컨트롤을 포함 하는 어셈블리에 설명 합니다.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?><asmv1:assembly manifestVersion="1.0"                xmlns="urn:schemas-microsoft-com:asm.v1"                xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"                xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"                xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  <dependency>    <dependentAssembly>      <assemblyIdentity        type="win32"        name="Microsoft.Windows.Common-Controls"        version="6.0.0.0"        processorArchitecture="*"        publicKeyToken="6595b64144ccf1df"        language="*"        />    </dependentAssembly>  </dependency></asmv1:assembly>  
    ```  
  
2.  메모장에서 **파일**, 클릭 하 고 **다른 이름으로 저장**합니다.  
  
3.  에 **다른 이름으로 저장** 대화 상자는 **파일 형식** 드롭 다운 목록 **모든 파일**합니다.  
  
4.  에 **파일 이름** 상자, 파일 이름을 지정 하 고 추가 **.manifest** 파일 이름의 끝에 있습니다. 예를 들어: **themes.manifest**합니다.  
  
5.  선택 된 **폴더 찾아보기** 단추 모든 폴더를 선택한 다음 클릭 **저장**합니다.  
  
    > [!NOTE]
    >  나머지 절차는이 파일의 이름은 이라고 가정 하겠습니다. **themes.manifest** 및 파일이 컴퓨터의 C:\temp 디렉터리에 저장 됩니다.  
  
##  <a name="BKMK_embedmanifest"></a> 게시 된 솔루션의 실행 파일에 매니페스트 파일을 포함  
  
1.  열기는 **Visual Studio 명령 프롬프트**합니다.  
  
     여는 방법에 대 한 자세한 내용은 **Visual Studio 명령 프롬프트**, 참조 [명령 프롬프트가](/dotnet/framework/tools/developer-command-prompt-for-vs)합니다.  
  
    > [!NOTE]
    >  나머지 단계에는 솔루션에 대 한 다음과 같은 가정을 확인합니다.  
    >   
    >  -   솔루션 이름은 **MyWPFProject**합니다.  
    > -   솔루션은 다음 디렉터리에 있는: `%UserProfile%\Documents\Visual Studio 2010\Projects\`합니다.  
    >   
    >      솔루션은 다음 디렉터리에 게시: `%UserProfile%\Documents\Visual Studio 2010\Projects\publish`합니다.  
    > -   게시 된 응용 프로그램 파일의 최신 버전은 다음 디렉터리에 있습니다. `%UserProfile%\Documents\Visual Studio 2010\Projects\publish\Application Files\WPFApp_1_0_0_0`  
    >   
    >  이름이 나 위에서 설명한 디렉터리 위치를 사용할 필요가 없습니다. 이름 및 위치 위에 설명 된 솔루션을 게시 하는 데 필요한 단계를 설명 하기 위해 사용 됩니다.  
  
2.  명령 프롬프트에서 경로 게시 된 응용 프로그램 파일의 최신 버전을 포함 하는 디렉터리를 변경 합니다. 다음 예제에서는이 단계를 보여 줍니다.  
  
    ```  
cd "%UserProfile%\Documents\Visual Studio 2010\Projects\MyWPFProject\publish\Application Files\WPFApp_1_0_0_0"  
    ```  
  
3.  명령 프롬프트에서 응용 프로그램의 실행 파일에 매니페스트 파일을 포함 하려면 다음 명령을 실행 합니다.  
  
    ```
    mt -manifest c:\temp\themes.manifest -outputresource:MyWPFApp.exe.deploy  
    ```  
  
##  <a name="BKMK_signappdeplyman"></a> 응용 프로그램 및 배포 매니페스트 서명  
  
1.  명령 프롬프트에서 제거 하려면 다음 명령을 실행 하 여 `.deploy` 현재 디렉터리에서 실행 파일에서 확장 합니다.  
  
    ```  
    ren MyWPFApp.exe.deploy MyWPFApp.exe  
    ```  
  
    > [!NOTE]
    >  이 예제에는 파일이 하나만 가정은 `.deploy` 파일 확장명입니다. 이 디렉터리에 있는 모든 파일 이름을 바꿔야 하는 `.deploy` 파일 확장명입니다.  
  
2.  명령 프롬프트에서 응용 프로그램 매니페스트에 서명 하려면 다음 명령을 실행 합니다.  
  
    ```  
    mage -u MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx  
    ```  
  
    > [!NOTE]
    >  이 예에서는 가정를 사용 하 여 매니페스트에 서명 하는 `.pfx` 프로젝트의 파일입니다. 매니페스트 되지 로그인 하는 경우 생략할 수 있습니다는 `-cf` 이 예제에 사용 되는 매개 변수입니다. 암호에 필요한 인증서를 사용 하 여 매니페스트에 서명 하는 경우 지정 된 `-password` 옵션 (`For example: mage -u MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx - password Password`).  
  
3.  명령 프롬프트를 추가 하려면 다음 명령을 실행 하 여 `.deploy` 이 절차의 이전 단계에서 이름을 바꾼 파일의 이름으로 확장 합니다.  
  
    ```  
    ren MyWPFApp.exe MyWPFApp.exe.deploy  
    ```  
  
    > [!NOTE]
    >  이 예에서는 하나의 파일만 가정 했습니다는 `.deploy` 파일 확장명입니다. 이전에이 디렉터리의 모든 파일 이름을 바꿔야 하는 `.deploy` 파일 이름 확장명입니다.  
  
4.  명령 프롬프트에서 배포 매니페스트에 서명 하려면 다음 명령을 실행 합니다.  
  
    ```  
    mage -u ..\..\MyWPFApp.application -appm MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx  
    ```  
  
    > [!NOTE]
    >  이 예에서는 가정를 사용 하 여 매니페스트에 서명 하는 `.pfx` 프로젝트의 파일입니다. 매니페스트 되지 로그인 하는 경우 생략할 수 있습니다는 `-cf` 이 예제에 사용 되는 매개 변수입니다. 암호에 필요한 인증서를 사용 하 여 매니페스트에 서명 하는 경우 지정 된 `-password` 다음이 예제와 같이 옵션을:`For example: mage -u MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx - password Password`합니다.  
  
 다음이 단계를 수행한 후에 최종 사용자가 응용 프로그램을 설치 하려는 위치에 게시 된 파일을 이동할 수 있습니다. 솔루션을 종종 업데이트 하려는 경우 이러한 명령을 스크립트에 이동한 새로운 버전을 게시할 때마다 스크립트를 실행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 배포 관련 오류 문제 해결](../deployment/troubleshooting-specific-errors-in-clickonce-deployments.md)   
 [비주얼 스타일 개요](http://msdn.microsoft.com/5b5d7bb6-684f-478d-bf5f-b8d18bbcff2e)   
 [비주얼 스타일을 사용 하도록 설정](https://msdn.microsoft.com/library/bb773175.aspx)   
 [명령 프롬프트](/dotnet/framework/tools/developer-command-prompt-for-vs)