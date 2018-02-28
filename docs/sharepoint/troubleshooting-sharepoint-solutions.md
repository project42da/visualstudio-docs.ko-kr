---
title: "SharePoint 솔루션 문제 해결 | Microsoft Docs"
ms.custom: 
ms.date: 02/22/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Microsoft.VisualStudio.Tools.SharePoint.Errors.Debugging
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, troubleshooting
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 6f03f8fd1fd5609f93d4fae22a7a694e61b1c80c
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="troubleshooting-sharepoint-solutions"></a>SharePoint 솔루션 문제 해결
  다음과 같은 문제 또는 경고를 사용 하 여 SharePoint 솔루션을 디버깅할 때 발생할 수 있습니다는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디버거 합니다. 자세한 내용은 참조 [SharePoint 2007 워크플로 솔루션 디버깅](http://msdn.microsoft.com/en-us/3a5392f3-66f3-48be-956e-02de23fa6247)합니다.
  
## <a name="token-restrictions-in-sandboxed-visual-web-parts"></a>샌드박스 비주얼 웹 파트의 토큰 제한 사항  
 샌드박스 솔루션의 비주얼 웹 파트는 SharePoint 런타임이 지원하는 $SPUrl과 같은 표준 토큰을 처리할 수 없습니다. 이에 따라 URL은 확인되지 않으며, 다음 예제와 같이 스크립트 요소에서 URL을 직접 참조하는 경우 비주얼 웹 파트 디자이너의 디자인 뷰에서 내용을 미리 볼 수 없습니다.  
  
```xml  
<script src="<% $SPUrl:~site/SiteAssets/ListOperations.js %>"></script>  
```  
  
 이 제한 사항을 해결하고 토큰을 확인하려면 리터럴을 사용하여 URL을 참조하십시오.  
  
```xml  
<asp:literal ID="Literal1" runat="server" Text="<script src='" />  
<asp:literal ID="Literal2" runat="server" Text="<% $SPUrl:~site/SiteAssets/ListOperations.js %>" />  
<asp:literal ID="Literal3" runat="server" Text="' type='text/javascript' ></script>" />  
```  
  
## <a name="character-restrictions-in-names-of-projects-and-project-items"></a>프로젝트 및 프로젝트 항목 이름의 문자 제한  
 프로젝트와 프로젝트 항목의 이름에는 SharePoint 2010의 배포 경로에서 유효한 문자만 포함될 수 있습니다. 다른 문자가 허용 됩니다.  
  
### <a name="error-message"></a>오류 메시지  
 "잘못 된 문자" 오류 메시지입니다.  
  
### <a name="resolution"></a>해결  
 SharePoint 프로젝트 및 프로젝트 항목 이름의 경우 다음 문자만 사용합니다.  
  
-   영숫자 ASCII 문자  
  
-   공백  
  
-   마침표 (입니다.)  
  
-   쉼표 ()  
  
-   밑줄 (_)  
  
-   대시 (-)  
  
-   백슬래시(\\)  
  
 프로젝트가 패키지될 때 유효성 검사 규칙은 배포 중인 각 파일의 배포 경로 속성에 이러한 유효한 문자만 포함되어 있는지 확인합니다.  
  
## <a name="errors-when-creating-custom-fields"></a>사용자 지정 필드를 만들 때 오류  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 사용자 지정 필드는 XML로 정의됩니다. 필드가 정의되어 있지 않거나 특정 형식을 사용하여 참조되는 경우 오류가 발생할 수 있습니다.  
  
### <a name="error-message"></a>오류 메시지  
 "잘못 된 문자" 패키징 시 오류 메시지입니다.  
  
### <a name="resolution"></a>해결  
 필드 정의의 ID는 다음 예제와 같이 중괄호로 묶은 GUID여야 합니다.  
  
```xml  
<Field ID="{5744d18c-305e-4632-8bd1-09d134f4830d}"   
    Type="Note"   
    Name="PatientName"   
    DisplayName="Patient Name"   
    Group="A Custom Group">  
</Field>.  
```  
  
 다음 예제와 같이 콘텐츠 형식에서 필드 참조 빈 요소 형식을 사용 하 여 정의 되어야 합니다 (\<FieldRef / >)를 시작/끝 요소를 사용 하 여 (\<FieldRef >\</FieldRef >):  
  
```xml  
<FieldRef ID="{5744d18c-305e-4632-8bd1-09d134f4830d}"   
    Name="PatientName"   
    DisplayName="Patient Name"   
    Required="TRUE"/>  
```  
  
 필드의 소스 XML에 잘못된 형식이나 유효하지 않은 XML 파일과 같은 문제가 있는 경우 "파일을 구문 분석할 수 없음" 오류가 발생합니다.  
  
## <a name="new-non-english-site-definitions-do-not-appear-in-site-creation-page-after-deployment"></a>배포 후 영어가 아닌 사이트 정의 새 사이트 만들기 페이지에 표시 되지 않습니다.  
 만들고의 영어 이외의 버전을 사용 하 여 사이트 정의 배포 후 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] (로캘로 버전 즉, [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)] 1033 이외의), **SharePoint 사용자 지정** 는 탭이나타나지않습니다**서식 파일 선택** 에 상자와 새 사이트 템플릿이 표시 되지 않으면는 **새 SharePoint 사이트** 페이지.  
  
