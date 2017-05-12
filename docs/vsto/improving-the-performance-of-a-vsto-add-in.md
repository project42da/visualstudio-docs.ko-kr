---
title: "VSTO 추가 기능의 성능 향상"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 03ef25c2-6308-4737-a655-74bbbb472dc2
caps.latest.revision: 14
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# VSTO 추가 기능의 성능 향상
  Office 응용 프로그램용으로 만드는 VSTO 추가 기능을 최적화하여 신속하게 시작하고, 종료하고, 항목을 열고, 다른 작업을 수행할 수 있는 향상된 환경을 사용자에게 제공할 수 있습니다. VSTO 추가 기능이 Outlook용인 경우 낮은 성능 때문에 VSTO 추가 기능이 사용하지 않도록 설정될 가능성도 줄일 수 있습니다. 다음 전략을 실행하여 VSTO 추가 기능의 성능을 높일 수 있습니다.  
  
-   [요청 시 VSTO 추가 기능 로드](#Load)  
  
-   [Windows Installer를 사용하여 Office 솔루션 게시](#Publish)  
  
-   [리본 리플렉션 우회](#Bypass)  
  
-   [별도의 실행 스레드에서 비용이 많이 드는 작업 수행](#Perform)  
  
 Outlook VSTO 추가 기능을 최적화하는 방법에 대한 자세한 내용은 [VSTO 추가 기능이 사용하도록 설정된 상태를 유지하기 위한 성능 기준](http://go.microsoft.com/fwlink/?LinkID=266503)을 참조하세요.  
  
##  <a name="Load"></a> 요청 시 VSTO 추가 기능 로드  
 다음과 같은 경우에만 로드되도록 VSTO 추가 기능을 구성할 수 있습니다.  
  
-   VSTO 추가 기능이 설치된 후 사용자가 응용 프로그램을 처음으로 시작하는 경우  
  
-   이후에 응용 프로그램을 시작한 후 사용자가 VSTO 추가 기능과 처음으로 상호 작용하는 경우  
  
 예를 들어 사용자가 **내 데이터 가져오기**라는 사용자 지정 단추를 선택할 때 VSTO 추가 기능은 워크시트를 데이터로 채울 수 있습니다. 응용 프로그램은 **내 데이터 가져오기** 단추가 리본에 나타날 수 있도록 VSTO 추가 기능을 적어도 한 번 로드해야 합니다. 그러나 사용자가 다음에 응용 프로그램을 시작할 때는 VSTO 추가 기능이 다시 로드되지 않습니다. VSTO 추가 기능은 사용자가 **내 데이터 가져오기** 단추를 선택할 때만 로드됩니다.  
  
#### 요청 시 VSTO 추가 기능을 로드하도록 ClickOnce 솔루션을 구성하려면  
  
1.  **솔루션 탐색기**에서 프로젝트 노드를 선택합니다.  
  
2.  메뉴 모음에서 **보기**, **속성 페이지**를 선택합니다.  
  
3.  **게시** 탭에서 **옵션** 단추를 선택합니다.  
  
4.  **게시 옵션** 대화 상자에서 **Office 설정** 목록 항목을 선택하고 **요청 시 로드** 옵션을 선택한 다음 **확인** 단추를 선택합니다.  
  
#### 요청 시 VSTO 추가 기능을 로드하도록 Windows Installer 솔루션을 구성하려면  
  
1.  레지스트리에서 *Root*\\Software\\Microsoft\\Office\\*ApplicationName*\\Addins\\*Add\-in ID* 키의 `LoadBehavior` 항목을 **0x10**으로 설정합니다.  
  
     자세한 내용은 [VSTO 추가 기능에 대한 레지스트리 항목](../vsto/registry-entries-for-vsto-add-ins.md)을 참조하세요.  
  
#### 솔루션을 디버그하는 동안 요청 시 VSTO 추가 기능을 로드하도록 솔루션을 구성하려면  
  
1.  *Root*\\Software\\Microsoft\\Office\\*ApplicationName*\\Addins\\*Add\-in ID* 키의 `LoadBehavior` 항목을 **0x10**으로 설정하는 스크립트를 만듭니다.  
  
     다음 코드에서는 이 스크립트의 예제를 보여 줍니다.  
  
    ```  
    [HKEY_CURRENT_USER\Software\Microsoft\Office\Excel\Addins\MyAddIn] "Description"="MyAddIn" "FriendlyName"="MyAddIn" "LoadBehavior"=dword:00000010 "Manifest"="c:\\Temp\\MyAddIn\\bin\\Debug\\MyAddIn.vsto|vstolocal"  
  
    ```  
  
2.  스크립트를 사용하여 레지스트리를 업데이트하는 빌드 후 이벤트를 만듭니다.  
  
     다음 코드에서는 빌드 후 이벤트에 추가할 수 있는 명령 문자열의 예를 보여 줍니다.  
  
    ```  
    regedit /s "$(SolutionDir)$(SolutionName).reg"  
  
    ```  
  
     C\# 프로젝트에서 빌드 후 이벤트를 만드는 방법에 대한 자세한 내용은 [방법: 빌드 이벤트 지정&#40;C&#35;&#41;](~/ide/how-to-specify-build-events-csharp.md)을 참조하세요.  
  
     Visual Basic 프로젝트에서 빌드 후 이벤트를 만드는 방법에 대한 자세한 내용은 [방법: 빌드 이벤트 지정&#40;C&#35;&#41;](~/ide/how-to-specify-build-events-csharp.md)을 참조하세요.  
  
##  <a name="Publish"></a> Windows Installer를 사용하여 Office 솔루션 게시  
 Windows Installer를 사용하여 솔루션을 게시하는 경우 Visual Studio 2010 Tools for Office Runtime은 VSTO 추가 기능이 로드될 때 다음 단계를 우회합니다.  
  
-   매니페스트 스키마의 유효성 검사  
  
-   자동으로 업데이트 확인  
  
-   배포 매니페스트의 디지털 서명 유효성 검사  
  
    > [!NOTE]  
    >  이 방법은 VSTO 추가 기능을 사용자 컴퓨터의 안전한 위치에 배포하는 경우 필요하지 않습니다.  
  
 자세한 내용은 [Windows Installer를 사용하여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-windows-installer.md)을 참조하십시오.  
  
##  <a name="Bypass"></a> 리본 리플렉션 우회  
 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)]를 사용하여 솔루션을 빌드하는 경우 솔루션을 배포할 때 사용자가 최신 버전의 Visual Studio 2010 Tools for Office Runtime을 설치했는지 확인하세요. 이 런타임의 이전 버전은 리본 사용자 지정을 찾기 위해 솔루션 어셈블리에 리플렉션합니다. 이 프로세스로 인해 VSTO 추가 기능이 더 느리게 로드될 수 있습니다.  
  
 다른 방법으로, Visual Studio 2010 Tools for Office Runtime의 모든 버전이 리본 사용자 지정을 식별하는 데 리플렉션을 사용하지 못하게 할 수 있습니다. 이 전략을 실행하려면 `CreateRibbonExtensibility` 메서드를 재정의하고 리본 개체를 명시적으로 반환합니다. VSTO 추가 기능에 리본 사용자 지정이 포함되지 않은 경우 이 메서드 내에서 `null`을 반환합니다.  
  
 다음 예제에서는 필드의 값을 기준으로 리본 개체를 반환합니다.  
  
 [!code-csharp[Trin_Ribbon_Choose_Ribbon#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Ribbon_Choose_Ribbon/CS/ThisWorkbook.cs#1)]
 [!code-vb[Trin_Ribbon_Choose_Ribbon#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Ribbon_Choose_Ribbon/VB/ThisWorkbook.vb#1)]  
  
##  <a name="Perform"></a> 별도의 실행 스레드에서 비용이 많이 드는 작업 수행  
 별도의 스레드에서 시간이 많이 걸리는 작업\(예: 장기 실행 작업, 데이터베이스 연결 또는 다른 종류의 네트워크 호출\)을 수행하는 것이 좋습니다. 자세한 내용은 [Office의 스레딩 지원](../vsto/threading-support-in-office.md)을 참조하세요.  
  
> [!NOTE]  
>  Office 개체 모델을 호출하는 모든 코드는 주 스레드에서 실행되어야 합니다.  
  
## 참고 항목  
 [VSTO 추가 기능 요청 시 로드](http://blogs.msdn.com/b/andreww/archive/2008/07/14/demand-loading-vsto-add-ins.aspx)   
 [Office 추가 기능에서 CLR 지연 로드](http://blogs.msdn.com/b/andreww/archive/2008/04/19/delay-loading-the-clr-in-office-add-ins.aspx)   
 [VSTO 성능: 지연 로드 및 사용자\(Stephen Peters\)](http://blogs.msdn.com/b/vsto/archive/2010/01/07/vsto-performance-delay-loading-and-you.aspx)   
 [서비스 팩의 성능이 곧 향상됩니다\(Stephen Peters\)](http://blogs.msdn.com/b/vsto/archive/2010/11/30/performance-improvements-coming-soon-to-a-service-pack-near-you-stephen-peters.aspx)   
 [VSTO 성능: 리본 리플렉션\(Stephen Peters\)](http://blogs.msdn.com/b/vsto/archive/2010/06/03/vsto-performance-ribbon-reflection.aspx)  
  
  