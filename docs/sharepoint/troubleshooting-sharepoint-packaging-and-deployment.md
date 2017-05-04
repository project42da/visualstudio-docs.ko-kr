---
caps.handback.revision: 24
---
# SharePoint 패키징 및 배포 문제 해결
  이 항목에서는 SharePoint 솔루션을 패키지하고 배포할 때 발생할 수 있는 다양한 문제에 대해 설명합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
## 고급 디버깅 사용  
 Visual Studio, SharePoint 및 기타 계층 간에서 진단하려면 EnableDiagnostics 레지스트리 키를 사용하여 스택 추적을 확인할 수 있습니다.  자세한 내용은 [SharePoint 솔루션 디버깅](../sharepoint/debugging-sharepoint-solutions.md)을 참조하십시오.  
  
## 솔루션 패키지에 프로젝트 출력 추가  
 패키지 디자이너를 통해 패키지에 프로젝트 출력을 추가할 수 있습니다.  그러나 프로젝트 출력을 추가할 때 프로젝트의 플랫폼이 SharePoint 솔루션의 플랫폼과 일치하는지 확인해야 합니다.  SharePoint 서버에 배포할 어셈블리에 대해 **Any CPU** 플랫폼 대상을 사용하는 것이 좋습니다.  자세한 내용은 [프로젝트 디자이너, 컴파일 페이지&#40;Visual Basic&#41;](../ide/reference/compile-page-project-designer-visual-basic.md) 및 [고급 컴파일러 설정 대화 상자&#40;Visual Basic&#41;](../ide/reference/advanced-compiler-settings-dialog-box-visual-basic.md)를 참조하십시오.  
  
## 유효성 검사 경고 및 오류  
 Visual Studio의 SharePoint 개발 도구는 유효성 검사 단계를 수행하여 솔루션 패키지가 올바르게 생성되었는지 확인합니다.  기능과 패키지에 대한 사용자 지정 유효성 검사 단계를 만들 수도 있습니다.  자세한 내용은 [How to: Create Custom Feature and Package Validation Rules for SharePoint Solutions](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md)을 참조하십시오.  
  
## 배포 충돌 해결  
 SharePoint 솔루션을 배포할 때 서버의 항목이 솔루션 패키지에 있는 항목과 같은 이름, URL 또는 ID를 갖고 있는 경우 충돌이 발생할 수 있습니다.  **배포 충돌 해결** 속성을 변경하여 모듈, 웹 파트, 목록 인스턴스 및 콘텐츠 형식에 대한 충돌을 해결하거나, 보고하거나, 무시할 수 있습니다.  
  
 다음 표에는 **배포 충돌 해결** 속성의 설정이 나와 있습니다.  
  
|값|설명|  
|-------|--------|  
|자동|충돌을 검색하고 자동으로 해결합니다.|  
|프롬프트|충돌을 검색하고 충돌을 해결하기 전에 개발자에게 보고합니다.|  
|없음|충돌을 검색하지 않습니다.|  
  
## F5 배포와의 차이점  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 사용하여 테스트 및 디버깅을 위해 SharePoint 프로젝트를 로컬 SharePoint 서버에 배포하는 경우 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 몇 가지 추가 단계가 수행됩니다.  
  
1.  배포 단계 중에 IIS\(인터넷 정보 서비스\)를 다시 설정합니다.  
  
2.  워크플로를 자동으로 연결합니다.  
  
3.  패키지 디자이너의 계층 구조에 따라 기능 활성화 순서를 설정합니다.  
  
 사용자 지정 배포 단계를 추가하여 F5 동작을 더 변경할 수 있습니다.  자세한 내용은 [Walkthrough: Creating a Custom Deployment Step for SharePoint Projects](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)을 참조하십시오.  
  
## 비주얼 웹 파트를 배포할 때 SharePoint 페이지 표시 지연  
 비주얼 웹 파트를 [!INCLUDE[wiprlhext](../sharepoint/includes/wiprlhext-md.md)], [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 또는 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)]의 Bin 폴더에 배포할 경우 SharePoint 페이지가 나타나는 데 오래 소요됩니다.  Bin 디렉터리와 같은 최상위 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 디렉터리에서 파일을 변경하는 경우 전체 웹 응용 프로그램이 다시 컴파일됩니다.  이로 인해 SharePoint 페이지가 렌더링되는 데 최대 25초가 지연될 수 있습니다.  
  
