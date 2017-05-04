---
title: "방법: 패키징 탐색기를 사용하여 패키지에 기능과 항목 추가 및 제거 | Microsoft Docs"
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
  - "VS.SharePointTools.RAD.PackagingExplorer"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 패키지"
ms.assetid: 549d5848-f0c9-42c6-b7f5-bc1e626a30e6
caps.latest.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# 방법: 패키징 탐색기를 사용하여 패키지에 기능과 항목 추가 및 제거
  SharePoint 항목과 기능을 배포하도록 패키지를 구성하려면 패키징 탐색기를 사용할 수 있습니다.  .wsp 파일 내에서 SharePoint 프로젝트 항목과 기능을 조정할 수 있습니다.  
  
 또는 패키징 디자이너를 통해 기능을 보고 다시 정렬하여 활성화 순서를 변경할 수 있습니다.  자세한 내용은 [방법: 패키지 디자이너를 사용하여 패키지에 기능과 항목 추가 및 제거](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)을 참조하십시오.  
  
## 패키징 탐색기 열기  
 Visual Studio 솔루션에 SharePoint 프로젝트가 하나 이상 있는 경우 다음 절차를 사용하여 패키징 탐색기를 열 수 있습니다.  또는 기능이나 패키지 디자이너를 볼 때 패키징 탐색기가 자동으로 열립니다.  모든 기능과 패키지 디자이너를 닫으면 패키징 탐색기도 닫힙니다.  
  
#### 패키징 탐색기를 열려면  
  
1.  메뉴 모음에서 **보기**, **다른 창**, **패키징 탐색기**를 차례로 선택합니다.  
  
     **패키징 탐색기** 가 **도구 상자**에 나타납니다.  
  
## 패키지에 기능 추가  
 패키징 탐색기를 사용하여 패키지에 새 기능과 기존 기능을 추가할 수 있습니다.  
  
#### SharePoint 기능을 추가하려면  
  
1.  **패키징 탐색기** 를 열고, 프로젝트에 대한 바로 가기 메뉴를 연 다음, **기능 추가** 를 선택합니다.  
  
#### 기존 SharePoint 기능을 이동하려면  
  
1.  **패키징 탐색기** 를 연 다음, 다음 단계 중 하나를 수행합니다.  
  
    -   **기능**을 한 프로젝트에서 다른 프로젝트로 끌어서 놓습니다.  
  
    -   기능에 대한 바로 가기 메뉴에서 **잘라내기** 를 선택하고, 프로젝트에 대한 바로가기 메뉴에서 이동할 기능을 선택한 다음, **붙여넣기** 를 선택합니다.  
  
    > [!NOTE]  
    >  솔루션에 SharePoint 프로젝트가 여러 개 있는 경우 이 방법을 사용합니다.  
  
## 기능 또는 패키지 유효성 검사  
 파일의 유효성을 검사하여 SharePoint 기능과 패키지의 잠재적 문제를 식별할 수 있습니다.  출력 창과 오류 목록 창에 경고 및 오류가 표시됩니다.  
  
#### SharePoint 기능이나 패키지의 유효성을 검사하려면  
  
1.  **패키징 탐색기**를 엽니다.  
  
2.  기능 또는 패키지에 대한 바로 가기 메뉴를 열고 **유효성 검사** 를 선택합니다.  
  
## 참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  