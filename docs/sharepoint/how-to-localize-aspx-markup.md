---
title: "방법: ASPX 태그 지역화"
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
  - "XML 지역화[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 지역화"
ms.assetid: 9559a1d1-6558-4c24-a51e-c6ee79432778
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# 방법: ASPX 태그 지역화
  [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)]\(.aspx\) 페이지에서는 일반적으로 하드 코드된 문자열 값을 사용합니다.  이러한 문자열을 지역화하려면 지역화된 리소스를 참조하는 식으로 문자열을 바꿉니다.  
  
## ASPX 태그 지역화  
  
#### ASPX 태그를 지역화하려면  
  
1.  기본 언어와 지역화된 언어마다 하나씩 별도의 리소스 파일을 추가합니다.  
  
     코드를 제외하고 태그만 지역화하는 경우 전역 리소스 파일 프로젝트 항목을 추가합니다.  코드와 태그를 지역화하는 경우에는 리소스 파일 프로젝트 항목을 추가합니다.  
  
    1.  전역 리소스 파일을 추가 하려면, **솔루션 탐색기** 에서 SharePoint 프로젝트 항목에 대한 바로 가기 메뉴를 연 다음 **추가**, **새 항목** 을 선택합니다.  SharePoint **2010** 노드 아래의 **전역 리소스 파일** 템플릿을 선택합니다.  
  
    2.  리소스 파일을 추가 하려면, **솔루션 탐색기** 에서 SharePoint 프로젝트 항목에 대한 바로 가기 메뉴를 연 다음 **추가**, **새 항목** 을 선택합니다.  **Visual Basic** 또는 **C\#** 노드를 아래의 **리소스 파일** 템플릿을 선택합니다.  
  
    > [!NOTE]  
    >  리소스 파일을 SharePoint 프로젝트 항목에 추가하여 배포 형식 속성을 사용할 수 있도록 설정합니다.  이 속성은 이 절차에서 이후에 필요합니다.  솔루션에 SharePoint 프로젝트 항목이 없는 경우 빈 SharePoint 프로젝트를 추가하고 기본 Elements.xml 파일을 제거할 수 있습니다.  
  
2.  기본 언어 리소스 파일에 선택한 이름을 지정하고 .resx 확장명을 추가합니다\(예: MyAppResources.resx\).  각 지역화된 리소스 파일에 동일한 기본 이름을 사용하고, 문화권 [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]를 추가합니다.  예를 들어, 독일어 지역화된 리소스의 이름을 MyAppResources.de\-DE.resx로 지정합니다.  
  
3.  각 리소스 파일의 **배포 형식** 속성의 값을 **AppGlobalResource**로 변경하여 파일들이 서버의 App\_GlobalResources 폴더에 배포되도록 합니다.  
  
4.  리소스를 사용하여 ASPX 태그 외에 코드도 지역화하는 경우 각 파일의 **빌드 작업** 속성의 값을 **포함 리소스**로 둡니다.  리소스 파일을 사용하여 태그만 지역화하는 경우에는 선택적으로 파일의 속성 값을 **내용**으로 변경할 수 있습니다.  자세한 내용은 [SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)을 참조하십시오.  
  
5.  각 리소스 파일을 열고 지역화된 문자열을 추가합니다. 이때 각 파일에서 동일한 문자열 ID를 사용합니다.  
  
6.  ASPX 페이지 또는 컨트롤의 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 태그에서 하드 코드된 문자열을 다음 형식을 사용하는 값으로 바꿉니다.  
  
    ```  
    <%$Resources:Resource File Name, String ID%>  
    ```  
  
     예를 들어, 응용 프로그램 페이지에서 레이블 컨트롤의 텍스트를 지역화하려면 다음과 같이 변경합니다.  
  
    ```  
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">  
    <asp:Label ID="lbl" runat="server" Text="Label text"></asp:Label>  
    </asp:Content>  
    ```  
  
     를 다음으로 변경:  
  
    ```  
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">  
    <asp:Label ID="lbl" runat="server" Text="<%$Resources:MyAppResources,String1%>"></asp:Label>  
    </asp:Content>  
    ```  
  
7.  프로젝트를 빌드하고 실행하려면 F5 키를 선택합니다.  
  
8.  SharePoint에서 기본 표시 언어를 변경합니다.  
  
     지역화된 문자열이 응용 프로그램에 표시됩니다.  지역화된 리소스를 표시하려면 SharePoint 서버에 리소스 파일의 문화권과 일치하는 언어 팩이 설치되어 있어야 합니다.  
  
## 참고 항목  
 [SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)   
 [방법: 기능 지역화](../sharepoint/how-to-localize-a-feature.md)   
 [방법: 리소스 파일 추가](../sharepoint/how-to-add-a-resource-file.md)   
 [방법: 코드 지역화](../sharepoint/how-to-localize-code.md)  
  
  