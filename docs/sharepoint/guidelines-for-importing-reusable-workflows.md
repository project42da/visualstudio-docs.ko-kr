---
title: "다시 사용 가능한 워크플로를 가져오기 위한 지침 | Microsoft Docs"
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
helpviewer_keywords: 
  - "항목 가져오기[Visual Studio에서 SharePoint 개발]"
  - "재사용 가능한 워크플로[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 항목 가져오기"
  - "Visual Studio에서 SharePoint 개발, 재사용 가능한 워크플로"
ms.assetid: 851043dd-ecbe-49ab-b5b7-5ea7b699df12
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# 다시 사용 가능한 워크플로를 가져오기 위한 지침
  SharePoint Designer에서 생성된 다시 사용할 수 있는 워크플로를 가져오려면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 다시 사용할 수 있는 SharePoint 2010 워크플로 프로젝트 가져오기 템플릿을 사용합니다.  이 템플릿은 *선언적* *워크플로*\([!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 전용\)를 가져와 *코드 워크플로*로 변환합니다. 이 워크플로는 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)] 코드를 사용하여 개선할 수 있습니다.  [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [연습: Visual Studio에 SharePoint Designer의 다시 사용 가능한 워크플로 가져오기](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md).  
  
 그러나, 다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기 템플릿은 팜 솔루션만 가져올 수 있습니다.  워크플로를 샌드박스가 적용된 솔루션으로 배포하려면 SharePoint 2010 솔루션 패키지 가져오기 템플릿을 사용하여 워크플로를 가져옵니다.  그러나 이렇게 하면 워크플로를 코드 워크플로로 변환할 수 없고 코드 워크플로로 수정할 수도 없습니다.  
  
## 다시 사용할 수 있는 워크플로 가져오기 템플릿을 사용하여 다시 사용할 수 있는 워크플로 가져오기  
 다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기 템플릿을 사용하여 다시 사용할 수 있는 워크플로를 가져오면 이 솔루션을 다른 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 솔루션과 같이 실행하거나 변경할 수 있지만 일부 항목은 수동으로 수정해야 합니다.  
  
### 작업 양식 가져오기  
 다시 사용할 수 있는 SharePoint 2010 워크플로 프로젝트 가져오기 템플릿은 모든 시작 양식과 연결 양식을 가져오지만 코드 워크플로 스키마에서 하나의 작업 양식만 허용하기 때문에 작업 양식은 하나만 가져옵니다.  원본 워크플로 솔루션의 다른 작업 양식은 **솔루션 탐색기**에서 **Other Imported Files** 폴더에 배치됩니다.  
  
## SharePoint 2010 솔루션 패키지 가져오기 템플릿을 사용하여 다시 사용할 수 있는 워크플로 가져오기  
 SharePoint 2010 솔루션 패키지 가져오기 템플릿을 사용하여 다시 사용할 수 있는 워크플로를 가져오는 경우 다음 문제점을 고려해야 합니다.  
  
-   워크플로를 가져온 직후 워크플로를 배포하고 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에서 F5 키를 눌러 실행할 수 있습니다.  그러나 가져온 솔루션의 워크플로를 변경한 경우에는 워크플로를 배포하고 실행하기 전에 프로젝트의 요소를 수동으로 수정해야 할 수도 있습니다.  
  
-   워크플로가 선언적이므로 워크플로에 코드는 추가할 수 없습니다.  이 워크플로를 코드 워크플로로 변환하려면 다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기 템플릿을 사용하여 해당 워크플로를 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]로 가져와야 합니다.  
  
-   디자인 뷰에서 워크플로 디자이너 파일\(.xoml\)을 편집할 수는 있지만 워크플로 디자이너가 허위 오류를 표시하기 때문에 이 파일을 소스 뷰에서 편집하는 것이 좋습니다.  
  
-   워크플로에서 디버깅하는 경우 선언적 콘텐츠에 대해서는 디버깅되지 않습니다.  [!INCLUDE[wfd2](../sharepoint/includes/wfd2-md.md)]에 설정된 중단점은 적중되지 않습니다.  
  
## 전역적으로 다시 사용할 수 있는 워크플로 솔루션 가져오기  
 전역적으로 다시 사용할 수 있는 워크플로는 다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기 템플릿을 사용하여 가져올 수 없습니다.  전역적으로 다시 사용할 수 있는 워크플로를 가져오려면 해당 워크플로를 전역적으로 재사용할 수 없는 워크플로로 변환하거나 SharePoint 2010 솔루션 패키지 가져오기 템플릿을 사용해야 합니다.  
  
 워크플로를 변환하려면 SharePoint Designer에서 워크플로의 바로가기 메뉴를 열어 **복사본 저장**을 선택하여 전역적으로 다시 사용할 수 있는 워크플로의 복사본을 만듭니다.  그런 다음 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 다시 사용할 수 있는 SharePoint 2010 워크플로 가져오기 템플릿을 사용하여 재사용 가능한 새 워크플로를 가져옵니다.  
  
 전역적으로 다시 사용할 수 있는 워크플로를 변환 없이 그대로 가져오려면 SharePoint 2010 솔루션 패키지 가져오기 템플릿을 사용합니다.  이 방법을 사용하면 워크플로가 코드 워크플로로 변환되지 않고 선언적 워크플로로 유지됩니다.  
  
## 참고 항목  
 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [연습: Visual Studio에 SharePoint Designer의 다시 사용 가능한 워크플로 가져오기](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)  
  
  