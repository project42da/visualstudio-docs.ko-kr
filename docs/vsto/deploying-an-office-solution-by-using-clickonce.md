---
title: "ClickOnce를 사용 하 여 Office 솔루션 배포 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, deploying solutions
- ClickOnce deployment [Office development in Visual Studio], deploying solutions
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: a989fe2bc88d25ad81238b65bf8ecd775c39bc35
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="deploying-an-office-solution-by-using-clickonce"></a>ClickOnce를 사용하여 Office 솔루션 배포
  ClickOnce를 사용하면 Office 솔루션을 더 적은 단계로 배포할 수 있습니다. 업데이트를 게시하는 경우 솔루션에서 자동으로 이를 감지하여 설치합니다. 그러나 ClickOnce에서는 컴퓨터의 각 사용자에 대해 별도로 솔루션을 설치하도록 합니다. 따라서 둘 이상의 사용자가 같은 컴퓨터에서 솔루션을 실행하는 경우 Windows Installer(.msi)를 사용하는 것이 좋습니다.  
  
## <a name="in-this-topic"></a>항목 내용  
  
-   [솔루션을 게시](#Publish)  
  
-   [솔루션에 신뢰를 부여 하는 방법을 결정합니다](#Trust)  
  
-   [사용자의 솔루션 설치 지원](#Helping)  
  
-   [최종 사용자의 컴퓨터 (문서 수준 사용자 지정에만 해당)에 솔루션 문서 저장](#Put)  
  
-   [(문서 수준 사용자 지정에만 해당) SharePoint를 실행 하는 서버에 솔루션 문서 저장](#SharePoint)  
  
-   [사용자 지정 설치 관리자 만들기](#Custom)  
  
-   [업데이트 게시](#Update)  
  
-   [솔루션의 설치 위치를 변경 합니다.](#Location)  
  
-   [이전 버전으로 솔루션 롤백](#Roll)  
  
 Windows Installer 파일을 만들어 Office 솔루션을 배포 하는 방법에 대 한 자세한 내용은 참조 [Windows Installer를 사용 하 여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-windows-installer.md)합니다.  
  
##  <a name="Publish"></a>솔루션을 게시  
 사용 하 여 솔루션을 게시할 수는 **게시 마법사** 또는 **프로젝트 디자이너**합니다. 이 절차를 사용 하 여는 **프로젝트 디자이너** 게시 옵션의 전체 집합을 제공 하기 때문에 있습니다. 참조 [마법사 &#40; Office 개발에서 Visual Studio &#41; 게시](../vsto/publish-wizard-office-development-in-visual-studio.md)합니다.  
  
#### <a name="to-publish-the-solution"></a>솔루션을 게시하려면  
  
1.  **솔루션 탐색기**, 프로젝트 이름으로 지정 하는 노드를 선택 합니다.  
  
2.  메뉴 모음에서 **프로젝트**, *ProjectName* **속성**합니다.  
  
3.  에 **프로젝트 디자이너**, 선택는 **게시** 탭 다음 그림에 나와 있습니다.  
  
     ![프로젝트 디자이너의 게시 탭](../vsto/media/vsto-publishtab.png "프로젝트 디자이너의 게시 탭")  
  
4.  에 **폴더 위치 게시 (ftp 서버 또는 파일 경로)** 상자 저장할 폴더의 경로 입력의 **프로젝트 디자이너** 솔루션 파일을 복사 합니다.  
  
     다음과 같은 형식의 경로를 입력할 수 있습니다.  
  
    -   로컬 경로 (예를 들어 *C:\FolderName\FolderName*).  
  
    -   네트워크의 폴더에 균일 한 명명 규칙 (UNC) 경로 (예를 들어  *\\\ServerName\FolderName*).  
  
    -   상대 경로 (예를 들어 *PublishFolder\\*, 기본적으로 프로젝트가 게시 되는 폴더).  
  
5.  에 **설치 폴더 URL** 상자에 최종 사용자가 솔루션을 찾을 위치의 정규화 된 경로 입력 합니다.  
  
     위치를 모르는 아직 경우,이 필드에 아무것도 입력 하지 마십시오. 기본적으로 ClickOnce에서는 사용자가 솔루션을 설치한 폴더에서 업데이트를 찾습니다.  
  
6.  **필수 구성 요소** 단추를 선택합니다.  
  
7.  에 **필수 구성 요소** 대화 상자에서 **필수 구성 요소를 설치 하려면 설치 프로그램 만들기** 확인란을 선택 합니다.  
  
8.  에 **설치할 필수 구성 요소 선택** 목록에 대 한 확인란을 선택 합니다 **Windows Installer 4.5** 및 적절 한.NET Framework 패키지 합니다.  
  
     예를 들어 경우 솔루션의 대상이 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]에 대 한 확인란을 선택 **Windows Installer 4.5** 및 **Microsoft.NET Framework 4.5 Full**합니다.  
  
9. 솔루션은.NET Framework 4.5를 대상으로 하는 경우 선택 된 **Visual Studio 2010 Tools for Office Runtime** 확인란 합니다.  
  
    > [!NOTE]  
    >  이 확인란은 기본적으로 표시 되지 않습니다. 이 확인란을 표시하려면 부트스트래퍼 패키지를 만들어야 합니다. 참조 [Visual Studio 2012를 사용한 Office 2013 VSTO 추가 기능에서 용 부트스트래퍼 패키지를 만드는](http://blogs.msdn.com/b/vsto/archive/2012/12/21/creating-a-bootstrapper-package-for-an-office-2013-vsto-add-in-with-visual-studio-2012.aspx)합니다.  
  
10. 아래 **필수 구성 요소에 대 한 설치 위치 지정**을 표시 한 다음를 선택 하는 옵션 중 하나를 선택 하는 **확인** 단추입니다.  
  
     다음 표는 각 옵션에 대해 설명합니다.  
  
    |옵션|설명|  
    |------------|-----------------|  
    |**구성 요소 공급업체의 웹 사이트에서 필수 구성 요소 다운로드**|사용자에게 공급업체로부터 이러한 필수 구성 요소를 다운로드하여 설치하라는 메시지가 나타납니다.|  
    |**내 응용 프로그램과 동일한 위치에서 필수 구성 요소 다운로드**|필수 구성 요소 소프트웨어가 솔루션과 함께 설치되어 있습니다. 이 옵션을 선택하면 자동으로 모든 필수 구성 요소 패키지가 게시 위치에 복사됩니다. 이 옵션이 작동하려면 필수 구성 요소 패키지가 개발 컴퓨터에 있어야 합니다.|  
    |**다음 위치에서 필수 구성 요소 다운로드**|모든 필수 구성 요소 패키지가 지정한 위치에 복사되고 솔루션을 사용하여 설치됩니다.|  
  
     참조 [필수 구성 요소 대화 상자](/visualstudio/ide/reference/prerequisites-dialog-box)합니다.  
  
11. 선택 된 **업데이트** 단추, 각 최종 사용자의 VSTO 추가 기능 또는 사용자 지정 업데이트를 확인 한 다음 원하는 얼마나 자주 지정는 **확인** 단추입니다.  
  
    > [!NOTE]  
    >  CD 또는 이동식 드라이브를 사용 하 여를 배포 하는 경우 선택 된 **업데이트 확인 안 함** 옵션 단추입니다.  
  
     업데이트를 게시 하는 방법에 대 한 정보를 참조 하십시오. [업데이트 게시](#Update)합니다.  
  
12. 선택 된 **옵션** 단추에서 옵션을 검토는 **옵션** 대화 상자를 선택한 후는 **확인** 단추입니다.  
  
13. 선택 된 **지금 게시** 단추입니다.  
  
     이 절차의 앞부분에서 지정한 게시 폴더에 다음과 같은 폴더 및 파일이 추가됩니다.  
  
    -   **응용 프로그램 파일** 폴더입니다.  
  
    -   설치 프로그램  
  
    -   최신 버전의 배포 매니페스트를 가리키는 배포 매니페스트  
  
     **응용 프로그램 파일** 게시 하는 각 버전에 대 한 하위 폴더 포함 합니다. 각 버전별 하위 폴더에는 다음 파일이 들어 있습니다.  
  
    -   응용 프로그램 매니페스트  
  
    -   배포 매니페스트  
  
    -   사용자 지정 어셈블리  
  
     다음 그림에서는 Outlook VSTO 추가 기능용 게시 폴더의 구조를 보여 줍니다.  
  
     ![게시 폴더 구조](../vsto/media/publishfolderstructure.png "게시 폴더 구조")  
  
    > [!NOTE]  
    >  ClickOnce에서는 인터넷 정보 서비스 (IIS)의 보안된 설치 안전 하지 않은 확장명 때문에 파일을 차단 하지 않도록 어셈블리에.deploy 확장명을 추가 합니다. 사용자가 솔루션을 설치하면 .deploy 확장명이 제거됩니다.  
  
14. 이 절차의 앞부분에서 지정한 설치 위치에 솔루션 파일을 복사합니다.  
  
##  <a name="Trust"></a>솔루션에 신뢰를 부여 하는 방법을 결정합니다  
 사용자 컴퓨터에서 솔루션을 실행하려면 먼저 관리자가 신뢰를 부여하거나 사용자가 솔루션을 설치할 때 신뢰 프롬프트에 응답해야 합니다. 솔루션에 신뢰를 부여하려면 신뢰할 수 있고 확인된 게시자를 식별하는 인증서를 사용하여 매니페스트에 서명합니다. 참조 [매니페스트 응용 프로그램 및 배포에 서명 하 여 솔루션 신뢰](../vsto/granting-trust-to-office-solutions.md#Signing)합니다.  
  
 문서 수준 사용자 지정을 배포 하는 경우 사용자의 컴퓨터에는 폴더에 문서를 저장 하거나 SharePoint 사이트에서 문서를 사용할 수 있도록 하려면 Office에서 문서의 위치를 신뢰 해야 합니다. 참조 [문서에 신뢰 부여](../vsto/granting-trust-to-documents.md)합니다.  
  
##  <a name="Helping"></a>사용자의 솔루션 설치 지원  
 사용자는 설치 프로그램을 실행하고 배포 매니페스트를 열거나 문서 수준 사용자 지정의 경우 문서를 직접 열어 솔루션을 설치할 수 있습니다. 가장 좋은 방법은 사용자가 설치 프로그램을 사용하여 솔루션을 설치하는 것입니다. 다른 두 방법에서는 필수 구성 요소 소프트웨어가 설치 되어 있는지 보장할 수 없습니다. 사용자가 설치 위치에서 문서를 열려는 경우, Office 응용 프로그램의 보안 센터에서 신뢰할 수 있는 위치 목록에 이 문서를 추가해야 합니다.  
  
### <a name="opening-the-document-of-a-document-level-customization"></a>문서 수준 사용자 지정의 문서 열기  
 사용자는 문서 수준 사용자 지정의 문서를 설치 위치에서 바로 열거나 문서를 자신의 로컬 컴퓨터로 복사한 다음 이 복사본을 열 수 있습니다.  
  
 가장 좋은 방법은 여러 사용자가 동시에 동일한 복사본을 열려고 시도하지 않도록 사용자가 자신의 컴퓨터에서 문서의 복사본을 여는 것입니다. 이 방법을 적용하려면 사용자 컴퓨터에 문서를 복사하도록 설치 프로그램을 구성하면 됩니다. 참조 [최종 사용자의 컴퓨터 (문서 수준 사용자 지정에만 해당)에 솔루션 문서 저장](#Put)합니다.  
  
### <a name="installing-the-solution-by-opening-the-deployment-manifest-from-an-iis-website"></a>IIS 웹 사이트에서 배포 매니페스트를 열어서 솔루션 설치  
 사용자는 웹에서 배포 매니페스트를 열어 Office 솔루션을 설치할 수 있습니다. 그러나 IIS(인터넷 정보 서비스)의 보안 설치 기능에서는 확장명이 .vsto인 파일을 차단합니다. 따라서 IIS를 사용하여 Office 솔루션을 배포하려면 먼저 IIS에서 MIME 형식을 정의해야 합니다.  
  
##### <a name="to-add-the-vsto-mime-type-to-iis-60"></a>IIS 6.0에 .vsto MIME 형식을 추가하려면  
  
1.  IIS 6.0을 실행 하는 서버의 선택 **시작**, **모든 프로그램**, **관리 도구**, **인터넷정보서비스(IIS)관리자**.  
  
2.  컴퓨터 이름을 선택 된 **웹사이트** 폴더 또는 웹 사이트를 구성 하는 합니다.  
  
3.  메뉴 모음에서 **동작**, **속성**합니다.  
  
4.  에 **HTTP 헤더** 탭, 선택는 **MIME 형식을** 단추입니다.  
  
5.  에 **MIME 형식을** 창 선택는 **새로** 단추입니다.  
  
6.  에 **MIME 형식을** 창 입력 **.vsto** 확장명으로 입력 **응용 프로그램/x-ms-vsto** MIME로 입력 한 다음 새로운 설정을 적용 합니다.  
  
    > [!NOTE]  
    >  변경 내용이 적용되려면 World Wide Web Publishing 서비스를 다시 시작하거나 작업자 프로세스가 재생될 때까지 기다려야 합니다. 그런 다음 브라우저의 디스크 캐시를 플러시하고 .vsto 파일을 다시 열어 봅니다.  
  
##### <a name="to-add-the-vsto-mime-type-to-iis-70"></a>IIS 7.0에 .vsto MIME 형식을 추가하려면  
  
1.  IIS 7.0을 실행 하는 서버의 선택 **시작**, **모든 프로그램**, **액세서리**합니다.  
  
2.  에 대 한 바로 가기 메뉴를 열고 **명령 프롬프트**를 선택한 후 **관리자 권한으로 실행 합니다.**  
  
3.  에 **열려** 상자에 다음 경로 입력 한 다음 선택에서 **확인** 단추입니다.  
  
    ```  
    %windir%\system32\inetsrv   
    ```  
  
4.  다음 명령을 입력한 다음 새로운 설정을 적용합니다.  
  
    ```  
    set config /section:staticContent /+[fileExtension='.vsto',mimeType='application/x-ms-vsto']  
    ```  
  
    > [!NOTE]  
    >  변경 내용이 적용되려면 World Wide Web Publishing 서비스를 다시 시작하거나 작업자 프로세스가 재생될 때까지 기다려야 합니다. 그런 다음 브라우저의 디스크 캐시를 플러시하고 .vsto 파일을 다시 열어 봅니다.  
  
##  <a name="Put"></a>최종 사용자의 컴퓨터 (문서 수준 사용자 지정에만 해당)에 솔루션 문서 저장  
 배포 후 작업을 만들어 최종 사용자의 컴퓨터에 솔루션의 문서에 복사할 수 있습니다. 이런 방식으로 사용자는 수동으로 복사 문서 설치 위치에서 자신의 컴퓨터에 솔루션을 설치한 후 필요가 없습니다. 배포 후 작업을 정의 하는 클래스를 생성, 빌드 및 솔루션을 게시할 응용 프로그램 매니페스트를 수정 및 응용 프로그램 및 배포 매니페스트에 다시 서명 해야 합니다.  
  
 다음 절차에서 프로젝트 이름의 임을 가정 **ExcelWorkbook** 솔루션을 게시 하 고는 **C:\publish** 컴퓨터에 디렉터리입니다.  
  
### <a name="create-a-class-that-defines-the-post-deployment-action"></a>배포 후 작업을 정의하는 클래스를 만듭니다.  
  
1.  메뉴 모음에서 **파일**, **추가**, **새 프로젝트**를 차례로 선택합니다.  
  
2.  에 **새 프로젝트 추가** 대화 상자는 **설치 된 템플릿** 창에서 선택 된 **Windows** 폴더.  
  
3.  에 **템플릿** 창, 선택는 **클래스 라이브러리** 서식 파일입니다.  
  
4.  에 **이름** 필드에, 입력 **FileCopyPDA**, 선택한 후는 **확인** 단추입니다.  
  
5.  **솔루션 탐색기**, 선택는 **FileCopyPDA** 프로젝트.  
  
6.  메뉴 모음에서 **프로젝트**, **참조 추가**를 선택합니다.  
  
7.  에 **.NET** 탭에서 Microsoft.VisualStudio.Tools.Applications.Runtime 및 Microsoft.VisualStudio.Tools.Applications.ServerDocument에 대 한 참조를 추가 합니다.  
  
8.  클래스 이름을 `FileCopyPDA`로 바꾼 다음 파일의 내용을 이 코드로 바꿉니다. 이 코드는 다음 작업을 수행합니다.  
  
    -   사용자의 바탕 화면에 문서를 복사합니다.  
  
    -   배포 매니페스트에 대 한 정규화 된 경로에 상대 경로에서 _AssemblyLocation 속성을 변경합니다.  
  
    -   사용자가 솔루션을 제거한 경우 파일을 삭제합니다.  
  
     [!code-vb[Trin_ExcelWorkbookPDA#7](../vsto/codesnippet/VisualBasic/trin_excelworkbookpda/filecopypda/class1.vb#7)]
     [!code-csharp[Trin_ExcelWorkbookPDA#7](../vsto/codesnippet/CSharp/trin_excelworkbookpda/filecopypda/class1.cs#7)]  
  
### <a name="build-and-publish-the-solution"></a>솔루션을 빌드하고 게시합니다.  
  
1.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **FileCopyPDA** 프로젝트를 선택한 후 **빌드**합니다.  
  
2.  에 대 한 바로 가기 메뉴를 열고는 **ExcelWorkbook** 프로젝트를 선택한 후 **빌드**합니다.  
  
3.  에 대 한 바로 가기 메뉴를 열고는 **ExcelWorkbook** 프로젝트를 선택한 후 **참조 추가**합니다.  
  
4.  에 **참조 추가** 대화 상자에서 선택 하는 **프로젝트** 탭을 선택 **FileCopyPDA**, 선택한 후는 **확인** 단추입니다.  
  
5.  **솔루션 탐색기**, 선택는 **ExcelWorkbook** 프로젝트.  
  
6.  메뉴 모음에서 **프로젝트**, **새 폴더**합니다.  
  
7.  Enter **데이터**, Enter 키를 선택 합니다.  
  
8.  **솔루션 탐색기**, 선택는 **데이터** 폴더입니다.  
  
9. 메뉴 모음에서 **프로젝트**, **기존 항목 추가**합니다.  
  
10. 에 **기존 항목 추가** 대화 상자에 대 한 출력 디렉터리를 찾습니다는 **ExcelWorkbook** 프로젝트는 **ExcelWorkbook.xlsx** 파일을 선택한 다음는 선택 **추가** 단추입니다.  
  
11. **솔루션 탐색기** 선택은 **ExcelWorkbook.xlsx** 파일입니다.  
  
12. 에 **속성** 창에서 변경 된 **빌드 작업** 속성을 **콘텐츠** 및 **출력 디렉터리로 복사** 속성 를 **변경 된 내용만 복사**합니다.  
  
     다음이 단계를 완료 하면 다음 그림을 프로젝트와 비슷합니다.  
  
     ![배포 후 작업의 프로젝트 구조입니다. ] (../vsto/media/vsto-postdeployment.png "프로젝트 배포 후 작업의 구조입니다.")  
  
13. 게시는 **ExcelWorkbook** 프로젝트.  
  
### <a name="modify-the-application-manifest"></a>응용 프로그램 매니페스트 수정  
  
1.  열기는 **c:\publish** 를 사용 하 여 디렉터리 **파일 탐색기**합니다.  
  
2.  열기는 **응용 프로그램 파일** 게시 된 버전의 솔루션 폴더를 연 다음 가장 최근의에 해당 하는 폴더를 엽니다.  
  
3.  열기는 **ExcelWorkbook.dll.manifest** 메모장과 같은 텍스트 편집기에서 파일입니다.  
  
4.  `</vstav3:update>` 요소 뒤에 다음 코드를 추가합니다. 클래스 특성에 대 한는 `<vstav3:entryPoint>` 요소를 다음 구문을 사용: *NamespaceName.ClassName*합니다. 다음 예제에서는 네임스페이스 및 클래스 이름이 같기 때문에 결과 진입점 이름은 `FileCopyPDA.FileCopyPDA`입니다.  
  
    ```  
    <vstav3:postActions>  
      <vstav3:postAction>  
        <vstav3:entryPoint  
          class="FileCopyPDA.FileCopyPDA">  
          <assemblyIdentity  
            name="FileCopyPDA"  
            version="1.0.0.0"  
            language="neutral"  
            processorArchitecture="msil" />  
        </vstav3:entryPoint>  
        <vstav3:postActionData>  
        </vstav3:postActionData>  
      </vstav3:postAction>  
    </vstav3:postActions>  
    ```  
  
### <a name="re-sign-the-application-and-deployment-manifests"></a>응용 프로그램 및 배포 매니페스트 다시 서명  
  
1.  에 **%USERPROFILE%\Documents\Visual Studio 2013 \ projects\excelworkbook\excelworkbook** 폴더에서는 **ExcelWorkbook_TemporaryKey.pfx** 인증서 파일을 복사한 후에  *PublishFolder* **\application**\__MostRecentPublishedVersion_ 폴더입니다.
  
2.  Visual Studio 명령 프롬프트를 열고 디렉터리는 **c:\publish\Application Files\ExcelWorkbook**\__MostRecentPublishedVersion_ 폴더 (예를 들어 **c:\publish\Application Files\ExcelWorkbook_1_0_0_4**).  
  
3.  다음 명령을 실행하여 수정된 응용 프로그램 매니페스트에 서명합니다.  
  
    ```  
    mage -sign ExcelWorkbook.dll.manifest -certfile ExcelWorkbook_TemporaryKey.pfx  
    ```  
  
     "ExcelWorkbook.dll.manifest에 서명했습니다"라는 메시지가 나타납니다.  
  
4.  변경 된 **c:\publish** 다음 명령을 실행 하 여 폴더를 다음 업데이트 및 기호 배포 매니페스트:  
  
    ```  
    mage -update ExcelWorkbook.vsto -appmanifest "Application Files\Ex  
    celWorkbookMostRecentVersionNumber>\ExcelWorkbook.dll.manifest" -certfile "Application Files\ExcelWorkbookMostRecentVersionNumber>\ExcelWorkbook_TemporaryKey.pfx"  
    ```  
  
    > [!NOTE]  
    >  앞의 예제에서 MostRecentVersionNumber 솔루션의 가장 최근에 게시 된 버전의 버전 번호로 바꿉니다 (예를 들어 **1_0_0_4**).  
  
     "ExcelWorkbook.vsto에 서명했습니다."라는 메시지가 나타납니다.  
  
5.  ExcelWorkbook.vsto 파일을 복사는 **c:\publish\Application Files\ExcelWorkbook**\__MostRecentVersionNumber_ 디렉터리입니다.  
  
##  <a name="SharePoint"></a>(문서 수준 사용자 지정에만 해당) SharePoint를 실행 하는 서버에 솔루션 문서 저장  
 SharePoint를 사용하여 최종 사용자에게 문서 수준 사용자 지정을 게시할 수 있습니다. 사용자가 SharePoint 사이트에서 문서를 열면 런타임에 자동으로 공유 네트워크 폴더의 솔루션을 사용자의 로컬 컴퓨터에 설치합니다. 솔루션이 로컬로 설치된 후, 문서가 바탕 화면과 같은 다른 위치에 복사되는 경우에도 사용자 지정은 계속 작동합니다.  
  
#### <a name="to-put-the-document-on-a-server-thats-running-sharepoint"></a>SharePoint를 실행하는 서버에 문서를 저장하려면  
  
1.  SharePoint 사이트의 문서 라이브러리에 솔루션 문서를 추가합니다.  
  
2.  다음 방법 중 하나에 해당하는 단계를 수행합니다.  
  
    -   Office 구성 도구를 사용하여 모든 사용자 컴퓨터에 있는 Word 또는 Excel의 보안 센터에 SharePoint 실행 서버를 추가합니다.  
  
         참조 [보안 정책 및 Office 2010의 설정을](http://go.microsoft.com/fwlink/?LinkId=99227)합니다.  
  
    -   각 사용자는 다음 단계를 수행해야 합니다.  
  
        1.  Word 또는 Excel을 열고 로컬 컴퓨터의 선택은 **파일** 탭을 선택 합니다는 **옵션** 단추입니다.  
  
        2.  에 **보안 센터** 대화 상자에서 선택 하는 **신뢰할 수 있는 위치** 단추입니다.  
  
        3.  선택 된 **(권장 하지 않음) 내 네트워크 상의 신뢰할 수 있는 위치 허용** 확인란을 선택한 후는 **새 위치 추가** 단추 합니다.  
  
        4.  에 **경로** 상자에 업로드 한 문서가 포함 된 SharePoint 문서 라이브러리의 URL을 입력 합니다 (예를 들어 *http://SharePointServerName/TeamName/ProjectName/DocumentLibraryName*).  
  
             Default.aspx 나 AllItems.aspx와 같은 기본 웹 페이지의 이름을 추가 하지 마십시오.  
  
        5.  선택 된 **이 위치의 하위 폴더도 신뢰할 수 있는 사항도** 확인란을 선택한 다음 선택는 **확인** 단추입니다.  
  
             사용자가 SharePoint 사이트에서 문서를 열면 이 문서가 열리고 사용자 지정이 설치됩니다. 사용자는 바탕 화면에 이 문서를 복사할 수 있습니다. 문서의 속성에서 문서의 네트워크 위치를 가리키므로 사용자 지정은 계속 실행됩니다.  
  
##  <a name="Custom"></a>사용자 지정 설치 관리자 만들기  
 솔루션을 게시할를 생성 하는 설치 프로그램을 사용 하는 대신 Office 솔루션에 필요한 사용자 지정 설치 관리자를 만들 수 있습니다. 예를 들어 로그온 스크립트를 사용하여 설치를 시작하거나 사용자 상호 작업 없이 배치 파일을 사용하여 솔루션을 설치할 수 있습니다. 이러한 시나리오는 최종 사용자의 컴퓨터에 필수 구성 요소가 이미 설치된 경우에 가장 적합합니다.  
  
 사용자 지정 설치 프로세스의 일부로, 다음 위치에 기본적으로 설치되어 있는 Office 솔루션용 설치 관리자 도구(VSTOInstaller.exe)가 호출됩니다.  
  
 %commonprogramfiles%\microsoft shared\VSTO\10.0\VSTOInstaller.exe  
  
 이 도구가 해당 위치에 없는 경우, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSTO Runtime Setup\v4\InstallerPath 레지스트리 키나 HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSTO Runtime Setup\v4\InstallerPath 레지스트리 키를 사용하여 이 도구의 경로를 찾을 수 있습니다.  
  
 VSTOinstaller.exe와 함께 다음 매개 변수를 사용할 수 있습니다.  
  
|매개 변수|정의|  
|---------------|----------------|  
|/Install 또는 /I|솔루션을 설치합니다. 이 옵션 뒤에는 배포 매니페스트의 경로가 와야 합니다. 로컬 컴퓨터, UNC(Universal Naming Convention) 파일 공유에 대한 경로를 지정할 수 있습니다. 로컬 경로 지정할 수 있습니다 (*C:\FolderName\PublishFolder*), 상대 경로 (*게시\\*), 또는 정규화 된 위치 (*\\\ServerName\ FolderName* 또는 http://*ServerName/FolderName*).|  
|/Uninstall 또는 /U|솔루션을 제거합니다. 이 옵션 뒤에는 배포 매니페스트의 경로가 와야 합니다. 경로를 로컬 컴퓨터의 UNC 파일 공유로 지정할 수 있습니다. 로컬 경로 지정할 수 있습니다 (*c:\FolderName\PublishFolder*), 상대 경로 (*게시\\*), 또는 정규화 된 위치 (*\\\ServerName\ FolderName* 또는 http://*ServerName/FolderName*).|  
|/Silent 또는 /S|입력에 대한 메시지나 그 밖의 메시지를 사용자에게 표시하지 않고 설치 또는 제거합니다. 신뢰 프롬프트가 필요한 경우 사용자 지정 설치 또는 업데이트 되지 않습니다.|  
|/Help 또는 /?|도움말 정보를 표시합니다.|  
  
 VSTOinstaller.exe를 실행하면 다음과 같은 오류 코드가 나타날 수 있습니다.  
  
|오류 코드|정의|  
|----------------|----------------|  
|0|솔루션이 성공적으로 설치되었거나 제거되었습니다. 또는 VSTOInstaller 도움말이 표시되었습니다.|  
|-100|하나 이상의 명령줄 옵션이 잘못되었거나 두 번 이상 설정되었습니다. 입력에 대 한 자세한 내용은 "vstoinstaller /?" 참조 또는 [ClickOnce Office 솔루션에 대 한 사용자 지정 설치 관리자를 만드는](http://msdn.microsoft.com/en-us/3e5887ed-155f-485d-b8f6-3c02c074085e)합니다.|  
|-101|하나 이상의 명령줄 옵션이 잘못 되었습니다. 자세한 내용을 보려면 "vstoinstaller /?"를 입력하세요.|  
|-200|배포 매니페스트 URI는 유효 하지 않습니다. 자세한 내용을 보려면 "vstoinstaller /?"를 입력하세요.|  
|-201|배포 매니페스트가 잘못 되었으므로 솔루션을 설치할 수 없습니다. 참조 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)합니다.|  
|-202|Visual Studio Tools for Office 섹션이 응용 프로그램 매니페스트의 잘못 되었으므로 솔루션을 설치할 수 없습니다. 참조 [Office 솔루션에 대 한 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)합니다.|  
|-203|다운로드 오류가 발생 했기 때문에 솔루션을 설치할 수 없습니다. 배포 매니페스트의 URI 또는 네트워크 파일 위치를 확인한 다음 다시 시도하세요.|  
|-300|보안 예외가 발생 했기 때문에 솔루션을 설치할 수 없습니다. 참조 [Office 솔루션 보안](../vsto/securing-office-solutions.md)합니다.|  
|-400|솔루션을 설치할 수 없습니다.|  
|-401|솔루션을 제거할 수 없습니다.|  
|-500|솔루션을 설치 또는 제거할 수 없거나 배포 매니페스트를 다운로드할 수 없어 작업이 취소되었습니다.|  
  
##  <a name="Update"></a>업데이트 게시  
 솔루션을 업데이트 하려면 다시 게시를 사용 하 여는 **프로젝트 디자이너** 또는 **게시 마법사**, 한 다음 업데이트 된 솔루션의 설치 위치로 복사 합니다. 설치 위치에 파일을 복사하면 이전 파일을 덮어쓰게 됩니다.  
  
 다음에 솔루션을 확인 하는 업데이트에 대 한 것 찾아 새 버전을 자동으로 로드 합니다.  
  
##  <a name="Location"></a>솔루션의 설치 위치를 변경 합니다.  
 솔루션이 게시된 후 설치 경로를 추가하거나 변경할 수 있습니다. 다음 이유 중 하나 이상으로 인해 설치 경로를 변경하려 할 수 있습니다.  
  
-   설치 경로가 알려지기 전에 설치 프로그램을 컴파일한 경우  
  
-   솔루션 파일이 다른 위치에 복사된 경우  
  
-   설치 파일이 호스팅된 서버에 새 이름 또는 위치가 있는 경우  
  
 솔루션의 설치 경로를 변경하려면 설치 프로그램을 업데이트한 다음 사용자가 이를 실행해야 합니다. 문서 수준 사용자 지정의 경우, 사용자가 문서의 속성이 새 위치를 가리키도록 업데이트해야 합니다.  
  
> [!NOTE]  
>  가 문서 속성을 업데이트 하도록 요청 하지 않으려면 설치 위치에서 업데이트 된 문서를 가져올 사용자를 요청할 수 있습니다.  
  
#### <a name="to-change-the-installation-path-in-the-setup-program"></a>설치 프로그램에서 설치 경로를 변경하려면  
  
1.  열기는 **명령 프롬프트** 창 및 디렉터리 설치 폴더로 변경 합니다.  
  
2.  설치 프로그램을 실행하고 새 설치 경로를 문자열로 받아들이는 `/url` 매개 변수를 포함시킵니다.  
  
     다음 예제에서는 Fabrikam 웹 사이트에 있는 위치로 설치 경로를 변경하는 방법을 보여 주지만, 해당 URL을 원하는 경로로 바꿀 수 있습니다.  
  
    ```  
    setup.exe /url="http://www.fabrikam.com/newlocation"  
    ```  
  
    > [!NOTE]  
    >  메시지가 표시되어 실행 파일의 시그니처가 무효가 되었음을 알리는 경우, 솔루션 서명에 사용된 인증서는 더 이상 유효하지 않으며 게시자는 알 수 없게 됩니다. 그 결과 사용자는 솔루션의 소스를 신뢰함을 확인한 뒤에야 이를 설치할 수 있게 됩니다.  
  
    > [!NOTE]  
    >  현재 URL 값을 표시하려면 `setup.exe /url`을 실행하세요.  
  
 문서 수준 사용자 지정에 대 한 사용자가 문서를 열 하 고의 _AssemblyLocation 속성을 업데이트 해야 합니다. 다음 단계에서는 사용자가 이 작업을 수행하는 방법을 설명합니다.  
  
#### <a name="to-update-the-assemblylocation-property-in-a-document"></a>문서에서 _AssemblyLocation 속성을 업데이트하려면  
  
1.  에 **파일** 탭에서 선택 **정보**, 다음 그림에 나와 있는 합니다.  
  
     ![Excel의 정보 탭](../vsto/media/vsto-infotab.png "Excel의 정보 탭")  
  
2.  에 **속성** 목록에서 선택 **고급 속성**, 다음 그림에 나와 있는 합니다.  
  
     ![Excel의 고급 속성입니다. ] (../vsto/media/vsto-advanceddocumentproperties.png "Excel에 고급 속성입니다.")  
  
3.  에 **사용자 지정** 탭에 **속성** 목록에서 다음 그림과 같이 _AssemblyLocation을 선택 합니다.  
  
     ![AssemblyLocation 속성입니다. ] (../vsto/media/vsto-assemblylocationproperty.png "The AssemblyLocation 속성입니다.")  
  
     **값** 상자 배포 매니페스트 식별자를 포함 합니다.  
  
4.  입력 형식에서 막대로 뒤에 문서의 정규화 된 경로 식별자 앞 *경로*|*식별자* (예를 들어 *File://ServerName/ 폴더 이름/FileName | 74744e4b-e4d6-41eb-84f7-ad20346fe2d9*합니다.  
  
     이 식별자 형식에 대 한 자세한 내용은 참조 [사용자 지정 문서 속성 개요](../vsto/custom-document-properties-overview.md)합니다.  
  
5.  선택 된 **확인** 단추, 다음을 저장 한 문서를 닫습니다.  
  
6.  /url 매개 변수를 사용하지 않고 설치 프로그램을 실행하여 지정한 위치에 솔루션을 설치합니다.  
  
##  <a name="Roll"></a>이전 버전으로 솔루션 롤백  
 솔루션을 롤백하면 사용자의 해당 솔루션이 이전 버전으로 돌아갑니다.  
  
#### <a name="to-roll-back-a-solution"></a>솔루션을 롤백하려면  
  
1.  솔루션의 설치 위치를 엽니다.  
  
2.  최상위 게시 폴더에서 배포 매니페스트(.vsto 파일)를 삭제합니다.  
  
3.  롤백할 버전의 하위 폴더를 찾습니다.  
  
4.  해당 하위 폴더의 배포 매니페스트를 최상위 게시 폴더에 복사합니다.  
  
     예를 들어, 라고 하는 솔루션을 롤백하려면 **OutlookAddIn1** 버전 1.0.0.0 버전 1.0.0.1에서에서 파일 복사 **OutlookAddIn1.vsto** 에서 **OutlookAddIn1_1_0_0_0** 폴더입니다. 최상위 수준에 파일을 붙여 넣습니다 게시 폴더, 버전별 배포 매니페스트를 덮어쓰게 **OutlookAddIn1_1_0_0_1** 의 합니다.  
  
     다음 그림에서는 이 예제의 게시 폴더 구조를 보여 줍니다.  
  
     ![게시 폴더 구조](../vsto/media/publishfolderstructure.png "게시 폴더 구조")  
  
     다음에 사용자가 응용 프로그램 또는 사용자 지정 문서를 열면 배포 매니페스트 변경 사항이 검색됩니다. 이전 버전의 Office 솔루션은 ClickOnce 캐시에서 실행됩니다.  
  
> [!NOTE]  
>  로컬 데이터는 이전 버전의 솔루션 하나에 대해서만 저장됩니다. 두 버전을 롤백하는 경우 로컬 데이터는 유지 되지 않습니다. 로컬 데이터에 대 한 자세한 내용은 참조 [로컬 액세스 및 ClickOnce 응용 프로그램의 원격 데이터](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)   
 [Office 솔루션 게시](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [방법: ClickOnce를 사용 하 여 Office 솔루션 게시](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)   
 [방법: ClickOnce Office 솔루션 설치](http://msdn.microsoft.com/en-us/14702f48-9161-4190-994c-78211fe18065)   
 [방법: ClickOnce를 사용 하 여 문서 수준 Office 솔루션을 SharePoint 서버에 게시 합니다.](http://msdn.microsoft.com/en-us/2408e809-fb78-42a1-9152-00afa1522e58)   
 [ClickOnce Office 솔루션에 대 한 사용자 지정 설치 관리자 만들기](http://msdn.microsoft.com/en-us/3e5887ed-155f-485d-b8f6-3c02c074085e)  
  
  
