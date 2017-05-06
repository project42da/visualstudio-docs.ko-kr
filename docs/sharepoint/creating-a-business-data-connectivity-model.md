---
title: "비즈니스 데이터 연결 모델 만들기"
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
  - "BDC[Visual Studio에서 SharePoint 개발], 모델 만들기"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 모델 만들기"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 모델"
  - "Visual Studio에서 SharePoint 개발, 비즈니스 데이터 연결 서비스"
ms.assetid: 19fd12d0-a51a-4da4-98ac-918542e84507
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 23
---
# 비즈니스 데이터 연결 모델 만들기
  Visual Studio를 사용하여 BDC\(비즈니스 데이터 연결\) 모델을 만들거나 기존 BDC 모델을 사용자 지정할 수 있습니다.  각 SharePoint 프로젝트에는 모델이 하나만 포함될 수 있습니다.  자세한 내용은 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)을 참조하십시오.  
  
## 새 모델 만들기  
 새 모델을 만들려면 **비즈니스 데이터 연결 모델** 프로젝트를 만들거나 **비즈니스 데이터 연결 모델** 항목을 **빈 SharePoint 프로젝트**에 추가합니다.  
  
> [!NOTE]  
>  컴퓨터에 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]이 설치되어 있어야 합니다.  
  
 프로젝트에 폴더가 추가됩니다.  **새 항목 추가** 대화 상자에서 **비즈니스 데이터 연결 모델** 항목에 지정한 이름이 이 폴더의 이름이 됩니다.  새 **비즈니스 데이터 연결 모델** 프로젝트를 만들면 폴더 이름으로 **BdcModel1**이 지정됩니다.  
  
 새 폴더에 다음 파일이 추가됩니다.  
  
|파일|설명|  
|--------|--------|  
|모델 정의 파일|엔터티, 메서드, 기간 업무\(LOB\) 시스템 개체 및 모델에 대해 설명하는 기타 메타데이터를 정의하는 XML이 들어 있습니다.<br /><br /> BDC 디자이너, **BDC 탐색기**, **BDC 메서드 세부 정보** 창 및 **속성** 창에서 이 파일의 메타데이터를 수정할 수 있습니다.|  
|엔터티 서비스 코드 파일|기본 엔터티의 인스턴스를 검색, 업데이트 및 삭제하는 메서드가 들어 있습니다.|  
  
 엔터티의 속성을 정의하려면 엔터티 코드 파일을 편집합니다.  자세한 내용은 [방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)을 참조하십시오.  
  
 엔터티의 인스턴스를 검색, 업데이트 및 삭제하려면 엔터티 서비스 코드 파일에 코드를 추가합니다.  자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
 프로젝트를 컴파일하면 어셈블리가 만들어집니다.  프로젝트 어셈블리에 코드를 추가하는 다른 항목\(예: **순차 워크플로** 항목 또는 **웹 파트** 항목\)을 프로젝트에 추가하지 않아야 합니다.  솔루션 패키지에서 어셈블리를 전역 어셈블리 캐시에 복사하지 않으므로 솔루션을 배포할 때 이러한 항목의 코드는 실행되지 않습니다.  솔루션 패키지는 SharePoint의 BDC 데이터베이스에만 어셈블리를 배포합니다.  
  
> [!NOTE]  
>  프로젝트를 디버깅할 때는 로컬 컴퓨터의 두 위치에 모두 어셈블리가 복사됩니다.  
  
## 기존 모델 추가  
 SharePoint Designer와 같은 다른 도구를 사용하여 만든 모델을 가져올 수 있습니다.  다음과 같은 경우 프로젝트에 기존 모델을 가져오면 좋습니다.  
  
-   SharePoint 서버 팜에 이미 배포된 모델을 사용자 지정하려는 경우  
  
-   기존 모델을 패키지하여 여러 SharePoint 서버 팜에 배포하려는 경우  
  
 이 경우 가져올 모델에 정의된 LOB 시스템은 영향을 받지 않으며 예상대로 작동합니다.  SharePoint 프로젝트에 기존 모델을 추가하려면 Visual Studio의 **기존 항목 추가** 대화 상자를 사용합니다.  자세한 내용은 [방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)을 참조하십시오.  
  
 **.NET 어셈블리 LobSystem 추가**에서 옵션을 선택하면 가져온 모델에 .NET Framework 어셈블리 형식의 LOB 시스템을 추가할 수 있습니다.  이렇게 하면 사용자 지정 코드를 작성하고 디자이너를 사용하여 가져온 모델의 메타데이터를 정의할 수 있습니다.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[방법: BDC 모델 만들기](../sharepoint/how-to-create-a-bdc-model.md)|새 BDC 모델을 만드는 방법을 보여 줍니다.|  
|[방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)|SharePoint 프로젝트에 기존 모델을 가져오는 방법을 보여 줍니다.|  
|[방법: 리소스 파일을 사용하여 지역화된 이름, 속성 및 사용 권한 지정](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)|웹 파트나 웹 페이지에서 모델을 사용할 때 모델 메타데이터와 병합될 문자열을 제공하는 방법을 설명합니다.|  
|[방법: BDC 기능에 사용자 지정 어셈블리 포함](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)|기능에 사용자 지정 어셈블리를 포함하는 방법을 보여 줍니다.|  
  
  