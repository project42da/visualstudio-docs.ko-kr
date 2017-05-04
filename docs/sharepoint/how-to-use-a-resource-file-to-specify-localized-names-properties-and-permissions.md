---
title: "방법: 리소스 파일을 사용하여 지역화된 이름, 속성 및 사용 권한 지정 | Microsoft Docs"
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
  - "BDC[Visual Studio에서 SharePoint 개발], 문자열 지역화"
  - "BDC[Visual Studio에서 SharePoint 개발], 속성"
  - "BDC[Visual Studio에서 SharePoint 개발], 리소스 파일"
  - "BDC[Visual Studio에서 SharePoint 개발], 리소스 문자열"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 문자열 지역화"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 속성"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 리소스 파일"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 리소스 문자열"
ms.assetid: 72bb744d-818b-4e5a-9da2-295412025680
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# 방법: 리소스 파일을 사용하여 지역화된 이름, 속성 및 사용 권한 지정
  리소스 파일을 사용하여 지역화 된 이름을 제공하고, 속성을 정의하고, BDC 비즈니스 데이터 연결 \(BDC\) 모델에 정의된 개체에 사용 권한을 적용할 수 있습니다.  이 정보를 지정하려면 **비즈니스 데이터 연결 리소스** 항목을 **비즈니스 데이터 연결 모델** 항목이 포함된 프로젝트에 추가합니다.  그런 다음 리소스 파일의 XML을 편집하여 이름, 속성 및 사용 권한을 지정합니다.  
  
### SharePoint 프로젝트에 BDC 리소스 파일을 추가하려면  
  
1.  **솔루션 탐색기**에서 SharePoint 프로젝트의 폴더를 확장한 다음 BDC 모델이 들어 있는 폴더를 선택합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
3.  **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
4.  **새 항목 추가** 대화 상자에서 **비즈니스 데이터 연결 리소스** 항목을 선택합니다.  
  
5.  **이름** 상자에 리소스 파일의 이름을 지정한 다음 **추가** 버튼을 선택합니다.  
  
     확장명이 .bdcr인 리소스 파일이 프로젝트에 추가되고 편집을 위해 열립니다.  
  
6.  XML을 추가하여 BDC 모델을 적용할 지역화된 이름, 속성 및 권한을 정의합니다.  
  
     이러한 요소를 정의 하는 방법에 대한 자세한 내용은 [모델 및 리소스 파일](http://go.microsoft.com/fwlink/?LinkID=169283) 을 참조하십시오.  
  
## 참고 항목  
 [방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)   
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [방법: BDC 모델 만들기](../sharepoint/how-to-create-a-bdc-model.md)   
 [방법: BDC 기능에 사용자 지정 어셈블리 포함](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  