---
title: "방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가"
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
  - "VS.SharePointTools.BDC.ImportDialog"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "BDC[Visual Studio에서 SharePoint 개발], 모델 가져오기"
  - "BDC[Visual Studio에서 SharePoint 개발], 모델 제거"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 모델 가져오기"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 모델 재사용"
ms.assetid: e843738a-f936-4dcd-be35-249407573b74
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# 방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가
  모델 파일 \(.bdcm\) 을 SharePoint 팜 프로젝트에 추가 하기 위해 Visual Studio를 사용하여 비지니스 데이터 연결 \(BDC\) 모델을 사용자 지정, 패키징 및 재 배포할 수 있습니다.  자세한 내용은 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)을 참조하십시오.  
  
### SharePoint 프로젝트에 BDC 모델 파일을 추가하려면  
  
1.  **솔루션 탐색기** 에서 SharePoint 프로젝트의 폴더를 선택 합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
3.  **기존 항목 추가** 대화 상자에서 프로젝트에 추가할 모델 정의 파일의 위치로 이동하여 파일을 선택한 다음 **추가** 버튼을 선택합니다.  
  
     *.NET 어셈블리 형식의 LOB\(기간 업무\) 시스템* 을 정의하지 않는 모델인 경우, **.NET 어셈블리 LobSystem 추가** 대화 상자가 열립니다.  
  
4.  대화 상자가 나타나면 다음 단계 중 하나를 수행 합니다.  
  
    -   사용자 지정 코드를 작성하고 디자이너를 사용하여 가져온 모델에 대한 메타 데이터를 정의하고자 할 경우, **예** 버튼을 선택하고 시스템의 이름을 지정한 다음 **확인** 버튼을 선택합니다.  
  
    -   그렇지 않으면, **아니오** 버튼을 선택한 후 **확인** 단추를 선택합니다.  
  
     **비즈니스 데이터 연결 모델** 항목이 프로젝트에 추가됩니다.  
  
## 참고 항목  
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [방법: BDC 모델 만들기](../sharepoint/how-to-create-a-bdc-model.md)   
 [방법: 리소스 파일을 사용하여 지역화된 이름, 속성 및 사용 권한 지정](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [방법: BDC 기능에 사용자 지정 어셈블리 포함](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  