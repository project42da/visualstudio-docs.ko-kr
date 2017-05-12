---
title: "방법: BDC 모델 만들기"
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
ms.assetid: e8b888d4-a531-4d13-9ebf-efbbd33eebc6
caps.latest.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# 방법: BDC 모델 만들기
  해당 종류의 항목에 대한 템플릿을 사용한 후 SharePoint 프로젝트에 모델을 추가하여 BDC\(비즈니스 데이터 연결\) 모델을 만들 수 있습니다.  자세한 내용은 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)을 참조하십시오.  모델을 디자인하는 방법에 대한 자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
### BDC 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
    > [!NOTE]  
    >  IDE가 Visual Basic 개발 설정을 사용하도록 설정된 경우 **파일**, **새 프로젝트**를 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
2.  **Visual Basic** 또는 **Visual C\#**에서 **SharePoint Solutions**, **Office\/SharePoint**를 선택합니다.  
  
3.  **템플릿** 창에서 **SharePoint 2013 – 빈 프로젝트** 항목을 선택한 다음 **확인** 단추를 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 열립니다.  
  
4.  **사이트 지정 및 디버깅에 대한 보안 수준** 페이지에서 로컬 컴퓨터의 SharePoint 사이트 URL을 지정하고 **팜 솔루션으로 배포** 옵션 단추를 선택한 다음 **마침** 단추를 선택합니다.  
  
     지정한 SharePoint 사이트에서 모델을 테스트합니다.  
  
    > [!IMPORTANT]  
    >  BDC 모델은 팜 솔루션만을 지원하므로 팜 솔루션으로 프로젝트를 배포해야 합니다.  
  
     빈 SharePoint 프로젝트가 만들어집니다.  
  
5.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
6.  **새 항목 추가** 대화 상자에서 **Office\/SharePoint** 노드를 선택합니다.  
  
7.  SharePoint 템플릿 목록에서 **비즈니스 데이터 연결 모델\(팜 솔루션에만 해당\)**을 선택합니다.  
  
8.  **이름** 상자에 BDC 모델의 이름을 지정한 다음 **추가** 단추를 선택합니다.  
  
     **비즈니스 데이터 연결 모델** 항목이 프로젝트에 추가됩니다.  기본적으로 BDC 디자이너에 모델이 표시됩니다.  자세한 내용은 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)을 참조하십시오.  
  
## 참고 항목  
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)   
 [방법: 리소스 파일을 사용하여 지역화된 이름, 속성 및 사용 권한 지정](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [방법: BDC 기능에 사용자 지정 어셈블리 포함](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  