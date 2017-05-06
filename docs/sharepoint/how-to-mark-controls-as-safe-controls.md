---
title: "방법: 컨트롤을 안전 컨트롤로 표시"
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
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "안전 컨트롤[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 고급 패키징 도구"
  - "Visual Studio에서 SharePoint 개발, 안전 컨트롤"
ms.assetid: 813727d5-6750-407c-a23e-c38dd611e78c
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# 방법: 컨트롤을 안전 컨트롤로 표시
  보안을 위해 SharePoint에서는 스크립트 삽입에 대해 보호되는 웹 컨트롤과 보호되지 않는 웹 컨트롤을 구분합니다.  보호되는 컨트롤, 즉 *안전 컨트롤*은 신뢰할 수 없는 사용자가 액세스할 수 있습니다.  패키지에 어셈블리를 추가할 때 SharePoint 프로젝트 항목의 안전 컨트롤 항목 속성이나 **패키지 디자이너**에서 컨트롤을 안전한 것으로 표시할 수 있습니다.  자세한 내용은 다음을 참조하십시오.  
  
 [web.config 파일 설정 변경](http://go.microsoft.com/fwlink/?LinkId=178965) 및 [웹 파트 어셈블리를 안전한 컨트롤로 등록](http://go.microsoft.com/fwlink/?LinkId=171013).  
  
> [!IMPORTANT]  
>  이러한 절차는 설명 용도로만 제공됩니다.  컨트롤이 안전하다고 확신하는 경우에만 컨트롤을 안전한 것으로 표시하십시오.  
  
## 안전 컨트롤 항목 속성에서 안전 컨트롤 표시  
  
#### 안전 컨트롤 항목 속성에서 컨트롤을 안전한 것이나 안전하지 않은 것으로 표시하려면  
  
1.  비주얼 웹 파트 프로젝트를 사용하여 SharePoint 솔루션을 만듭니다.  
  
2.  웹 파트에 텍스트 상자 컨트롤과 단추 컨트롤을 추가합니다.  이름을 기본값\(각각 TextBox1 및 Button1\)으로 그대로 둡니다.  
  
3.  웹 파트의 **안전 컨트롤 항목** 속성에 두 항목을 추가합니다.  이렇게 하려면 **속성** 창에서 **안전 컨트롤 항목** 옆에 있는 줄임표\(![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.png "ASP.NET 모바일 디자이너 줄임표")\) 버튼을 선택합니다.  
  
     **안전 컨트롤 항목** 대화 상자가 나타납니다.  
  
4.  **안전 컨트롤 항목** 대화 상자에서 **추가** 버튼을 선택하여 단추와 텍스트 상자에 해당하는 두 안전 컨트롤 항목을 **멤버** 창에 추가합니다.  
  
5.  첫 번째 안전 컨트롤 항목을 선택한 다음 **안전** 속성을 **False**로, **형식 이름** 속성을 **Button1**로, **스크립트에 대해 안전** 속성을 **False**로 변경합니다.  
  
     이 단계는 단추 컨트롤을 안전하지 않은 컨트롤로 식별합니다.  
  
6.  목록에서 두 번째 안전 컨트롤 항목을 선택합니다.  **안전** 속성의 값을 **True** 로 두고 **형식 이름** 속성을 **TextBox1** 로, **스크립트에 대해 안전** 속성을 **True** 로 설정합니다.  
  
     텍스트 상자 컨트롤이 이제 스크립트 삽입에 대해 안전한 컨트롤로 표시되었습니다.  
  
7.  **확인** 버튼을 선택하여 대화 상자를 닫습니다.  
  
## 패키지 디자이너에서 안전 컨트롤 표시  
  
#### 패키지 디자이너에서 컨트롤을 안전한 것이나 안전하지 않은 것으로 표시하려면  
  
1.  비주얼 웹 파트 프로젝트를 사용하여 SharePoint 솔루션을 만듭니다.  
  
2.  웹 파트에 텍스트 상자 컨트롤과 단추 컨트롤을 추가합니다.  이름을 기본값\(각각 TextBox1 및 Button1\)으로 그대로 둡니다.  
  
     나중에 사용되므로 컨트롤의 네임스페이스를 기록해 둡니다.  
  
3.  프로젝트를 빌드하려면 메뉴 표시줄에서 **빌드**, **솔루션 빌드** 를 선택합니다.  
  
4.  다른 SharePoint 솔루션을 만듭니다.  
  
5.  **솔루션 탐색기** 에서 Package.Package 파일에 대한 바로 가기 메뉴를 연 다음, **열기** 를 선택하여 **패키지 디자이너** 를 엽니다.  
  
6.  **패키지 디자이너**에서 **고급** 탭을 선택합니다.  
  
7.  **추가 어셈블리** 아래에서 **추가** 버튼을 선택하고 목록에서 **기존 어셈블리 추가** 를 선택합니다.  
  
8.  **기존 어셈블리 추가** 대화 상자에서 **소스 경로** 옆의 줄임표\(![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.png "ASP.NET 모바일 디자이너 줄임표")\) 버튼을 선택합니다.  
  
9. 1 단계에서 만든 SharePoint 솔루션에서 어셈블리를 선택한 다음 **열기** 버튼을 선택합니다.  
  
10. 이 예제의 경우 **배포 대상** 옵션을 GlobalAssemblyCache로 둡니다.  
  
     이 단계를 수행하면 어셈블리가 시스템 GAC\(전역 어셈블리 캐시\)에 배포됩니다.  어셈블리가 웹 응용 프로그램\(Bin\) 폴더에 배포되게 하려면 해당 옵션을 대신 선택합니다.  자세한 내용은 [SharePoint 기반에서 웹 파트 배포](http://go.microsoft.com/fwlink/?LinkId=177509) 를 참조하십시오.  
  
11. **안전 컨트롤** 상자에서 **새 항목을 추가하려면 여기를 클릭하십시오.** 버튼을 선택합니다.  
  
12. 다음 표에 있는 속성의 값을 입력합니다.  
  
    |속성 이름|값|  
    |-----------|-------|  
    |네임스페이스|**BdcModelProject1.VisualWebPart1**과 같은 컨트롤의 정규화된 네임스페이스입니다.|  
    |형식 이름|Button1|  
    |어셈블리 이름|Microsoft.Office.SharePoint.ClientExtensions, Version\=14.0.0.0, Culture\=neutral, PublicKeyToken\=71e9bce111e9429c와 같은 강력한 어셈블리 이름입니다.|  
    |안전|**안전** 확인란의 선택을 취소합니다.|  
    |스크립트에 대해 안전|**스크립트에 대해 안전** 확인란을 선택 취소된 상태로 둡니다.|  
  
    > [!NOTE]  
    >  **패키지 디자이너**의 **고급** 탭을 통해 추가된 어셈블리의 **어셈블리 이름** 값은 토큰일 수 없으며 강력한 이름의 어셈블리여야 합니다.  자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](http://go.microsoft.com/fwlink/?LinkId=177513) 을 참조하십시오.  
  
13. Tab 키를 눌러 다른 안전 컨트롤 항목을 만듭니다.  
  
14. **새 항목을 추가하려면 여기를 클릭하십시오.** 버튼을 다시 선택합니다.  
  
15. 다음 표에 있는 속성의 값을 입력합니다.  
  
    |속성 이름|값|  
    |-----------|-------|  
    |네임스페이스|**BdcModelProject1.VisualWebPart1**과 같은 컨트롤의 정규화된 네임스페이스입니다.|  
    |형식 이름|TextBox1|  
    |어셈블리 이름|Microsoft.Office.SharePoint.ClientExtensions, Version\=14.0.0.0, Culture\=neutral, PublicKeyToken\=71e9bce111e9429c와 같은 강력한 어셈블리 이름입니다.|  
    |안전|**안전** 확인란을 선택합니다.|  
    |스크립트에 대해 안전|**스크립트에 대해 안전** 확인란을 선택합니다.|  
  
16. Tab 키를 누른 다음 **확인** 버튼을 선택하여 대화 상자를 닫습니다.  
  
## 참고 항목  
 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  