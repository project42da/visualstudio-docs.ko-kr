---
title: "SharePoint 솔루션 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.Project.WebConfigModificationDialog
- VS.SharePointTools.Project.DebuggingNotEnabled
dev_langs:
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, debugging
ms.assetid: 5120f21e-4c27-4906-b982-85e9cd5170e6
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 14a3c7a2676c786e631b4c8b471272185b81e36c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-sharepoint-solutions"></a>SharePoint 솔루션 디버깅
  사용 하 여 SharePoint 솔루션을 디버그할 수는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디버거 합니다. 디버깅을 시작할 때 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 서버에 프로젝트 파일을 배포 하 고 다음 웹 브라우저에서 SharePoint 사이트의 인스턴스를 엽니다. 다음 섹션에서 SharePoint 응용 프로그램을 디버깅 하는 방법을 설명 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
-   [디버깅 사용](#EnableDebug)  
  
-   [F5 디버깅 및 배포 프로세스](#Deployment)  
  
-   [SharePoint 프로젝트 기능](#Features)  
  
-   [워크플로 디버깅](#Workflow)  
  
-   [디버깅 기능 이벤트 수신자](#FeatureEvents)  
  
-   [향상 된 디버깅 정보를 사용 하도록 설정](#EnhancedDebug)  
  
##  <a name="EnableDebug"></a>디버깅 사용  
 먼저 SharePoint 솔루션을 디버그할 때 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 대화 상자 알려 web.config 파일 디버깅을 사용 하도록 구성 되지 됩니다. (Web.config 파일은 SharePoint 서버를 설치할 때 생성 됩니다. 자세한 내용은 참조 [Web.config 파일을 작업할](http://go.microsoft.com/fwlink/?LinkID=149266).) 대화 상자는 디버깅을 사용 하려면 web.config 파일을 수정 하거나 디버깅 하지 않고 프로젝트를 실행 하는의 옵션을 제공 합니다. 첫 번째 옵션을 선택하면 프로젝트가 정상적으로 실행됩니다. 두 번째 옵션을 선택하면 web.config 파일이 다음과 같이 구성됩니다.  
  
-   호출 스택에 설정 (`CallStack="true"`)  
  
-   사용자 지정 오류가 비활성화 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] (`<customErrors mode="Off" />`)  
  
-   컴파일 디버깅 사용 (`<compilation debug="true">`)  
  
 결과 web.config 파일이 다음과 같습니다.  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <configuration>  
        ...  
        <SharePoint>  
            <SafeMode MaxControls="200"  
                CallStack="true"  
                DirectFileDependencies="10"  
                TotalFileDependencies="50"  
                AllowPageLevelTrace="false">  
                ...  
            </SafeMode>  
        ...  
        </SharePoint>  
        <system.web>  
            ...  
            <customErrors mode="Off" />  
            ...  
            <compilation debug="true">  
            ...  
            </compilation>  
            ...  
        </system.web>  
        ...  
    </configuration>  
```  
  
 다음을 변경 하는 변경 내용이 되돌릴 하 고 디버깅 사용 안 함, [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] web.config 파일에:  
  
-   호출 스택 해제 (`CallStack="false"`)  
  
-   사용자 지정 오류 사용 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] (`<customErrors mode="On" />`)  
  
-   컴파일 디버깅 사용 안 함 (`<compilation debug="false">`)  
  
##  <a name="Deployment"></a>F5 디버깅 및 배포 프로세스  
 디버그 모드에서 SharePoint 프로젝트를 실행 하는 경우 SharePoint 배포 프로세스는 다음과 같은 작업을 수행 합니다.  
  
1.  사용자 지정 가능한 배포 전 명령이 실행 됩니다.  
  
2.  사용 하 여 웹 솔루션 패키지 (.wsp) 파일을 만듭니다 [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 명령입니다. .Wsp 파일에 필요한 파일 및 기능이 모두 포함 됩니다. 자세한 내용은 참조 [솔루션 개요](http://go.microsoft.com/fwlink/?LinkID=128154)합니다.  
  
3.  SharePoint 솔루션은 팜 솔루션을 하는 경우 재생 되는 [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] 지정된 된 사이트에 대 한 응용 프로그램 풀 [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)]합니다. 이 단계에서 잠긴 파일을 해제는 [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] 작업자 프로세스입니다.  
  
4.  이전 버전의 패키지에 이미 있으면 기능과.wsp 파일에서 파일의 이전 버전을 제거 합니다. 이 단계에서는 기능을 비활성화 하 고 솔루션 패키지를 제거 후 SharePoint 서버에 솔루션 패키지를 삭제 합니다.  
  
5.  .Wsp 파일에서 기능 및 파일의 현재 버전을 설치합니다. 이 단계는 추가 하 고 SharePoint 서버에 솔루션을 설치 합니다.  
  
6.  워크플로의 워크플로 어셈블리를 설치합니다. 사용 하 여 해당 위치를 변경할 수는 *어셈블리 위치* 속성입니다.  
  
7.  사이트 또는 웹 범위인 경우 SharePoint에서 프로젝트의 기능을 활성화 합니다. 팜 및 웹 응용 프로그램 범위에서 기능이 활성화 되지 않았습니다.  
  
8.  워크플로의 워크플로가 연결 SharePoint 라이브러리, 목록 또는에서 선택한 사이트는 **SharePoint 사용자 지정 마법사**합니다.  
  
    > [!NOTE]  
    >  이 연결은 선택한 경우에 발생 **자동으로 연결 된 워크플로** 마법사에서.  
  
9. 사용자 지정 가능한 배포 후 명령을 실행합니다.  
  
10. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디버거를 [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] 프로세스(w3wp.exe)에 연결합니다. 해당 프로젝트 형식을 변경할 수 있도록 하는 경우는 *샌드박스 솔루션* 속성 및 해당 값은로 설정 되어 **true**, 디버거는 다른 프로세스 (SPUCWorkerProcess.exe)에 연결 합니다. 자세한 내용은 참조 [샌드박스 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)합니다.  
  
11. SharePoint 솔루션은 팜 솔루션은 JavaScript 디버거를 시작 합니다.  
  
12. 웹 브라우저에서 적절 한 라이브러리, 목록 또는 사이트 페이지를 표시합니다.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]각 작업이 완료 된 후 출력 창에 상태 메시지를 표시 합니다. 작업을 완료할 수 없는 경우 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 오류 목록 창에 오류 메시지를 표시 합니다.  
  
##  <a name="Features"></a>SharePoint 프로젝트 기능  
 기능은 기능 사이트 정의 사용 하 여 사이트 수정을 간소화 하는 이식 가능한 모듈식 단위입니다. 패키지 이기도 [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] (WSS) 요소의 특정 범위에 활성화 될 수 있고 사용자가 특정 목표 또는 작업을 수행 합니다. 서식 파일은 기능으로 배포 됩니다.  
  
 디버그 모드에서 프로젝트를 실행 하는 경우 배포 프로세스에 폴더를 만듭니다는 *기능* %COMMONPROGRAMFILES%\Microsoft Shared\web server extensions\14\TEMPLATE\FEATURES에 디렉터리입니다. 기능 이름 않은 형식이 *프로젝트 이름*_Feature*x*, TestProject_Feature1 등입니다.  
  
 기능 디렉터리에 솔루션 폴더를 포함 한 *기능 정의* 파일 및 *워크플로 정의* 파일입니다. 파일을 설명 하는 기능 정의 파일 (Feature.xml) 프로젝트의 기능의 프로젝트 정의 파일 (Elements.xml) 프로젝트 템플릿을 설명 합니다. Elements.xml을 확인할 수 있습니다 **솔루션 탐색기**, 되지만 Feature.xml는 솔루션 패키지를 만들 때 생성 됩니다. 이러한 파일에 대 한 자세한 내용은 참조 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)합니다.  
  
##  <a name="Workflow"></a>워크플로 디버깅  
 워크플로 프로젝트를 디버깅할 때 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] (해당 유형에 따라)에서 워크플로 템플릿으로 라이브러리에 목록을 추가 합니다. 그런 다음 수동으로 또는 추가 하거나 업데이트 하 여 항목에서 워크플로 템플릿으로 시작할 수 있습니다. 사용할 수 있습니다 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 워크플로 디버깅할 수 있습니다.  
  
> [!NOTE]  
>  다른 어셈블리에 대 한 참조를 추가 하는 경우 해당 어셈블리가 전역 어셈블리 캐시에 설치 되어 있는 ([!INCLUDE[TLA2#tla_gac](../sharepoint/includes/tla2sharptla-gac-md.md)]). 그렇지 않으면 워크플로 솔루션은 실패 합니다. 어셈블리를 설치 하는 방법에 대 한 정보를 참조 하십시오. [문서 또는 항목에서 워크플로 수동으로 시작](http://go.microsoft.com/fwlink/?LinkID=79938)합니다.  
  
 그러나 배포 프로세스는 워크플로 시작 하지 않습니다. SharePoint 웹 사이트에서 워크플로 시작 해야 합니다. 또한 Microsoft Office Word 2010와 같은 클라이언트 응용 프로그램을 사용 하 여 또는 별도 서버 쪽 코드를 사용 하 여 워크플로 시작할 수 있습니다. 에 지정 된 방법 중 하나를 사용 하 여는 **SharePoint 사용자 지정 마법사**합니다.  
  
 예를 들어 워크플로 수동으로 시작할 수 있음을 지정 하는 경우 라이브러리 또는 목록에 있는 항목에서 직접 워크플로 시작 합니다. 워크플로 수동으로 시작 하는 방법에 대 한 자세한 내용은 참조 하십시오. [문서 항목에는 워크플로 수동으로 시작할](http://go.microsoft.com/fwlink/?LinkID=79938)합니다.  
  
##  <a name="FeatureEvents"></a>디버깅 기능 이벤트 수신자  
 실행 하면 기본적으로는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 응용 프로그램을 SharePoint 서버에서 사용자에 대 한 해당 기능이 자동으로 활성화 합니다. 그러나 되므로 문제가 발생 기능 이벤트 수신자를 디버깅할 때에서 기능을 활성화 하는 경우 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 디버거에서 다른 프로세스에서 실행 합니다. 즉, 중단점, 등의 몇 가지 디버깅 기능을 제대로 작동 하지 않습니다.  
  
 자동으로 SharePoint에서 기능 활성화를 사용 하지 않도록 설정 하 고 기능 이벤트 수신자의 디버깅이 올바르게 작동 하도록 하려면 프로젝트의 값 설정 **활성 배포 구성** 속성을 **활성화없음** 디버깅 하기 전에. 그런 다음 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 응용 프로그램의 디버깅을 시작한 후 SharePoint에서 수동으로 기능을 활성화합니다. 기능을 활성화 하려면 엽니다는 **사이트 작업** sharepoint에서 메뉴 선택 **사이트 설정**, 선택는 **사이트 기능 관리** 링크를 선택한 후는 **Activate** 정상적으로 디버깅을 계속 하려면 기능 옆에 있는 단추입니다.  
  
##  <a name="EnhancedDebug"></a>향상 된 디버깅 정보를 사용 하도록 설정  
 간의 복잡 한 상호 작용으로 인해는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] (devenv.exe) 프로세스는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 호스트 프로세스 (vssphost4.exe), SharePoint 및 WCF 계층 빌드, 배포 및 기타 하는 동안 발생 하는 오류를 진단 수 있습니다는 해야 합니다. 이러한 오류를 해결 하기 위해 향상 된 디버깅 정보를 사용할 수 있습니다. 이렇게 하려면 Windows 레지스트리에서 다음 레지스트리 키로 이동:  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\11.0\SharePointTools]  
  
 경우 "EnableDiagnostics" **REG_DWORD** 값 않습니다 하지이 값을 직접 만들어야 합니다. "EnableDiagnostics" 값을 "1"로 설정  
  
 1 원인 스택에이 키 값을 설정 합니다. 추적 정보에는 **출력** 창에서 실행 하는 동안 프로젝트 시스템 오류가 발생할 때마다 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 고급 디버깅 정보를 사용하지 않도록 설정하려면 EnableDiagnostics를 다시 0으로 설정하거나 이 값을 삭제합니다.  
  
 다른 SharePoint 레지스트리 키에 대 한 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장 디버깅](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md)  
  
  