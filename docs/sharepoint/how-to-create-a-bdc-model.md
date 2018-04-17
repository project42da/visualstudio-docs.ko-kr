---
title: '방법: BDC 모델 만들기 | Microsoft Docs'
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
- BDC [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], creating a model
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: aae6789d9961fa3cbf63ce073a33251465ee308a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-bdc-model"></a>방법: BDC 모델 만들기
  서식 파일을 사용 하 여 이러한 종류의 항목에 대 한 다음 모든 SharePoint 프로젝트에 모델을 추가 하 여 비즈니스 데이터 BDC (연결) 모델을 만들 수 있습니다. 자세한 내용은 참조 [비즈니스 데이터 연결 모델을 만드는](../sharepoint/creating-a-business-data-connectivity-model.md)합니다. 모델을 디자인 하는 방법에 대 한 자세한 내용은 참조 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
### <a name="to-create-a-bdc-project"></a>BDC 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
    > [!NOTE]  
    >  IDE가 Visual Basic 개발 설정을 사용 하도록 설정 되는 경우 선택 **파일**, **새 프로젝트**합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
2.  아래의 **Visual Basic** 또는 **Visual C#**, 선택 **Office/SharePoint**, **SharePoint 솔루션**합니다.  
  
3.  에 **템플릿** 창 선택는 **SharePoint 2013-빈 프로젝트** 항목을 선택한 다음 선택는 **확인** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 열립니다.  
  
4.  에 **디버깅에 대 한 사이트 및 보안 수준을 지정** 페이지, 로컬 컴퓨터에 SharePoint 사이트의 URL을 지정 하 고, 선택는 **팜 솔루션으로 배포** 옵션 단추를 선택한 후는 **마침** 단추입니다.  
  
     지정 된 SharePoint 사이트에 대 한 모델을 테스트 합니다.  
  
    > [!IMPORTANT]  
    >  BDC 모델은 팜 솔루션만 지원 하기 때문에 팜 솔루션으로 프로젝트를 배포 해야 합니다.  
  
     빈 SharePoint 프로젝트 생성 됩니다.  
  
5.  메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다.  
  
6.  에 **새 항목 추가** 대화 상자에서 선택 하는 **Office/SharePoint** 노드.  
  
7.  SharePoint 템플릿의 목록에서 선택 **비즈니스 데이터 연결 모델 (팜 솔루션에만 해당)**합니다.  
  
8.  에 **이름** 상자 BDC 모델에 대 한 이름을 지정 하 고 선택 합니다는 **추가** 단추입니다.  
  
     A **비즈니스 데이터 연결 모델** 항목이 프로젝트에 추가 됩니다. 기본적으로 모델 BDC 디자이너에 나타납니다. 자세한 내용은 참조 [비즈니스 데이터 연결 모델을 만드는](../sharepoint/creating-a-business-data-connectivity-model.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)   
 [방법: 리소스 파일을 사용 하 여 지역화 된 이름, 속성 및 사용 권한을 지정 합니다.](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [방법: BDC 기능에 사용자 지정 어셈블리 포함](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  