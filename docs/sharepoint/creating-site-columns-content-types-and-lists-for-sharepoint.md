---
title: "SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기 | Microsoft Docs"
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
  - "VS.SharePointTools.ListDesigner.ContentTypeSetting"
  - "VS.SharePointTools.ContentTypeDesigner.CommonPropertiesPage"
  - "VS.SharePointTools.ListDesigner.CreatingLists"
  - "VS.SharePointTools.ListDesigner.ListPage"
  - "VS.SharePointTools.ListDesigner.ViewPage"
  - "VS.SharePointTools.ListDesigner.CommonPropertiesPage"
  - "VS.SharePointTools.ContentTypeDesigner.ColumnsPage"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 9ceed263-3aec-41dc-8708-63cb37a08fa8
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기
  Visual Studio는 많은 기본 SharePoint 항목에 대해 사이트 열\(또는 *필드*\)을 통합할 수 있는 *표시* 및 *콘텐츠 형식* 을 포함한 프로젝트 항목 템플릿을 제공합니다.  콘텐츠 형식 및 목록에 대한 새로운 디자이너가 이러한 항목을 더 쉽게 만들어 줍니다.  
  
## 사이트 열  
 사이트 열은 SharePoint 프로젝트에 추가할 수 있는 가장 기본적인 요소 중 하나입니다.  사이트 열은 전화 번호, 텍스트 메모, 또는 연락처 목록에서 연락처의 도시 이름 등의 데이터 형식을 나타냅니다.  
  
 새 사이트 열 프로젝트 항목 템플릿은 Visual Studio의 이전 버전보다 사이트 열을 쉽게 생성하도록 만듭니다.  새 사이트 열을 만든 후, SharePoint에서 사이트 열을 나타낼 위치의 표시 이름, 데이터 형식, 그룹과 같은 원하는 정보를 포함 하도록 사이트 열의 Elements.xml 파일에서 XML을 수정할 수 있습니다.  사이트 열에 대한 자세한 내용은 [열에 대한 소개](http://go.microsoft.com/fwlink/?LinkId=224996) 을 참조하십시오.  
  
## 콘텐츠 형식 및 목록  
 콘텐츠 형식과 목록은 SharePoint에서 가장 자주 사용되는 요소입니다.  
  
 콘텐츠 형식은 SharePoint 목록 또는 문서 라이브러리에서 메타 데이터, 워크플로 및 항목의 범주에 대한 동작을 정의합니다.  예를 들어, 연락처 목록 또는 작업 목록에서 정보에 대한 콘텐츠 형식을 만들 수 있습니다.  연락처 콘텐츠 형식은 이름, 전자 메일, 전화 번호 및 주소 등의 열을 포함할 수 있습니다.  사이트 수준에서 정의하는 콘텐츠 형은식 사이트의 모든 목록 또는 문서 라이브러리에 독립적입니다.  SharePoint 사이트에서 다른 목록 또는 문서 라이브러리를 사용하여 동일한 콘텐츠 형식을 사용할 수 있습니다.  또한 같은 목록이나 문서 라이브러리에서 여러 콘텐츠 형식을 사용할 수도 있습니다.  
  
 목록은 다른 사용자와 공유할 수 있는 SharePoint 정보의 모음입니다.  데이터를 포함하는 열의 행을 포함하는 목록.  그룹의 몇 가지 예: 작업 목록, 연락처 목록 및 공지 사항 목록.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에서 새 콘텐츠 형식 및 목록 디자이너는 이전 버전의 Visual Studio 보다 사이트 콘텐츠 형식 만들기를 보다 쉽고 직관적으로 하도록 해줍니다,  UI는 콘텐츠 형식을 시각적으로 구성하고 친숙한 방식으로 나열하도록 해주고, 목록에서의 데이터 정렬 및 그룹화, 그리고 그룹 머리글으 사용하도록 해줍니다.  콘텐츠 유형에 대한 자세한 내용은 [Content Types](http://go.microsoft.com/fwlink/?LinkId=224997) 를 참조하십시오.  목록에 대한 자세한 내용은 [리스트 양식](http://go.microsoft.com/fwlink/?LinkId=224998) 및 [리스트 뷰](http://go.microsoft.com/fwlink/?LinkId=224999) 를 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[연습: SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)|사용자 지정 콘텐츠 형식에 사용되는 사이트 열을 만드는 방법을 보여 줍니다.  콘텐츠 형식은 이제 사용자 지정 목록에서 사용 됩니다.|  
  
## 참고 항목  
 [SharePoint 2010 개발 시작](http://go.microsoft.com/fwlink/?LinkId=225000)  
  
  