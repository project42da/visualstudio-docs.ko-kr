---
title: "SharePoint 솔루션 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.Project.WebConfigModificationDialog"
  - "VS.SharePointTools.Project.DebuggingNotEnabled"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 디버깅"
ms.assetid: 5120f21e-4c27-4906-b982-85e9cd5170e6
caps.latest.revision: 29
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 28
---
# SharePoint 솔루션 디버깅
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디버거를 사용하여 SharePoint 솔루션을 디버깅할 수 있습니다.  디버깅을 시작하면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 프로젝트 파일을 SharePoint 서버에 배포한 다음 웹 브라우저에서 SharePoint 사이트 인스턴스를 엽니다.  다음 단원에서는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 응용 프로그램을 디버깅하는 방법에 대해 설명합니다.  
  
-   [디버깅 사용](#EnableDebug)  
  
-   [F5 디버깅 및 배포 프로세스](#Deployment)  
  
-   [$SharePoint 프로젝트 기능](#Features)  
  
-   [워크플로 디버깅](#Workflow)  
  
-   [기능 이벤트 수신자 디버깅](#FeatureEvents)  
  
-   [고급 디버깅 정보 사용](#EnhancedDebug)  
  
##  <a name="EnableDebug"></a> 디버깅 사용  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 솔루션을 처음 디버깅하는 경우 web.config 파일이 디버깅을 사용하도록 구성되지 않았다는 알림 대화 상자가 나타납니다. web.config 파일은 SharePoint 서버를 설치할 때 만들어집니다.  자세한 내용은 [Web.config 파일 작업](http://go.microsoft.com/fwlink/?LinkID=149266)을 참조하십시오.\) 이 대화 상자에서는 디버깅을 설정하기 위해 web.config 파일을 디버깅하거나 수정하지 않고 프로젝트를 실행하는 옵션을 제공합니다.  첫 번째 옵션을 선택하면 프로젝트가 정상적으로 실행됩니다.  두 번째 옵션을 선택하면 web.config 파일이 다음과 같이 구성됩니다.  
  
-   호출 스택을 사용하도록 설정합니다\(`CallStack="true"`\).  
  
-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 사용자 지정 오류를 해제합니다\(`<customErrors mode="Off" />`\).  
  
-   컴파일 디버깅을 사용하도록 설정합니다\(`<compilation debug="true">`\).  
  
 결과로 생성된 web.config 파일은 다음과 같습니다.  
  
```  
  
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
  
 변경 내용을 취소하고 디버깅을 사용하지 않도록 설정하려면 web.config 파일의 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]을 다음과 같이 변경합니다.  
  
-   호출 스택을 해제합니다\(`CallStack="false"`\).  
  
-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 사용자 지정 오류를 사용하도록 설정합니다\(`<customErrors mode="On" />`\).  
  
-   컴파일 디버깅을 해제합니다\(`<compilation debug="false">`\).  
  
##  <a name="Deployment"></a> F5 디버깅 및 배포 프로세스  
 디버그 모드에서 SharePoint 프로젝트를 실행하면 SharePoint 배포 프로세스에서 다음 작업을 수행합니다.  
  
1.  사용자 지정 가능한 배포 전 명령을 실행합니다.  
  
2.  [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 명령을 사용하여 웹 솔루션 패키지 파일\(.wsp\)을 만듭니다.  .wsp 파일에는 필요한 파일과 기능이 모두 포함됩니다.  자세한 내용은 [솔루션 개요http:\/\/go.microsoft.com\/fwlink\/?LinkID\=128154](http://go.microsoft.com/fwlink/?LinkID=128154) 를 참조하십시오.  
  
3.  SharePoint 솔루션이 팜 솔루션인 경우 지정한 사이트 [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)]에 대해 [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] 응용 프로그램 풀을 재생합니다.  이 단계에서는 [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] 작업자 프로세스에서 잠긴 파일을 해제합니다.  
  
4.  이전 버전의 패키지가 이미 있는 경우 .wsp 파일에서 이전 버전의 기능과 파일을 제거합니다.  이 단계에서는 기능을 비활성화하고 솔루션 패키지를 제거한 다음 SharePoint 서버에서 솔루션 패키지를 삭제합니다.  
  
5.  .wsp 파일에 있는 최신 버전의 기능과 파일을 설치합니다.  이 단계에서는 SharePoint 서버에 솔루션을 추가하고 설치합니다.  
  
6.  워크플로의 경우 워크플로 어셈블리를 설치합니다.  *Assembly Location* 속성을 사용하여 해당 위치를 변경할 수 있습니다.  
  
7.  범위가 사이트 또는 웹인 경우 SharePoint에서 프로젝트의 기능을 활성화합니다.  팜 및 WebApplication 범위의 기능은 활성화되지 않습니다.  
  
8.  워크플로의 경우 **SharePoint 사용자 지정 마법사**에서 선택한 SharePoint 라이브러리, 목록 또는 사이트에 워크플로를 연결합니다.  
  
    > [!NOTE]  
    >  이 연결은 마법사에서 **자동으로 워크플로 연결**을 선택한 경우에만 발생합니다.  
  
9. 사용자 지정 가능한 배포 후 명령을 실행합니다.  
  
10. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디버거를 [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] 프로세스\(w3wp.exe\)에 연결합니다.  프로젝트 형식에서 *Sandboxed Solution* 속성의 변경을 허용하고 해당 값이 **true** 로 설정되어 있다면, 디버거가 다른 프로세스\(SPUCWorkerProcess.exe\)에 연결됩니다.  자세한 내용은 [샌드박스가 적용된 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)을 참조하십시오.  
  
11. SharePoint 솔루션이 팜 솔루션인 경우 JavaScript 디버거를 시작합니다.  
  
12. 웹 브라우저에서 적절한 라이브러리, 목록 또는 사이트 페이지를 표시합니다.  
  
 각 작업이 완료된 후 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 출력 창에 상태 메시지를 표시합니다.  작업을 완료할 수 없으면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 오류 목록 창에 오류 메시지를 표시합니다.  
  
##  <a name="Features"></a> $SharePoint 프로젝트 기능  
 기능이란 사이트 정의를 사용하여 사이트 수정을 단순화하는 이식 가능한 모듈식 기능 단위를 말합니다.  또한 특정 범위에 대해 활성화될 수 있고 사용자가 특정 목표 또는 작업을 수행할 수 있도록 돕는 [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)]\(WSS\) 요소의 패키지입니다.  템플릿은 기능으로 배포됩니다.  
  
 디버그 모드에서 프로젝트를 실행하면 배포 프로세스에서 %COMMONPROGRAMFILES%\\Microsoft Shared\\web server extensions\\14\\TEMPLATE\\FEATURES의 *기능* 디렉터리에 폴더를 만듭니다.  기능 이름은 *project name*\_Feature*x* 형식을 사용합니다. \(예: TestProject\_Feature1\)  
  
 기능 디렉터리의 솔루션 폴더에는 *기능 정의* 파일과 *워크플로 정의* 파일이 들어 있습니다.  기능 정의 파일\(Feature.xml\)은 프로젝트 기능의 파일을 설명하고프로젝트 정의 파일\(Elements.xml\)은 프로젝트 템플릿을 설명합니다.  Elements.xml은 **솔루션 탐색기**에서 찾을 수 있지만 Feature.xml은 솔루션 패키지를 만들 때 생성됩니다.  이러한 파일에 대한 자세한 내용은 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)을 참조하십시오.  
  
##  <a name="Workflow"></a> 워크플로 디버깅  
 워크플로 프로젝트를 디버깅하는 경우 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 형식에 따라 워크플로 템플릿을 라이브러리나 목록에 추가합니다.  수동으로 또는 항목을 추가하거나 업데이트하여 워크플로 템플릿을 시작할 수 있습니다.  그런 다음 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 사용하여 워크플로를 디버깅할 수 있습니다.  
  
> [!NOTE]  
>  다른 어셈블리에 대한 참조를 추가하는 경우 해당 어셈블리가 [!INCLUDE[TLA2#tla_gac](../sharepoint/includes/tla2sharptla-gac-md.md)]\(전역 어셈블리 캐시\)에 설치되어 있는지 확인하십시오.  그렇지 않으면 워크플로 솔루션이 실패합니다.  어셈블리를 설치하는 방법에 대한 자세한 내용은 [수동으로 문서 또는 항목에서 워크플로 시작](http://go.microsoft.com/fwlink/?LinkID=79938) 을 참조하십시오.  
  
 하지만 배포 프로세스에서는 워크플로를 시작하지 않습니다.  따라서 사용자가 SharePoint 웹 사이트에서 워크플로를 직접 시작해야 합니다.  Microsoft Office Word 2010 등의 클라이언트 응용 프로그램이나 별도의 서버 쪽 코드를 사용하여 워크플로를 시작할 수도 있습니다.  **SharePoint 사용자 지정 마법사**에서 지정한 방법 중 하나를 사용합니다.  
  
 예를 들어 워크플로를 수동으로 시작할 수 있도록 지정한 경우 라이브러리 또는 목록의 항목에서 직접 워크플로를 시작합니다.  워크플로를 수동으로 시작하는 방법에 대한 자세한 내용은 [수동으로 문서 항목에서 워크플로 시작](http://go.microsoft.com/fwlink/?LinkID=79938) 을 참조하십시오.  
  
##  <a name="FeatureEvents"></a> 기능 이벤트 수신자 디버깅  
 기본적으로 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 응용 프로그램을 실행하면 SharePoint 서버에서 해당 기능이 자동으로 활성화됩니다.  하지만 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 기능을 활성화할 때 기능이 디버거가 아닌 다른 프로세스에서 실행되므로 기능 이벤트 수신자를 디버깅하는 경우 문제가 발생합니다.  즉, 중단점과 같은 일부 디버깅 기능이 제대로 작동하지 않습니다.  
  
 SharePoint에서 기능이 자동으로 활성화되지 않도록 하고 기능 이벤트 수신자의 디버깅이 올바르게 작동하도록 하려면 디버깅하기 전에 프로젝트의 **활성 배포 구성** 속성을 **활성화 없음**으로 설정합니다.  그런 다음 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에서 해당 SharePoint 응용 프로그램이 디버그가 시작되고 난 후, 수동으로 SharePoint의 기능을 활성화합니다.  기능을 활성화 하려면 SharePoint의 **사이트 작업** 메뉴에서 **사이트 설정**을 선택하고 **사이트 기능 관리** 링크를 선택한 다음 기능 옆에 있는 **활성화** 단추를 클릭하고 디버깅을 정상적으로 다시 시작합니다.  
  
##  <a name="EnhancedDebug"></a> 고급 디버깅 정보 사용  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 프로세스\(devenv.exe\), [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 호스트 프로세스\(vssphost4.exe\), SharePoint 및 WCF 레이어 사이의 상호 작용이 때로는 복잡할 수 있습니다. 이 경우 빌드, 배포 등을 수행하는 동안 발생하는 오류를 진단하기가 어려울 수 있습니다.  이러한 오류 해결을 돕기 위해 고급 디버깅 정보를 사용하도록 설정할 수 있습니다.  이렇게 하려면 Windows 레지스트리에서 다음 레지스트리 키로 이동합니다.  
  
 \[HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\11.0\\SharePointTools\]  
  
 "EnableDiagnostics" **REG\_DWORD** 값이 이미 존재하지 않을 경우, 값을 수동으로 생성합니다.  "EnableDiagnostics" 값을 "1"로 설정합니다.  
  
 이 키 값을 1로 설정하면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 실행하는 동안 프로젝트 시스템 오류가 발생할 때마다 **출력** 창에 스택 추적 정보가 표시됩니다.  고급 디버깅 정보를 사용하지 않으려면 EnableDiagnostics를 다시 0으로 설정하거나 값을 지웁니다.  
  
 기타 SharePoint 레지스트리 키에 대한 자세한 내용은 [Debugging Extensions for the SharePoint Tools in Visual Studio](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
## 참고 항목  
 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md)  
  
  