---
caps.handback.revision: 41
---
# SharePoint 솔루션 문제 해결
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디버거를 사용하여 SharePoint 솔루션을 디버깅할 때는 다음 문제나 경고가 발생할 수 있습니다.  자세한 내용은 [NIB: Debugging SharePoint 2007 Workflow Solutions](http://msdn.microsoft.com/ko-kr/3a5392f3-66f3-48be-956e-02de23fa6247)을 참조하십시오.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
## Token Restrictions in Sandboxed Visual Web Parts  
 샌드박스 솔루션에서 비주얼 웹 파트는 SharePoint 런타임이 지원하는 $SPUrl와 같은 표준 토큰을 처리할 수 없습니다.  결과적으로 URL는 해결되지 않으며, 다음의 예제에서와 같이 스크립트 요소에서 직접 참조하는 경우 비주얼 웹 파트 디자이너의 디자인 보기에서 내용을 미리 볼 수 없습니다 :  
  
```  
<script src=”<% $SPUrl:~site/SiteAssets/ListOperations.js %>"></script>  
```  
  
 이 제한 사항을 피하고 토큰을 해결하기위해 literal을 사용하여 참조 하십시오.  
  
```  
<asp:literal ID="Literal1" runat="server" Text="<script src='" />  
<asp:literal ID="Literal2" runat="server" Text="<% $SPUrl:~site/SiteAssets/ListOperations.js %>" />  
<asp:literal ID="Literal3" runat="server" Text="' type='text/javascript' ></script>" />  
```  
  
## Character Restrictions in Names of Projects and Project Items  
 프로젝트와 프로젝트 항목 이름에는 SharePoint 2010의 배포 경로에서 유효한 문자만 포함될 수 있습니다.  다른 문자는 허용되지 않습니다.  
  
### 오류 메시지  
 "잘못된 문자" 오류 메시지  
  
### 해결  
 SharePoint 프로젝트 및 프로젝트 항목 이름의 경우 다음 문자만 사용합니다.  
  
-   영숫자 ASCII 문자  
  
-   공백  
  
-   마침표\(.\)  
  
-   쉼표\(,\)  
  
-   밑줄\(\_\)  
  
-   파선\(\-\)  
  
-   백슬래시\(\\\)  
  
 프로젝트가 패키지될 때 유효성 검사 규칙은 배포되는 각 파일의 배포 경로 속성에 이러한 유효한 문자가 포함되어 있는지 확인합니다.  
  
## 사용자 지정 필드를 만드는 경우의 오류  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 사용자 지정 필드는 XML로 정의됩니다.  필드가 정의되어 있지 않거나 특정 형식을 사용하여 참조되지 않는 경우 오류가 발생할 수 있습니다.  
  
### 오류 메시지  
 패키지 시 "잘못된 문자" 오류 메시지  
  
### 해결  
 필드 정의에 대한 ID는 다음 예제와 같이 반드시 중괄호로 묶은 GUID 여야 합니다.  
  
```  
<Field ID="{5744d18c-305e-4632-8bd1-09d134f4830d}"   
    Type="Note"   
    Name="PatientName"   
    DisplayName="Patient Name"   
    Group="A Custom Group">  
</Field>.  
```  
  
 아래의 예시가 보여주는 것처럼 콘텐츠 형식에서 필드 참조는 시작\/끝\(\<FieldRef\>\<\/FieldRef\>\) 요소가 아닌 빈 요소 형식\(\<FieldRef \/\>\) 을 사용하여 정의해야 합니다.  
  
```  
<FieldRef ID="{5744d18c-305e-4632-8bd1-09d134f4830d}"   
    Name="PatientName"   
    DisplayName="Patient Name"   
    Required="TRUE"/>  
```  
  
 필드에 대한 소스 XML이 잘못된 형식이거나 유효하지 않은 XML 파일이거나 문제를 나타내는 경우, "Cannot parse file" 오류가 발생합니다.  
  
## 배포 후 사이트 만들기 페이지에서 영어가 아닌 새 사이트 정의가 나타나지 않음  
 영어가 아닌 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 버전\(즉, 1033 외의 로캘 [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)] 를 사용하는 버전\)을 사용하여 새 사이트 정의를 만들고 배포한 후에는 **SharePoint 사용자 지정** 탭이 **템플릿 선택** 상자에 나타나지 않고 새 사이트 템플릿이 **새 SharePoint 사이트** 페이지에 나타나지 않습니다.  
  
