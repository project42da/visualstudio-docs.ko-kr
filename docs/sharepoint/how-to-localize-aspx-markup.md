---
title: '방법: ASPX 태그 지역화 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- localizing XML [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9dd127fea21a53b9a29082f536ac8c0404299c63
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-localize-aspx-markup"></a>방법: ASPX 태그 지역화
  [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] (.aspx) 페이지는 일반적으로 하드 코드 된 문자열 값을 사용합니다. 이러한 문자열을 지역화 하려면 지역화 된 리소스를 참조 하는 식으로 대체 합니다.  
  
## <a name="localizing-aspx-markup"></a>ASPX 태그 지역화  
  
#### <a name="to-localize-aspx-markup"></a>ASPX 태그 지역화  
  
1.  별도 리소스 파일 추가: 기본 언어와 각 지역화 된 언어입니다.  
  
     태그 및 코드가 아닌 지역화 하는 경우에 전역 리소스 파일 프로젝트 항목을 추가 합니다. 코드 및 태그 지역화 하는 경우 리소스 파일 프로젝트 항목을 추가 합니다.  
  
    1.  전역 리소스 파일을 추가 하려면 **솔루션 탐색기**을 SharePoint 프로젝트 항목에 대 한 바로 가기 메뉴를 열고 다음 선택 **추가**, **새 항목**합니다. SharePoint에서 **2010** 노드를 선택는 **전역 리소스 파일** 템플릿.  
  
    2.  리소스 파일을 추가 하려면 **솔루션 탐색기**을 SharePoint 프로젝트 항목에 대 한 바로 가기 메뉴를 열고 다음 선택 **추가**, **새 항목**합니다. 아래의 **Visual Basic** 또는 **Visual C#** 노드를 선택는 **리소스 파일** 템플릿.  
  
    > [!NOTE]  
    >  배포 유형의 속성을 사용 하는 SharePoint 프로젝트 항목에 리소스 파일을 추가 해야 합니다. 이 속성은이 절차의 뒷부분에 나오는 필요 합니다. 솔루션에 SharePoint 프로젝트 항목을 찾을 수 없는 경우 빈 SharePoint 프로젝트를 추가 하 고 해당 기본 Elements.xml 파일을 제거할 수 있습니다.  
  
2.  기본 언어 리소스 파일 MyAppResources.resx 같은.resx 확장명을 추가 하거나 원하는 이름을 지정 합니다. 지역화된 각 리소스 파일에 동일한 기본 이름을 사용하지만 문화권 [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]를 추가합니다. 예를 들어 독일어 지역화 된 리소스 MyAppResources.de 같은 이름을 지정 합니다.  
  
3.  값을 변경는 **배포 유형을** 각 리소스 파일의 속성 **AppGlobalResource** 서버의 App_GlobalResources 폴더에 배포 하도록 합니다.  
  
4.  ASPX 태그 외에 코드도 지역화 하는 리소스를 사용 하는 경우의 값을 두고는 **빌드 작업** 으로 각 파일의 속성 **포함 리소스**합니다. 태그를 지역화 하는 리소스 파일을 사용 하는 파일의 속성 값 필요에 따라 변경할 수 있습니다 **콘텐츠**합니다. 자세한 내용은 참조 [SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)합니다.  
  
5.  각 리소스 파일을 열고 각 파일에 동일한 문자열 Id를 사용 하 여 지역화 된 문자열을 추가 합니다.  
  
6.  에 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] ASPX 페이지 또는 컨트롤에 대 한 태그 형식을 사용 하는 값으로 하드 코드 된 문자열을 바꿉니다.  
  
    ```  
    <%$Resources:Resource File Name, String ID%>  
    ```  
  
     예를 들어 응용 프로그램 페이지에서 레이블 컨트롤에 대 한 텍스트를 지역화 하려면 다음과 같이 변경  
  
    ```  
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">  
    <asp:Label ID="lbl" runat="server" Text="Label text"></asp:Label>  
    </asp:Content>  
    ```  
  
     다음으로 변경:  
  
    ```  
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">  
    <asp:Label ID="lbl" runat="server" Text="<%$Resources:MyAppResources,String1%>"></asp:Label>  
    </asp:Content>  
    ```  
  
7.  F5 키를 선택하여 응용 프로그램을 빌드하고 실행합니다.  
  
8.  Sharepoint의 기본에서 표시 언어를 변경 합니다.  
  
     지역화 된 문자열 응용 프로그램에 나타납니다. 지역화 된 리소스를 표시 하려면 SharePoint 서버에서 리소스 파일의 문화권과 일치 하는 언어 팩 설치 되어 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)   
 [방법: 기능 지역화](../sharepoint/how-to-localize-a-feature.md)   
 [방법: 리소스 파일 추가](../sharepoint/how-to-add-a-resource-file.md)   
 [방법: 코드 지역화](../sharepoint/how-to-localize-code.md)  
  
  