### 오류 메시지  
 없음  
  
### 해결  
 이 문제를 해결하려면 다음 단계를 수행합니다.  
  
1.  Microsoft 지원 문서 [FIX: A hotfix is available to fix two problems in ASP.NET on IIS 7.0 for Windows Vista and Windows Server 2008](http://go.microsoft.com/fwlink/?LinkId=179055)에 설명된 대로 업데이트 KB967535를 설치합니다.  
  
2.  Web.config 파일에 다음 코드를 추가합니다.  
  
    ```  
    <compilation batch="false" optimizeCompilations="true">  
    ```  
  
## "솔루션에서 cab 파일의 압축을 풀지 못했습니다."라는 오류를 표시하며 SharePoint 프로젝트 배포가 실패함  
 SharePoint 프로젝트 항목의 이름에 괄호가 포함되어 있으면 오류가 표시되면서 솔루션 배포에 실패하게 됩니다.  
  
### 오류 메시지  
 배포 단계 '솔루션 추가'에서 오류가 발생했습니다. 솔루션에서 cab 파일의 압축을 풀지 못했습니다.  
  
### 해결  
 이 문제를 해결하려면 SharePoint 프로젝트 항목의 이름에서 모든 괄호를 제거합니다.  
  
## 비주얼 웹 파트를 다른 웹 응용 프로그램의 사이트에 배포하면 오류가 나타남  
 현재 배포되어 있는 웹 응용 프로그램이 아닌 다른 웹 응용 프로그램의 사이트에 비주얼 웹 파트를 처음으로 배포\(비주얼 웹 파트의 SiteUrl 속성을 변경하여 배포함\)하면 오류가 발생합니다.  
  
### 오류 메시지  
 배포 단계 '솔루션 추가'에서 오류가 발생했습니다. 이 팜에 ID \[\#\]인 기능이 이미 설치되었습니다.  강제 특성을 사용하여 기능을 명시적으로 다시 설치합니다.  
  
### 해결  
 이 오류는 비주얼 웹 파트 기능이 SharePoint에서 제거되는 방식으로 인해 발생합니다.  비주얼 웹 파트를 성공적으로 배포하려면 F5 키를 선택하여 솔루션을 다시 배포합니다.  
  
## 중첩된 사용자 정의 컨트롤을 배포하면 경고가 나타남  
 이 경고는 사용자 정의 컨트롤이 포함된 비주얼 웹 파트나 비주얼 웹 파트 또는 다른 사용자 정의 컨트롤이 포함된 사용자 정의 컨트롤과 같은 중첩된 사용자 정의 컨트롤이 있는 SharePoint 솔루션을 배포하면 발생합니다.  이 경고는 도구 상자에서 컨트롤을 끌어 오거나 소스 뷰에서 @Register 지시문을 사용하여 디자이너에 컨트롤을 추가할 때 발생합니다.  
  
### 오류 메시지  
 경고 1 '\[*Control Name*\]' 요소는 알 수 없는 요소입니다.  이 경고는 웹 사이트에 컴파일 오류가 있거나 web.config 파일이 없는 경우 발생할 수 있습니다.  
  
### 해결  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 프로젝트 시스템에서 중첩된 사용자 정의 컨트롤을 인식하지 못하는 경우 Intellisense를 제공할 수 없으며 경고를 표시합니다.  프로젝트가 빌드되지 않고 디자이너가 닫히고 다시 열리지 않은 경우나 자동 취소 옵션을 사용하도록 설정하여 디버깅 후 사용자 정의 컨트롤이 SharePoint 하이브에서 제거되는 경우에 프로젝트 시스템에서 중첩된 사용자 정의 컨트롤을 인식하지 못합니다.  
  
 이 경고를 제거하려면 프로젝트를 빌드한 다음 디자이너를 닫았다가 다시 열거나 프로젝트에 대해 자동 취소 옵션을 사용하지 않도록 설정합니다.  이렇게 하려면 프로젝트 속성 대화 상자의 **SharePoint** 탭에서 **디버깅 후 자동 취소** 확인란의 선택을 취소합니다.  
  
## 참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  