### 오류 메시지  
 없음  
  
### 해결  
 이 문제는 webtemp\_SiteDefinitionProject1.xml과 같은 webtemp 사이트 정의 구성 파일의 **경로** 속성에 잘못된 값이 있기 때문에 발생합니다.  **배포 위치** 아래에 있는 webtemp 파일의 **경로** 속성에서 1033을 적절한 로캘 [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]로 변경합니다.  예를 들어, 일본어 로캘을 사용하려면 값을 1041로 변경합니다.  자세한 내용은 MSDN 웹 사이트의 [Locale IDs Assigned by Microsoft](http://go.microsoft.com/fwlink/?LinkID=165561) 을 참조하십시오.  
  
## 클린 시스템에 워크플로 프로젝트가 배포될 때 오류가 나타남  
 이 문제는 클린 시스템에 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에 워크플로 프로젝트를 배포하는 경우 발생합니다.  클린 시스템은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 와 SharePoint를 새로 설치해지만 배포된 워크플로 프로젝트를 가지지 않는 컴퓨터입니다.  
  
### 오류 메시지  
 SharePoint 목록을 찾을 수 없습니다. 워크플로 기록.  
  
### 해결  
 이 오류는 워크플로 기록 목록이 없기 때문에 발생합니다.  개발 환경이 클린 시스템이기 때문에 워크플로가 배포되지 않으며 워크플로 기록 목록이 아직 없습니다.  이 문제를 해결하려면 워크플로 마법사를 다시 열어 워크플로 기록 목록이 만들어지도록 합니다.  
  
##### 워크플로 마법사에 다시 들어가려면  
  
1.  **솔루션 탐색기**에서 워크플로 노드를 선택합니다.  
  
2.  **속성** 창에서 줄임표 단추\(…\)가 있는 임의의 속성에서 줄임표 단추를 클릭합니다.  
  
## 사용자가 디버깅 중에 업데이트된 이미지를 보려면 브라우저에서 응용 프로그램 페이지를 새로 고쳐야 함  
 [!INCLUDE[TLA2#tla_html](../sharepoint/includes/tla2sharptla-html-md.md)] 이미지 컨트롤과 같이 이미지를 표시하는 컨트롤이 있는 응용 프로그램 페이지가 포함된 SharePoint 솔루션을 디버깅하는 경우 이미지의 변경 내용을 표시하려면 브라우저에서 페이지를 새로 고쳐야 합니다.  
  
## 오류: 사이트 위치가 올바르지 않음  
 이 문제는 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)]이 설치되어 있지 않은 경우 발생할 수 있습니다.  또한 **SharePoint 사용자 지정 마법사**에서 지정된 SharePoint 웹 사이트에 대한 관리자 액세스 권한이 없는 경우에도 이 문제가 발생할 수 있습니다.  
  
### 오류 메시지  
  
-   SharePoint 사이트 위치가 잘못되었습니다.  
  
### 해결  
  
-   [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)]를 설치합니다.  
  
