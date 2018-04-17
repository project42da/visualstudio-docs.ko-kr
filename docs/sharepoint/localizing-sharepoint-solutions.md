---
title: SharePoint 솔루션 지역화 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.GlobalAndFeatureResource
- VS.SharePoint.Project.AddResourceDialog
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- globalizing [SharePoint development in Visual Studio]
- localizing [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 86ffb2795d5e2a9b9583360146c4bb1d2556b9a1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="localizing-sharepoint-solutions"></a>SharePoint 솔루션 지역화
  전 세계적으로 사용 될 수 있도록 응용 프로그램을 준비 하는 과정을 지역화 라고 합니다. 지역화를 특정 문화권 리소스를 번역 됩니다. 자세한 내용은 참조 [전역화 및 지역화 응용 프로그램](/visualstudio/ide/globalizing-and-localizing-applications)합니다. 이 항목 SharePoint 솔루션 지역화 하는 방법에 대 한 개요를 제공 합니다.  
  
 솔루션을 지역화 하려면 코드에서 하드 코드 된 문자열을 제거 하 고 리소스 파일에 추상화 합니다. 리소스 파일은 한 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]-.resx 확장명을 가진 파일을 기반으로 합니다. 솔루션에 사용 되는 문자열의 번역 된 버전을 포함 하는 리소스 파일입니다. 자세한 내용은 참조 [응용 프로그램의 리소스](http://go.microsoft.com/fwlink/?LinkID=155844)합니다.  
  
> [!NOTE]  
>  SharePoint 솔루션 리소스 파일에만 문자열 리소스를 추가 합니다. 리소스 편집기를 사용 하면 문자열이 아닌 리소스를 추가, 있지만 SharePoint에 문자열이 아닌 리소스 배포 하지 않습니다.  
  
## <a name="resource-files"></a>리소스 파일  
 리소스 파일의 세 종류: default, 언어 중립 및 특정 언어 관련 됩니다.  
  
|리소스 파일 형식|설명|  
|------------------------|-----------------|  
|기본|라고도 대체 (fallback) 리소스에 기본 리소스 파일 영어와 같이 기본 문화권에 대 한 지역화 된 문자열을 포함 합니다. 지정된 된 언어에 대 한 지역화 된 리소스 파일을 찾을 수 있는 경우 사용 됩니다. 기본 리소스 별도 파일 필요는 없으며, 주 응용 프로그램 어셈블리에 저장 됩니다.|  
|중립 언어|언어만 하지 특정 문화권에 대 한 지역화 된 문자열을 포함 하는 리소스 파일입니다. 예를 들어 프랑스어 "fr"입니다.|  
|언어별|언어와 문화권에 대 한 지역화 된 문자열을 포함 하는 리소스 파일입니다. 예를 들어, "fr CA" 프랑스어 캐나다에 대 한 합니다.|  
  
 자세한 내용은 참조 [리소스 지역화를 위한의 계층적 구성](http://go.microsoft.com/fwlink/?LinkId=178360)합니다.  
  
 개발 하는 SharePoint 프로젝트에 기본 리소스 파일을 지정 하려면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 선택 **고정 언어 (고정 국가)** 문화권 목록에는 **리소스 추가** 대화 상자가 있습니다 리소스 파일을 추가 합니다.  
  
## <a name="localizing-visual-studio-sharepoint-solutions"></a>Visual Studio SharePoint 솔루션 지역화  
 솔루션을 지역화 하는 경우 솔루션에 사용자에 게 표시 하는 텍스트 정보의 모든 고려해 야 합니다. 정보 메시지, 오류 메시지 및 [!INCLUDE[TLA2#tla_ui](../sharepoint/includes/tla2sharptla-ui-md.md)] 문자열을 변환 해야 하 고 리소스 파일에 이러한 번역을 포함 합니다.  
  
 리소스 파일에서 모든 문자열에는 고유 식별자입니다. 각 리소스 파일에 번역된 된 문자열에 동일한 식별자를 사용 합니다. 예를 들어 "String1"는 기본 리소스 파일의 첫 번째 문자열에 대 한 식별자, 언어 관련 리소스 파일의 첫 번째 문자열에 대 한 동일한 식별자를 사용 합니다.  
  
 세 가지 부분에서 일반적으로 지역화 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 응용 프로그램: 기능, ASPX 페이지 태그 및 코드입니다. 설명을 위해 다음 섹션에서는 독일어와 일본어로 지역화 하려고 하는 SharePoint 솔루션을 있다고 가정 합니다. 기본 언어는 영어입니다.  
  
### <a name="localizing-features"></a>기능 지역화  
 기능을 지역화 하려면 번역 된 제목 및 지역화 된 리소스 파일에 문자열을 참조 하는 식으로 하드 코드 된 제목과 설명을 기능을 대체 해야 합니다. 변경 된 **기능 디자이너** 에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 자세한 내용은 참조 [하는 방법: 기능 지역화](../sharepoint/how-to-localize-a-feature.md)합니다.  
  
 독일어와 일본어로 영어 기능을 지역화 하려면 프로젝트에 세 개의 리소스 파일 프로젝트 항목 추가: 영어, 독일어 및 일본어입니다. ASPX 태그 또는 코드가; 필드를 지역화 기능 리소스 파일을 사용할 수 없습니다. 별도 리소스 파일은 해당 필요 합니다.  
  
 기능 리소스 파일을 만든 후에 번역 된 문자열을 추가 합니다. 다음과 같은 형식의 식으로 지역화 된 문자열에 액세스 합니다.  
  
```  
$Resources:String ID  
```  
  
 기능에 대 한 리소스 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 리소스인 항상 합니다. 고정 언어, 문화권 이외의 언어를 선택 하는 경우 [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)] 리소스 파일 이름에 추가 됩니다. 예를 들어, 기본값인 고정 언어 기능 리소스 파일을 추가 하는 경우 Resources.resx 호출 됩니다. 일본어 (일본) 문화권을 선택 하 여 특정 언어 관련 기능 리소스를 추가 하는 경우 파일 Resources.ja JP.resx 라고 합니다. 기능 리소스 파일 이름은 자동으로 할당 됩니다 및 변경할 수 없습니다.  
  
 기능 리소스의 범위에 추가 된 기능에 로컬입니다. 솔루션의 기능이 나 요소가 파일에서 사용할 수 있는 리소스를 만들려면 추가 **전역 리소스 파일** 기능 리소스 파일 대신 프로젝트 항목입니다. **전역 리소스 파일** 프로젝트 항목에는 **2010** 아래에 폴더 **SharePoint** 에 **새 항목 추가** 대화 상자. 전역 리소스 파일의 SharePoint 루트 폴더 \Resources 폴더에 배포합니다.  
  
### <a name="localizing-aspx-page-markup"></a>ASPX 페이지 태그 지역화  
 필드를 지역화 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 페이지, 프로젝트에 3 개의 리소스 파일의 프로젝트 항목 추가: 영어, 독일어 및 일본어입니다. 태그 외에 코드도 지역화 해야 하는 경우 대신 전역 리소스 파일을 추가할 수 있습니다.  
  
 기본 언어 리소스 파일에 대 한 이름을 제공 합니다. 지역화 된 리소스 파일 추가 언어별 culture와 동일한 이름을 지정 [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]합니다. 예를 들어, 독일어 MyAppResources.de 같 및 일본어 MyAppResources.ja JP.resx 합니다.  
  
 설정의 **배포 유형을** 각 리소스 파일의 속성 **AppGlobalResource**합니다. 이렇게 하면 리소스 파일은 솔루션에 있는 모든 컨트롤과 ASPX 페이지에서 사용할 수는 App_GlobalResources 폴더에 배포 되도록 합니다. C:\inetpub\wwwroot\wss\VirtualDirectories App_GlobalResources 폴더에\\< 포트 번호\>\App_GlobalResources 합니다.  
  
> [!NOTE]  
>  비전역 리소스 파일을 사용 하는 경우 배포 유형 속성 및 기타 SharePoint 관련 속성을 사용 하도록 설정 하려면 프로젝트 항목 폴더로 이동 합니다.  
  
 코드 필드를 지역화 ASPX 태그 리소스 파일을 사용할 수도 있습니다. ASPX 태그 외에 코드도 지역화 하는 리소스를 사용 하는 경우 빌드 작업 속성의 설정을 그대로 적용 각 파일 리소스가 포함 리소스로 위성 어셈블리로 컴파일할 수 있습니다. 그러나 태그 지역화 하는 리소스 파일을 사용 중인 파일을 기본 응용 프로그램 어셈블리로 컴파일할 방지 하기 위해 콘텐츠를 빌드 작업 필요에 따라 변경할 수 있습니다.  
  
 ASPX 페이지 및 컨트롤 태그에 있는 모든 속성 하드 코드 된 문자열을 다음과 같은 형식의 식으로 바꿉니다.  
  
```  
<asp:<class> runat="server" Text="<%$Resources:<Resource File Name>, <String ID>%>" />  
```  
  
 예를 들어:  
  
```  
<asp:Button ID="btn1" runat="server" onclick="btn1_Click" Text="<%$Resources:Resource1,String7%>"></asp:Button>  
```  
  
 텍스트로 ASPX에 대 한 다음과 같은 형식의 식을 사용 합니다.  
  
```  
<asp:literal ID="<ID>" runat="server" Text="<%$Resources:<Resource File Name>, <String ID>%>" />  
```  
  
 예를 들어:  
  
```  
<asp:literal ID="Literal1" runat="server" Text="<%$Resources:Resource1, String9%>" />  
```  
  
 자세한 내용은 참조 [하는 방법: ASPX 태그 지역화](../sharepoint/how-to-localize-aspx-markup.md)합니다.  
  
### <a name="localizing-code"></a>코드 지역화  
 문자열 기능을 지역화 하는 것 외에도 및 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 태그 있습니다 메시지 문자열 및 솔루션 코드에 표시 된 오류 문자열 필드를 지역화 합니다. 지역화 된 정보 및 오류 메시지는 위성 어셈블리에 포함 되어 있습니다. 위성 어셈블리와 같은 사용자에 게 표시 되는 문자열이 포함 [!INCLUDE[TLA2#tla_ui](../sharepoint/includes/tla2sharptla-ui-md.md)] 텍스트와 출력 메시지 예외를 선택 합니다.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 표준.NET Framework 허브 및 스포크 모델을 사용합니다. 허브 또는 주 프로그램 어셈블리에는 기본 언어 리소스가 포함 되어 있습니다. 스포크 또는 위성 어셈블리 언어 관련 리소스를 포함합니다. 자세한 내용은 [리소스 패키지 및 배포](http://go.microsoft.com/fwlink/?LinkId=179280)를 참조하세요. 위성 어셈블리는 리소스 (.resx) 파일에서 컴파일됩니다. 프로젝트 및 솔루션 패키지 언어 관련 리소스 파일을 추가 하면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 를 명명 된 위성 어셈블리에 리소스 파일을 컴파일합니다 *프로젝트 이름을*. resources.dll 합니다.  
  
 ASPX 태그와 마찬가지로; 프로젝트에 별도 리소스 파일의 프로젝트 항목을 추가 하 여 SharePoint 응용 프로그램 코드 지역화 기본 언어 마다 하나씩 지역화 된 언어입니다. 그러나 ASPX 태그 지역화를 위한 리소스 파일이 이미 있는 경우 이전에 언급 했 듯이 재사용할 수 있습니다 코드 지역화에 대 한 합니다. 리소스 파일을 만들도록 해야 할 경우 기본 언어 리소스 파일을.resx 확장명을 추가 하거나 원하는 이름을 지정 합니다. 지역화 된 리소스 파일의 이름을 언어별로 문화권이 추가 된 동일한 이름과 이름 [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]합니다. 포함 리소스 위성 리소스 어셈블리를 만들 수 있도록 하려면 각 리소스 파일의 빌드 작업 속성을 설정 합니다.  
  
 위성 어셈블리를 만들려면 프로젝트를 빌드하고 추가한 다음 파일을 통해 추가 어셈블리로 **고급** 탭은 **패키지 디자이너**합니다. 어셈블리를 추가할 때 추가 문화권 [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)] DE-DE 등 위치 경로에 폴더\\*프로젝트 항목 이름*. resources.dll 합니다. 이 패키지를를 동일한 이름의 파일을 포함할 수 있습니다.  
  
 코드를 바꿉니다 하드 코드 된 문자열에 대 한 호출에서 <xref:System.Web.HttpContext.GetGlobalResourceObject%2A> 다음 구문을 사용 하 여 메서드:  
  
```  
HttpContext.GetGlobalResourceObject("<Resource File Name>", "<String ID>")  
```  
  
 자세한 내용은 참조 [하는 방법: 코드 지역화](../sharepoint/how-to-localize-code.md)합니다.  
  
#### <a name="web-part-code-localization"></a>웹 파트 코드 지역화  
 웹 파트 WebDisplayName, 범주 및 WebDescription 같은 하드 코드 된 문자열을 사용 하는 코드 특성을 포함 하는 사용자 지정 속성 편집기 기능을 포함 합니다. 이러한 특성에 대 한 문자열 값을 대체 하려면 특성의 클래스에서 파생 되는 별도 클래스를 만듭니다. 이러한 클래스에 특성의 속성을 설정 합니다. 특성 속성의 기본 클래스에 따라 달라 집니다. 예를 들어 WebDisplayName 특성 속성은 DisplayNameValue WebDescription 특성 속성은 DescriptionValue 하며  
  
 파생된 클래스에서 참조 되는 리소스 파일 및 문자열 ID에 대 한 지역화 된 값을 가져올 ResourceManager 개체에서 문자열 ID 속성 편집기 특성에이 값을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 기능 지역화](../sharepoint/how-to-localize-a-feature.md)   
 [방법: ASPX 태그 지역화](../sharepoint/how-to-localize-aspx-markup.md)   
 [방법: 코드 지역화](../sharepoint/how-to-localize-code.md)   
 [방법: 리소스 파일 추가](../sharepoint/how-to-add-a-resource-file.md)   
 [방법: 리소스 파일을 사용하여 지역화된 이름, 속성 및 사용 권한 지정](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)  
  
  