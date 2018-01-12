---
title: "비즈니스 데이터 연결 모델 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], model
- BDC [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], creating a model
- SharePoint development in Visual Studio, Business Data Connectivity service
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: ab375e95d1deccb614a7908ec7608ffcb0da2e9c
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="creating-a-business-data-connectivity-model"></a>비즈니스 데이터 연결 모델 만들기
  BDC 비즈니스 데이터 연결 () 모델을 만들거나 Visual Studio를 사용 하 여 기존 BDC 모델을 사용자 지정할 수 있습니다. 각 SharePoint 프로젝트에 모델 하나만 포함할 수 있습니다. 자세한 내용은 참조 [를 SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)합니다.  
  
## <a name="creating-a-new-model"></a>새 모델 만들기  
 새 모델을 만들려면 만들기는 **비즈니스 데이터 연결 모델** 프로젝트 또는 추가 **비즈니스 데이터 연결 모델** 항목의 **빈 SharePoint 프로젝트**합니다.  
  
> [!NOTE]  
>  있어야 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] 컴퓨터에 설치 합니다.  
  
 Visual Studio 프로젝트에 폴더를 추가 합니다. 이 폴더에 대해 지정한 이름을 가진는 **비즈니스 데이터 연결 모델** 항목에 **새 항목 추가** 대화 상자. 새 만들면 **비즈니스 데이터 연결 모델** 프로젝트를 Visual Studio에는 폴더 이름 **BdcModel1**합니다.  
  
 Visual Studio를 새 폴더로 다음 파일을 추가합니다.  
  
|파일|설명|  
|----------|-----------------|  
|모델 정의 파일|엔터티, 메서드, 업무 (LOB) 시스템 개체 및 모델을 설명 하는 다른 메타 데이터를 정의 하는 XML을 포함 합니다.<br /><br /> BDC 디자이너를 사용 하 여이 파일의 메타 데이터를 수정 **BDC 탐색기**, **BDC 메서드 세부 정보** 창 및 **속성** 창.|  
|엔터티 서비스 코드 파일|검색, 업데이트 및 기본 엔터티 인스턴스를 삭제 하는 메서드를 포함 합니다.|  
  
 엔터티의 속성을 정의 하려면 엔터티 코드 파일을 편집 합니다. 자세한 내용은 참조 [하는 방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)합니다.  
  
 검색, 업데이트 및 엔터티 인스턴스 삭제를 엔터티 서비스 코드 파일에 코드를 추가 합니다. 자세한 내용은 참조 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
 Visual Studio 프로젝트를 컴파일할 때 어셈블리를 만듭니다. 프로젝트 어셈블리에 코드를 추가 하는 프로젝트에 다른 항목을 추가 하지 않으면 확인 (예: 한 **순차 워크플로** 항목 또는 **웹 파트** 항목). 솔루션 패키지는 전역 어셈블리 캐시에 어셈블리를 복사 하지 않으므로 솔루션을 배포할 때에 해당 항목에 대 한 코드 실행 되지 않습니다.  솔루션 패키지만 sharepoint에서 BDC 데이터베이스에 어셈블리를 배포 합니다.  
  
> [!NOTE]  
>  Visual Studio 프로젝트를 디버깅할 때 로컬 컴퓨터에 두 위치 모두에 어셈블리를 복사 합니다.  
  
## <a name="adding-an-existing-model"></a>기존 모델 추가  
 SharePoint Designer와 같은 다른 도구를 사용 하 여 만든 모델을 가져올 수 있습니다. 다음과 같은 경우 프로젝트에 기존 모델을 가져올 수 있습니다.  
  
-   SharePoint 서버 팜에 이미 배포 된 모델을 사용자 지정 합니다.  
  
-   패키지 하 고 SharePoint 서버 팜에 여러 기존 모델을 배포 합니다.  
  
 두 경우 모두에서 가져올 모델에 정의 된 LOB 시스템 영향을 받지 않는 하 고 예상 대로 작동 하도록 계속 됩니다. 기존 모델을 SharePoint 프로젝트를 추가 하려면 Visual Studio를 사용 하 여 **기존 항목 추가** 대화 상자. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)합니다.  
  
 옵션을 선택 하 여 가져온된 모델에 형식이.NET Framework 어셈블리의 LOB 시스템을 추가할 수 있습니다는 **추가.NET 어셈블리 LobSystem**합니다. 이 사용자 지정 코드를 작성 및 디자이너를 사용 하 여 가져온된 모델에 대 한 메타 데이터를 정의할 수 있습니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[방법: BDC 모델 만들기](../sharepoint/how-to-create-a-bdc-model.md)|새 BDC 모델을 만드는 방법을 보여 줍니다.|  
|[방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)|SharePoint 프로젝트에 기존 모델을 가져오는 방법을 보여 줍니다.|  
|[방법: 리소스 파일을 사용하여 지역화된 이름, 속성 및 사용 권한 지정](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)|웹 파트 또는 웹 페이지에서 모델을 사용할 때 모델 메타 데이터와 병합 될 문자열을 제공 하는 방법에 설명 합니다.|  
|[방법: BDC 기능에 사용자 지정 어셈블리 포함](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)|기능에 있는 사용자 지정 어셈블리를 포함 하는 방법을 보여 줍니다.|  
  
  