### <a name="error-message"></a>오류 메시지  
 없음  
  
### <a name="resolution"></a>해결  
 에 잘못 된 값으로 인해이 문제가 발생 된 **경로** webtemp 사이트 정의 구성 파일 예 webtemp_SiteDefinitionProject1.xml:에 대 한 속성. 에 **경로** 아래에 있는 webtemp 파일에 대 한 속성의 **배포 위치**, 적절 한 로캘로 1033 변경 [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]합니다. 예를 들어 사용 하려면 일본어 로캘을 변경 값 1041을 합니다. 자세한 내용은 참조 [Microsoft에서 할당 한 로캘 Id](http://go.microsoft.com/fwlink/?LinkID=165561) MSDN 웹 사이트에 있습니다.  
  
## <a name="error-appears-when-a-workflow-project-is-deployed-on-a-clean-system"></a>워크플로 프로젝트가 클린 시스템에 배포 될 때 오류가 나타남  
 이 문제는 클린 시스템의 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 워크플로 프로젝트를 배포하는 경우 발생합니다. 클린 시스템은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 및 SharePoint를 새로 설치했지만 워크플로 프로젝트를 배포하지 않은 컴퓨터입니다.  
  
### <a name="error-message"></a>오류 메시지  
 SharePoint 목록을 찾을 수 없습니다: 워크플로 기록 합니다.  
  
### <a name="resolution"></a>해결  
 누락 된 워크플로 기록 목록 인해이 오류가 발생 합니다. 개발 환경에는 클린 시스템 이므로 워크플로가 배포 되지 및 워크플로 기록 목록 아직 존재 하지 않습니다. 이 문제를 해결 하려면 워크플로 마법사를 사용 하면 만들 워크플로 기록 목록을 다시 엽니다.  
  
##### <a name="to-reenter-the-workflow-wizard"></a>워크플로 마법사를 다시 입력 하려면  
  
1.  **솔루션 탐색기**, 워크플로 노드를 선택 합니다.  
  
2.  에 **속성** 창에서 줄임표 단추가 있는 임의의 속성에서 줄임표 (...) 단추를 선택 합니다.  
  
## <a name="user-must-refresh-application-page-in-browser-while-debugging-to-view-updated-image"></a>업데이트 된 이미지 보기를 디버깅 하는 동안 사용자 브라우저에서 응용 프로그램 페이지를 새로 고쳐야  
 와 같은 이미지를 표시 하는 컨트롤과 함께 응용 프로그램 페이지를 포함 하는 SharePoint 솔루션 디버깅 하는 경우는 [!INCLUDE[TLA2#tla_html](../sharepoint/includes/tla2sharptla-html-md.md)] 이미지 컨트롤은 이미지에 대 한 모든 변경 사항을 표시 하려면 브라우저에서 페이지를 새로 고쳐야 합니다.  
  
## <a name="error-the-site-location-is-not-valid"></a>오류: 사이트 위치가 잘못 되었습니다.  
 이 문제가 발생할 수 있습니다 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] 설치 되어 있지 않습니다. 에 지정 된 SharePoint 웹 사이트에 대 한 관리자 권한이 없는 경우 발생할 수 있습니다는 **SharePoint 사용자 지정 마법사**합니다.  
  
### <a name="error-message"></a>오류 메시지  
  
-   SharePoint 사이트 위치가 올바르지 않습니다.  
  
### <a name="resolution"></a>해결  
  
-   [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)]을 설치합니다.  
  
-   SharePoint 웹 사이트에 대 한 관리자 권한이 있는지 확인 하십시오. 자세한 내용은 참조는 [!INCLUDE[TLA2#tla_office](../sharepoint/includes/tla2sharptla-office-md.md)] 온라인 문서 [포털 사이트에 대 한 액세스 권한을 부여](http://go.microsoft.com/fwlink/?LinkId=98310)합니다.  
  
## <a name="site-deletion-web-event-does-not-occur-in-event-receiver-project"></a>이벤트 수신기 프로젝트의 사이트 삭제 웹 이벤트가 발생 하지 않습니다.  
 이벤트 수신기 프로젝트를 만들 때 "사이트를 삭제 하는 중"와 같은 특정 웹 이벤트를 선택 하면 이벤트가 발생 하지 않습니다.  
  
### <a name="error-message"></a>오류 메시지  
 없음  
  
### <a name="resolution"></a>해결  
 이 문제는 기능 범위 "Site" 사이트 수준 이벤트를 처리 해야 합니다. 하지만 이벤트 수신기 프로젝트에 대 한 기본 기능 범위는 "웹" 때문에 발생 합니다. 영향을 받는 웹 이벤트는 같습니다.  
  
-   사이트 되 고 (WebDeleting)를 삭제 합니다.  
  
-   사이트 삭제 됨 (WebDeleted)  
  
-   사이트 되 고 (WebMoving)를 이동 합니다.  
  
-   사이트 이동 됨 (WebMoved)  
  
 이 문제를 해결 하려면 이벤트 수신기의 기능 범위를 다음과 같이 변경 합니다.  
  
##### <a name="to-change-the-feature-scope-of-the-event-receiver"></a>이벤트 수신기의 기능 범위를 변경 하려면  
  
1.  **솔루션 탐색기**, 이벤트 수신기의.feature 파일을 열고는 **기능 디자이너** 파일을 두 번 클릭 하거나 메뉴를 연 바로 가기 차례로 선택 하 여 **열**.  
  
2.  옆에 있는 화살표를 선택 **범위**를 선택한 후 **사이트** 표시 되는 목록에 있습니다.  
  
## <a name="deployment-error-appears-after-the-name-of-an-identifier-in-a-business-data-connectivity-model-project-is-changed"></a>비즈니스 데이터 연결 모델 프로젝트에 있는 식별자의 이름이 변경 된 후 배포 오류가 나타남  
 이 문제는 비즈니스 데이터 BDC (연결) 모델의 엔터티 식별자 이름을 변경 하 고 솔루션을 배포 하려고 하는 경우에 발생 합니다.  
  
### <a name="error-messages"></a>오류 메시지  
  
-   \<*모델 이름*> 다음 외부 콘텐츠 형식 활성화 오류가 있습니다...  
  
-   이름의 IMetadataObject '\<*모델 이름*>'에 'name' 필드가 중복 된 값 중...  
  
### <a name="resolution"></a>해결  
 이 문제를 해결 하려면 모델을 수동으로 삭제 한 다음 솔루션을 다시 배포 합니다.  다음 도구 중 하나를 사용 하 여 모델을 삭제할 수 있습니다.  
  
-   SharePoint 2010 중앙 관리 합니다. 자세한 내용은 참조 [BDC 모델 관리](http://go.microsoft.com/fwlink/?LinkID=181472) Microsoft TechNet 웹 사이트에 있습니다.  
  
-   Windows PowerShell. 명령 프롬프트에서 다음이 명령을 입력 하 여 모델을 삭제할 수 있습니다: **제거 SPBusinessDataCatalogModel**합니다. 자세한 내용은 참조 [일반 cmdlet (SharePoint Server 2010)](http://go.microsoft.com/fwlink/?LinkID=182375) Microsoft TechNet 웹 사이트에 있습니다.  
  
## <a name="an-error-appears-when-you-try-to-view-a-visual-web-part-in-sharepoint"></a>Sharepoint에서 비주얼 웹 파트를 보려고 하면 오류가 발생  
 이 문제는 발생 때는 **경로** 사용자 정의 컨트롤의 속성 문자열으로 시작 하지 않으면 "보려면\\"입니다.  
  
### <a name="error-messages"></a>오류 메시지  
  
-   파일 ' /_CONTROLTEMPLATES/*\<프로젝트 이름 >*/*\<웹 파트 이름 >*/*\<사용자 정의 컨트롤 이름 >*.ascx'가 없습니다.  
  
-   '/' 응용 프로그램에서 서버 오류입니다.  
  
### <a name="resolution"></a>해결  
  
##### <a name="to-resolve-this-issue"></a>이 문제를 해결 하려면  
  
1.  **솔루션 탐색기**, 파일 이름 확장명이.ascx가 사용자 정의 컨트롤 파일을 선택 합니다.  
  
2.  메뉴 모음에서 **보기**, **속성 창**합니다.  
  
3.  에 **속성** 창을 확장 하 고는 **배포 위치** 노드.  
  
4.  값을 확인 하는 **경로** 속성 문자열로 시작 "보려면\\"입니다.  
  
## <a name="error-appears-when-an-imported-reusable-workflow-that-contains-a-task-form-field-is-run"></a>작업 양식 필드를 포함 하는 가져온된 다시 사용할 수 있는 워크플로 실행 하면 오류가 나타남  
 이 문제는 필드가 태스크 폼을 포함 하는 워크플로 가져온 후 가져온 원본 동일한 시스템에서 새 워크플로 실행 하는 경우에 발생 합니다.  
  
### <a name="error-message"></a>오류 메시지  
 배포 단계 ' 기능 활성화에서 오류가 발생 했습니다: 필드 Id [*Guid*] 기능에 정의 된 [*Guid*] 또는 하위 사이트에 현재 사이트 모음의에서 발견 되었습니다.  
  
### <a name="resolution"></a>해결  
 이 오류는 프로젝트에서 다시 사용할 수 있는 워크플로 가져오기 때문에 발생 하는 필드 ID 충돌의 결과 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 작업 폼 필드 Id를 변경 하지 않습니다. 원래 워크플로 포함 하는 동일한 서버에서 가져온된 워크플로 배포 하는 경우 필드 ID 충돌이 발생 합니다.  
  
 이 문제를 해결 하려면 모든 가져온된 워크플로 파일에서 필드 ID 특성의 값을 변경 하려면 찾기 및 바꾸기 기능을 사용 합니다.  
  
## <a name="error-appears-when-a-renamed-imported-list-instance-is-run"></a>오류 경우 표시 이름을 바꾼 가져온 목록 인스턴스가 실행 될  
 가져온된 목록 인스턴스에 이름을 바꾼 후 실행 하는 경우이 문제가 발생 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
### <a name="error-message"></a>오류 메시지  
 빌드 오류: 배포 단계 ' 기능 활성화에서 오류가 발생 했습니다: 파일 Template\Features\\[*프로젝트 가져오기**기능**이름*] \Files\Lists \\[*이전**목록 이름*] \Schema.xml 존재 하지 않습니다.  
  
### <a name="resolution"></a>해결  
 목록 인스턴스를 가져올 때 CustomSchema 특성 목록 인스턴스의 Elements.xml 파일에 추가 됩니다. Elements.xml 목록 인스턴스에 대 한 사용자 지정 schema.xml의 경로 포함 합니다. 에 목록 인스턴스의 이름을 바꾸면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 사용자 지정 schema.xml에 대 한 배포 경로 변경 되지만 CustomSchema 특성의 경로 값 업데이트 되지 않습니다. 결과적으로, 목록 인스턴스는이 기능을 활성화 하는 경우 CustomSchema 특성에 지정 된 이전 경로에 schema.xml 파일을 찾을 수 없습니다.  
  
 이 문제를 해결 하려면 CustomSchema 특성에 schema.xml 파일의 배포 위치 경로 업데이트 합니다.  
  
## <a name="sharepoint-debugging-session-terminated-by-iis"></a>SharePoint 디버깅 세션이 IIS에 의해 종료 됨  
 에 중단점을 설정 하는 경우이 문제가 발생 한 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 솔루션을 실행 한 다음 90 초 넘게 중단점에 머무르는 F5 키를 선택 합니다.  
  
### <a name="error-message"></a>오류 메시지  
 인터넷 정보 서비스 (IIS)에서 디버깅 중이 던 웹 서버 프로세스가 종료 되었습니다. IIS에서 응용 프로그램 풀 ping 설정을 구성하여 이 문제를 방지할 수 있습니다. 참조에 대 한 자세한 내용은 도움말입니다.  
  
### <a name="resolution"></a>해결  
 기본적으로 IIS 응용 프로그램 풀에는 응용 프로그램이 닫히기 전에 응답 하도록 응용 프로그램에 대 한 90 초 동안 기다립니다. 이 프로세스는 응용 프로그램을 "ping" 라고 합니다. 이 문제를 해결 하려면 대기 시간을 늘리려면 또는 ping을 완전히 응용 프로그램을 사용 하지 않도록 설정 합니다.  
  
##### <a name="to-access-the-iis-app-pool-settings"></a>IIS 응용 프로그램 풀 설정에 액세스 하려면  
  
1.  IIS 관리자를 엽니다.  
  
2.  에 **연결** 창, SharePoint 서버 노드를 확장 한 다음 선택에서 **응용 프로그램 풀** 노드.  
  
3.  에 **응용 프로그램 풀** 페이지에서 SharePoint 응용 프로그램 풀 (대개 "SharePoint-80")를 선택를 선택한 후는 **동작** 창, 선택는 **고급 설정** 링크입니다.  
  
4.  IIS 시간 제한 전에 대기 시간을 늘리려면 값을 변경 **Ping 최대 응답 시간 (초)** 90 초 보다 큰 값으로.  
  
5.  Ping을 실행 하는 IIS를 사용 하지 않으려면 설정 **Ping 사용** 를 **False**합니다.  
  
## <a name="auto-retract-leaves-orphaned-list-instance-in-sharepoint"></a>SharePoint에서 분리 된 목록 인스턴스 Leaves 자동 취소  
 다음 단계를 수행 하는 경우이 문제가 발생 합니다.  
  
1.  목록 인스턴스에 있는 목록 정의 만듭니다 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
2.  F5 키를 선택하여 솔루션을 실행합니다.  
  
3.  디버깅을 중지 하거나 SharePoint 사이트를 닫습니다.  
  
4.  SharePoint 사이트를 다시 열고 하 고 목록 인스턴스를 엽니다.  
  
### <a name="error-message"></a>오류 메시지  
 '/' 응용 프로그램에서 서버 오류입니다.  
  
### <a name="resolution"></a>해결  
 SharePoint 솔루션의 디버그 세션을 닫은 후 때문에 이런는 자동 취소 기능 솔루션을 취소 합니다. 취소는 SharePoint에서 목록 정의 삭제 하지만 목록의 인스턴스를 삭제 하지 않습니다. 목록 인스턴스는 기본 목록 정의 필요 합니다.  
  
 이 문제를 해결 하려면 메뉴 모음에서 선택에 의해 솔루션을 배포할 **빌드**, **배포**합니다. F5 키를 선택하여 솔루션을 디버깅하지 마십시오. 그런 다음 SharePoint에서 목록 인스턴스를 삭제 합니다.  
  
## <a name="original-sharepoint-solution-is-replaced-by-an-exported-version"></a>원래 SharePoint 솔루션은 내보낸 버전으로 교체  
 SharePoint 솔루션을 내보내는 경우에 솔루션을 가져오기 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 다음 내보낸 된 동일한 사이트에 다시 솔루션을 배포 하 고, SharePoint 솔루션을 원래 대체 됩니다. 원래 솔루션에 활성화 되지 않은 서버에 솔루션을 배포 하는 경우에이 문제가 발생 하지 않습니다.  
  
### <a name="error-message"></a>오류 메시지  
 없음  
  
### <a name="resolution"></a>해결  
 을 내보낸 된 사이트에 솔루션을 덮어쓰지 않으려면 변경는 SolutionID의 guid와 가져온된의 모든 기능에 대 한 기능 Id는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 프로젝트.  
  
## <a name="error-appears-when-debugging-starts"></a>디버깅을 시작할 때 오류가 나타남  
 Visual Studio에서 SharePoint 솔루션의 디버깅을 시작할 때 지정한 키가 사전에 없기 때문에 Visual Studio에서 Web.config 파일을 로드할 수 없다는 오류가 발생합니다.  
  
### <a name="error-message"></a>오류 메시지  
 Web.config 구성 파일을 로드 하지 못했습니다. 잘못 된 형식의 모든 XML 요소에 대 한 파일을 확인 하 고 다시 시도 하십시오. 다음 오류가 발생 했습니다: 지정한 키가 사전에 없습니다.  
  
### <a name="resolution"></a>해결  
 이 문제를 해결하려면 Visual Studio에서 SharePoint 프로젝트의 사이트 URL 속성 값이 웹 응용 프로그램의 대체 액세스 매핑에 대한 기본 영역에 할당된 URL과 일치하는지 확인합니다. 인트라넷 등의 다른 영역을 URL에 사용하여 오류를 해결할 수 없습니다. 프로젝트의 사이트 URL과 기본 영역의 URL은 일치해야 합니다. 대체 액세스 매핑에 액세스 하려면 SharePoint 2010 중앙 관리 유틸리티를 열고, 선택는 **응용 프로그램 관리** 링크를 차례로 선택한 다음 **웹 응용 프로그램**, 선택는  **대체 액세스 매핑 구성** 링크 합니다. 자세한 내용은 참조 [웹 응용 프로그램에 대 한 영역을 만들](http://go.microsoft.com/fwlink/?LinkId=192274)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 패키징 및 배포 문제 해결](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md)   
 [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)   
 [Visual Studio의 디버깅](/visualstudio/debugger/debugging-in-visual-studio)  
  
  
