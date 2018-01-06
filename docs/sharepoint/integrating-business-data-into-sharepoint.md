---
title: "SharePoint에 비즈니스 데이터 통합 | Microsoft Docs"
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
- Business Data Connectivity service [SharePoint development in Visual Studio], business data
- BDC [SharePoint development in Visual Studio], aggregating data
- BDC [SharePoint development in Visual Studio], business data
- Business Data Connectivity service [SharePoint development in Visual Studio], aggregating data
- BDC [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], data
- BDC [SharePoint development in Visual Studio], data
ms.assetid: e092e3d6-2c5f-4060-ae86-d37db8967559
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4cacdbb314130fa45b5aa3820abbbffbcbc6c0bf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="integrating-business-data-into-sharepoint"></a>SharePoint에 비즈니스 데이터 통합
  SharePoint에 비즈니스 데이터를 통합할 수 있습니다. 비즈니스 데이터와 같은 백 엔드 서버 응용 프로그램에서 가져올 수 있습니다 [!INCLUDE[TLA#tla_sqlsvr](../sharepoint/includes/tlasharptla-sqlsvr-md.md)], Siebel 및 SAP, 또는 웹 서비스입니다. 사용자 수 보기, 추가, 업데이트 또는 외부 목록 또는 SharePoint에 비즈니스 데이터 웹 파트를 사용 하 여 비즈니스 데이터를 삭제 합니다.  사용자가 Microsoft Outlook과 같은 Microsoft Office 응용 프로그램에서 오프 라인으로이 데이터에 액세스할 수도 있습니다. 자세한 내용은 참조 [위치 수 하면 외부 데이터 표시](http://go.microsoft.com/fwlink/?LinkId=169295)합니다.  
  
 SharePoint에 데이터를 통합 하는 비즈니스 데이터 연결 (BDC) 서비스에 대 한 모델을 만듭니다. BDC 서비스는 비즈니스 응용 프로그램의 데이터에 대 한 정보를 저장 하는 SharePoint에서 응용 프로그램. 자세한 내용은 참조 [BDC 비즈니스 데이터 연결 () 서비스](http://go.microsoft.com/fwlink/?LinkID=169276)합니다.  
  
## <a name="models-in-visual-studio"></a>Visual Studio의 모델  
 Visual Studio에서 모델을 사용 하 여 백 엔드 데이터 원본에서 데이터 검색 및 업데이트 하는 사용자 지정 코드를 작성할 수 있습니다. 또한 여러 데이터 원본에서 데이터를 집계 수 있습니다. 예를 들어 데이터를 포함 하는 고객 목록을 표시할 수 있습니다는 [!INCLUDE[ssNoVersion](../sharepoint/includes/ssnoversion-md.md)] 데이터베이스 및 웹 서비스입니다.  
  
 이미 SharePoint에 배포 된 모델을 가져올 수도 있습니다. 모델을 가져온 후에 사용자 지정 코드를 추가할 수도 있고 방금 Visual Studio를 사용 하 여 패키징 및 모델에 여러 SharePoint 서버 팜을 배포 하 수 있습니다. 자세한 내용은 참조 [비즈니스 데이터 연결 모델을 만드는](../sharepoint/creating-a-business-data-connectivity-model.md)합니다.  
  
## <a name="designing-a-model-in-visual-studio"></a>Visual Studio에서 모델 디자인  
 디자이너 및 다양 한 도구 창을 사용 하 여 모델을 디자인할 수 있습니다. 모델을 디자인할 때 Visual Studio는 모델 XML을 생성 합니다. 자세한 내용은 참조 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)합니다.  
  
 모델은 엔터티 및 메서드를 포함 합니다.  
  
### <a name="entities"></a>엔터티  
 엔터티 필드의 컬렉션을 설명 합니다. 예를 들어 엔터티는 데이터베이스의 테이블을 나타낼 수 있습니다. 엔터티 sharepoint에서 외부 콘텐츠 형식으로 나타납니다. 외부 콘텐츠 형식에 대 한 자세한 내용은 참조 하십시오. [외부 콘텐츠 유형 이란?](http://go.microsoft.com/fwlink/?LinkId=169293)  
  
### <a name="methods"></a>메서드  
 메서드를 사용 하면 엔터티의 필드에 작업을 수행 하는 외부 콘텐츠 형식의 소비자가 있습니다. Updater 메서드 주소를 변경 하려면 사용자가 될 수 있습니다 및 고객의 생년월일 되는 예를 들어 여기서 `Address` 및 `BirthDate` 는의 필드는 `Customer` 엔터티.  
  
 Visual Studio는 모델의 각 엔터티에 대 한 서비스 코드 파일을 생성합니다. 모델에는 메서드를 추가 하면 Visual Studio 서비스 코드 파일에 해당 하는 메서드를 생성 합니다. 적절 한 작업을 수행 하려면 각 메서드에 코드를 추가 합니다. 예를 들어 모델에 Creator 메서드를 추가 하는 경우 Visual Studio 서비스 코드 파일에서 Creator 메서드를 생성 합니다. 이 메서드는 BDC 서비스에서 사용자가 클릭는 **새 항목** 모델을 기반으로 하는 목록에서 단추입니다. 따라서 데이터 원본에 새 데이터를 추가 하는 작성자 메서드에 코드를 추가 합니다. 자세한 내용은 참조 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)|어떻게 새 모델을 만들거나 가져오는 SharePoint에서 내보내기 하는 모델을 보여 줍니다.|  
|[비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)|Visual Studio 디자인 도구를 사용 하 여 모델의 요소를 디자인 하는 방법에 설명 합니다.|  
|[SharePoint Designer를 사용 하 여 vs 하는 경우. BCS를 사용 하 여 visual Studio를 만들 때 솔루션](http://go.microsoft.com/fwlink/?LinkID=183448)|Visual Studio를 사용 하거나 SharePoint Designer를 사용 하 여 BDC에 대 한 모델을 만들 것인지 결정 하는 데 도움이 됩니다.|  
  
  