-   SharePoint 웹 사이트에 대한 관리자 액세스 권한이 있는지 확인합니다.  자세한 내용은 [!INCLUDE[TLA2#tla_office](../sharepoint/includes/tla2sharptla-office-md.md)] Online article [Grant access to the portal site](http://go.microsoft.com/fwlink/?LinkId=98310) 를 참조하십시오.  
  
## 사이트 삭제 웹 이벤트가 이벤트 수신자 프로젝트에서 발생하지 않음  
 이벤트 수신자 프로젝트를 만들고 "사이트 삭제 중" 같은 특정 웹 이벤트를 선택하면 해당 이벤트가 발생하지 않습니다.  
  
### 오류 메시지  
 없음  
  
### 해결  
 이 문제는 사이트 수준 이벤트를 처리하려면 기능 범위가 "사이트"여야 하지만 이벤트 수신자 프로젝트의 기본 기능 범위가 "웹"이기 때문에 발생합니다.  영향을 받는 웹 이벤트는 다음과 같습니다.  
  
-   사이트 삭제 중\(WebDeleting\)  
  
-   사이트 삭제됨\(WebDeleted\)  
  
-   사이트 이동 중\(WebMoving\)  
  
-   사이트 이동됨\(WebMoved\)  
  
 이 문제를 해결하려면 이벤트 수신자의 기능 범위를 다음과 같이 변경합니다.  
  
##### 이벤트 수신자의 기능 범위를 변경하려면  
  
1.  **솔루션 탐색기**에서, 파일을 더블 클릭하거나 바로가기 메뉴를 열고 **Open** 를 선택해서 **기능 디자이너** 에 있는 이벤트 수신자의 기능파일을 엽니다.  
  
2.  **Scope** 옆에 있는 화살표를 선택하고 나타나는 목록에서 **사이트** 를 선택합니다.  
  
## 비즈니스 데이터 연결 모델 프로젝트에서 식별자 이름이 변경된 후 배포 오류가 나타남  
 이 문제는 BDC\(비즈니스 데이터 연결\) 모델에서 엔터티의 식별자 이름을 변경한 후 솔루션을 배포하려고 하는 경우 발생합니다.  
  
### 오류 메시지  
  
-   \<*model name*\> has the following External Content Type activation errors ...  
  
-   The IMetadataObject with Name '\<*model name*\>' has a value in Field 'name' that is duplicated ...  
  
### 해결  
 이 문제를 해결하려면 수동으로 모델을 삭제한 다음 솔루션을 다시 배포합니다.  모델은 다음 도구 중 하나를 사용하여 삭제할 수 있습니다.  
  
-   SharePoint 2010 중앙 관리.  자세한 내용은 Microsoft TechNet 웹 사이트에서 [BDC Model Management](http://go.microsoft.com/fwlink/?LinkID=181472) 를 참조하십시오.  
  
-   Windows PowerShell.  명령 프롬프트에서 **Remove\-SPBusinessDataCatalogModel** 명령을 입력하여 모델을 삭제할 수 있습니다.  자세한 내용은 Microsoft TechNet 웹사이트의 [General cmdlets \(SharePoint Server 2010\)](http://go.microsoft.com/fwlink/?LinkID=182375) 를 참조하십시오.  
  
## SharePoint에서 비주얼 웹 파트를 보려고 하면 오류가 나타남  
 이 문제는 사용자 정의 컨트롤의 **경로** 속성이 "CONTROLTEMPLATES\\" 문자열로 시작되지 않는 경우 발생합니다.  
  
### 오류 메시지  
  
-   The file '\/\_CONTROLTEMPLATES\/*\<project name\>*\/*\<Web Part name\>*\/*\<user control name\>*.ascx' does not exist.  
  
-   '\/' 응용 프로그램의 서버 오류  
  
### 해결  
  
##### 이 문제를 해결하려면  
  
1.  **솔루션 탐색기**에서 파일 이름 확장명이 .ascx인 사용자 정의 컨트롤 파일을 선택 합니다.  
  
2.  메뉴 모음에서 **보기**, **속성 창**을 선택합니다.  
  
3.  **속성** 창에서 **배포 위치** 노드를 확장합니다.  
  
4.  **경로** 속성의 값이 "CONTROLTEMPLATES\\" 문자열로 시작되는지 확인합니다.  
  
## 작업 폼 필드가 포함된 가져온 다시 사용할 수 있는 워크플로가 실행될 때 오류가 나타남  
 이 문제는 필드가 있는 작업 폼이 포함된 워크플로를 가져온 다음 이 워크플로를 가져온 동일한 시스템에서 새 워크플로를 실행하는 경우 발생합니다.  
  
### 오류 메시지  
 배포 단계 '기능 활성화'에서 오류가 발생했습니다. 기능 \[*Guid*\]에 ID \[*Guid*\]\(으\)로 정의된 필드가 현재 사이트 모음 또는 하위 사이트에서 발견되었습니다.  
  
### 해결  
 이 오류는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 다시 사용할 수 있는 워크플로 프로젝트를 가져올 때 작업 폼 필드 ID가 변경되지 않기 때문에 발생하는 필드 ID 충돌의 결과입니다.  가져온 워크플로를 원래 워크플로가 포함된 동일한 서버에 배포하는 경우 필드 ID 충돌이 발생합니다.  
  
 이 문제를 해결하려면 찾기 및 바꾸기 기능을 사용하여 모든 가져온 워크플로 파일에서 필드 ID 특성의 값을 변경합니다.  
  
## 이름을 바꾼 가져온 목록 인스턴스가 실행될 때 오류가 나타남  
 이 문제는 가져온 목록 인스턴스의 이름을 바꾼 다음 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 실행하는 경우 발생합니다.  
  
### 오류 메시지  
 빌드 오류: 배포 단계 '기능 활성화'에서 오류가 발생했습니다. Template\\Features\\\[*import project* *feature* *name*\]\\Files\\Lists\\\[*old* *list name*\]\\Schema.xml 파일이 없습니다.  
  
### 해결  
 목록 인스턴스를 가져오는 경우 CustomSchema라는 특성이 목록 인스턴스의 Elements.xml 파일에 추가됩니다.  Elements.xml에는 목록 인스턴스에 대한 사용자 지정 schema.xml의 경로가 포함됩니다.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 목록 인스턴스의 이름을 바꾼 경우 사용자 지정 schema.xml의 배포 경로가 변경되지만 CustomSchema 특성의 경로 값은 업데이트되지 않습니다.  따라서 목록 인스턴스에서는 기능이 활성화될 때 CustomSchema 특성으로 지정된 이전 경로에서 schema.xml 파일을 찾을 수 없습니다.  
  
 이 문제를 해결하려면 CustomSchema 특성에서 schema.xml 파일의 배포 위치 경로를 업데이트합니다.  
  
## SharePoint 디버깅 세션이 IIS에 의해 종료됨  
 이 문제는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 솔루션에서 중단점을 설정하고 F5 키를 눌러 실행한 다음 90초 넘게 중단점에 머무르는 경우 발생합니다.  
  
### 오류 메시지  
 디버깅 중이던 웹 서버 프로세스가 IIS\(Internet Information Services\)에 의해 종료되었습니다.  IIS에서 응용 프로그램 풀 ping 설정을 구성하면 이 문제를 피할 수 있습니다.  자세한 내용은 도움말을 참조하십시오.  
  
### 해결  
 기본적으로 IIS 응용 프로그램 풀은 응용 프로그램이 응답할 때까지 90초 동안 대기한 후 응용 프로그램을 닫습니다.  이 프로세스를 응용 프로그램 "Ping"이라고 합니다.  이 문제를 해결하려면 대기 시간을 늘리거나 응용 프로그램 Ping을 완전히 사용하지 않도록 설정하면 됩니다.  
  
##### IIS 응용 프로그램 풀 설정에 액세스하려면  
  
1.  IIS 관리자를 엽니다.  
  
2.  **연결** 창에서 SharePoint 서버 노드를 확장하고 **응용 프로그램 풀** 노드를 클릭합니다.  
  
3.  **응용 프로그램 풀** 페이지에서 SharePoint 응용 프로그램 풀\(일반적으로 "SharePoint \- 80"\)을 선택한 다음 **작업** 창에서 **고급 설정** 링크를 선택합니다.  
  
4.  IIS 시간 제한 전에 대기 시간을 늘리려면 **Ping 최대 응답 시간\(초\)**의 값을 90초보다 큰 값으로 변경합니다.  
  
5.  IIS Ping을 사용하지 않도록 설정하려면 **Ping 사용**을 **False**로 설정합니다.  
  
## 자동 취소를 수행하면 SharePoint에서 고아 목록 인스턴스가 남음  
 이 문제는 다음 단계를 수행하는 경우 발생합니다.  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 목록 인스턴스가 있는 목록 정의를 만듭니다.  
  
2.  F5 키를 선택하여 솔루션을 실행합니다.  
  
3.  디버깅을 중지하거나 SharePoint 사이트를 닫습니다.  
  
4.  SharePoint 사이트를 다시 열고 목록 인스턴스를 엽니다.  
  
### 오류 메시지  
 '\/' 응용 프로그램의 서버 오류  
  
### 해결  
 이 문제는 SharePoint 솔루션의 디버그 세션을 닫은 후 자동 취소 기능으로 솔루션이 취소되기 때문에 발생합니다.  취소를 통해 SharePoint에서 목록 정의가 삭제되지만 목록의 인스턴스는 삭제되지 않습니다.  기본 목록 정의는 목록 인스턴스에 필요하지 않습니다.  
  
 이 문제를 해결하려면 메뉴 바에서 **빌드**, **배포**를 클릭하여 솔루션을 배포합니다. \(F5 키를 눌러서 솔루션을 디버깅 하지마십시오\) 그런 다음 SharePoint에서 목록 인스턴스를 삭제합니다.  
  
## 원래 SharePoint 솔루션이 내보낸 버전으로 대체됨  
 SharePoint 솔루션을 내보내고 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]로 가져온 다음 내보낸 동일한 사이트에 솔루션을 다시 배포하는 경우 원래 SharePoint 솔루션이 대체됩니다.  이 문제는 원래 솔루션이 활성화되지 않은 서버에 솔루션을 배포하는 경우 발생하지 않습니다.  
  
### 오류 메시지  
 없음  
  
### 해결  
 솔루션을 내보낸 사이트에서 솔루션을 덮어쓰지 않으려면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 프로젝트에서 모든 가져온 기능의 기능 ID와 SolutionID의 GUID를 변경합니다.  
  
## Error Appears when Debugging Starts  
 Visual Studio에서 SharePoint 솔루션의 디버깅을 시작할 때 지정한 키가 딕셔너리에 없기 때문에 Visual Studio에서 Web.config 구성 파일을 로드할 수 없다는 오류가 발생합니다.  
  
### 오류 메시지  
 Web.config 구성 파일을 로드할 수 없습니다.  파일에서 구성이 잘못된 XML 요소가 있는지 확인한 후 다시 시도하십시오.  다음 오류가 발생했습니다. 지정한 키가 사전에 없습니다.  
  
### 해결  
 이 문제를 해결하려면 Visual Studio에서 SharePoint 프로젝트의 사이트의 URL 속성 값이 웹 응용 프로그램의 대체 액세스 매핑에 대한 기본 영역에 할당된 URL과 일치하는지 확인합니다.  인트라넷과 같은 다른 영역을 URL에 사용하면 오류가 해결되지 않습니다.  프로젝트의 사이트 URL과 기본 영역의 URL은 반드시 동일해야 합니다.  액세스 대체 매핑에 액세스하려면, SharePoint 2010 Central Administration utility 를 열고 **응용 프로그램 관리** 링크를 선택한 후 **웹 응용 프로그램** 에서 **대체 액세스 매핑 구성** 링크를 선택합니다.  자세한 정보는 [Create zones for Web applications](http://go.microsoft.com/fwlink/?LinkId=192274) 를 참조하십시오.  
  
## 참고 항목  
 [SharePoint 패키징 및 배포 문제 해결](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md)   
 [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)   
 [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md)  
  
  