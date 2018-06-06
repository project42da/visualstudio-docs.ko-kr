---
title: '방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.BDC.ImportDialog
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], import a model
- Business Data Connectivity service [SharePoint development in Visual Studio], reuse a model
- BDC [SharePoint development in Visual Studio], import a model
- BDC [SharePoint development in Visual Studio], remove a model
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4ca7f4befcb75a48e5b03637c143edfdd81b428a
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767743"
---
# <a name="how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project"></a>방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가
  사용자 지정, 패키지 및 모델 파일을 추가 하려면 Visual Studio를 사용 하 여 비즈니스 데이터 BDC (연결) 모델을 다시 배포할 수 있습니다 (*.bdcm*)을 SharePoint 팜에 프로젝트. 자세한 내용은 참조 [비즈니스 데이터 연결 모델을 만드는](../sharepoint/creating-a-business-data-connectivity-model.md)합니다.  
  
### <a name="to-add-a-bdc-model-file-to-a-sharepoint-project"></a>BDC 모델 파일을 SharePoint 프로젝트에 추가 하려면  
  
1.  **솔루션 탐색기**을 SharePoint 프로젝트에 대 한 폴더를 선택 합니다.  
  
2.  메뉴 모음에서 **프로젝트** > **기존 항목 추가**합니다.  
  
3.  에 **기존 항목 추가** 대화 상자, 프로젝트에 추가할 파일을 선택한 다음 선택 하려는 모델 정의 파일의 위치로 이동 하 여 **추가** 단추입니다.  
  
     모델을 정의 하지 않은 경우는 *업무 (LOB) 형식의 시스템에.NET 어셈블리*, **추가.NET 어셈블리 LobSystem** 대화 상자가 열립니다.  
  
4.  대화 상자가 나타나면 다음 단계 중 하나를 수행 합니다.  
  
    -   디자이너를 사용 하 여 가져온된 모델에 대 한 메타 데이터 정의 선택 하 고 사용자 지정 코드를 작성 하려는 경우는 **예** 단추, 시스템에서 이름을 선택한 후는 **확인** 단추입니다.  
  
    -   그렇지 않은 경우, 선택는 **아니요** 단추를 선택한 후는 **확인** 단추입니다.  
  
     **비즈니스 데이터 연결 모델** 항목이 프로젝트에 추가 됩니다.  
  
## <a name="see-also"></a>참고자료
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [방법: BDC 모델 만들기](../sharepoint/how-to-create-a-bdc-model.md)   
 [방법: 리소스 파일을 사용 하 여 지역화 된 이름, 속성 및 사용 권한을 지정 합니다.](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [방법: BDC 기능에 사용자 지정 어셈블리 포함](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
 