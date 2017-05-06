---
title: "방법: SharePoint 솔루션 패키지 사용자 지정"
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
  - "VS.SharePointTools.RAD.PackageDesignerAdvanced"
  - "VS.SharePointTools.RAD.PackageDesigner.Manifest"
  - "VS.SharePointTools.RAD.PackageDesignerProperties"
  - "VS.SharePointTools.RAD.PackageDesigner.SwitchView"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 패키지"
ms.assetid: fd365f8c-8a80-4ce8-8e28-c0eb609f12f3
caps.latest.revision: 20
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 19
---
# 방법: SharePoint 솔루션 패키지 사용자 지정
  패키지 디자이너를 사용하여 패키지\(.wsp\)를 만들고 사용자 지정할 수 있습니다.  예를 들어 SharePoint 프로젝트 항목과 기능을 추가하고, 솔루션을 배포할 때 웹 서버를 다시 설정할지 여부를 지정하고, 배포 서버 종류를 설정할 수 있습니다.  
  
## 패키지 디자이너 열기  
  
#### 패키지 디자이너를 열려면  
  
-   **솔루션 탐색기** 에서 **패키지** 를 더블클릭 하거나 또는 **패키지** 의 바로가기 메뉴에서 **뷰 디자이너** 를 선택합니다.  
  
## 패키징된 매니페스트 파일 보기  
 패키지 디자이너를 사용하여 패키징된 매니페스트 파일을 수정하고 생성할 수 있습니다.  그런 다음 Visual Studio에서 이 파일의 XML 코드를 볼 수 있습니다.  
  
#### XML 소스 파일을 보려면  
  
1.  **패키지 디자이너** 에서 **매니페스트** 를 선택합니다.  
  
#### 솔루션 탐색기를 사용하여 패키징된 매니페스트 파일을 보려면  
  
1.  **솔루션 탐색기**에서 **모든 파일 표시** 를 선택합니다.  
  
2.  Package, Package.package를 확장한 다음 Package.Template.xml 파일을 엽니다.  
  
    > [!NOTE]  
    >  패키지 템플릿에 대한 매니페스트 XML 파일을 열 때, 파일은 자동으로 유효성이 검사되고, 오류 목록 창에 표시되는 경고를 무시할 수 있습니다.  
  
## 매니페스트 템플릿 변경  
 Visual Studio XML 편집기나 매니페스트 템플릿 창에서 패키징된 매니페스트 파일의 XML 코드를 변경할 수 있습니다.  XML 코드의 모든 변경 내용이 패키지에 대해 패키징된 매니페스트 파일에 병합됩니다.  
  
#### XML 편집기를 사용하여 매니페스트 템플릿을 변경하려면  
  
1.  **패키지 디자이너** 의 **매니페스트** 탭에서 **편집 옵션** 노드를 확장한 다음, **XML 편집기에서 열기** 링크를 선택합니다.  
  
     XML 변경 내용이 패키징된 매니페스트 파일에 병합됩니다.  
  
#### \[매니페스트 템플릿\] 창을 사용하여 매니페스트 템플릿을 변경하려면  
  
1.  **패키지 디자이너** 의 **매니페스트** 탭에서 **편집 옵션** 노드를 확장한 다음, 매니페스트 템플릿 창에 표시되는 XML을 변경합니다.  
  
     XML 변경 내용이 **패키지 매니페스트 미리 보기** 창에 표시됩니다.  
  
## 패키징된 매니페스트 파일 덮어쓰기  
 패키지 디자이너를 사용하지 않도록 설정하고 manifest.xml 파일을 수동으로 만들 수 있습니다.  이 절차를 처음으로 수행하는 경우 패키지 디자이너의 현재 설정이 패키지 템플릿 XML 파일에 저장됩니다.  그런 다음 XML 코드를 수정하거나 덮어쓸 수 있습니다.  
  
> [!NOTE]  
>  패키지 디자이너를 사용할 수 없을 때 XML 파일에 SharePoint 프로젝트 항목과 기능을 추가하거나 제거하면 이러한 프로젝트 항목과 기능이 패키징되지 않습니다.  
  
#### 디자이너를 사용하지 않도록 설정하여 패키징된 매니페스트 파일을 덮어쓰려면  
  
1.  **패키지 디자이너** 에서 **매니페스트** 탭을 선택합니다.  
  
2.  .  
  
3.  **편집 옵션** 노드를 확장하고 **생성된 XML 덮어쓰기 및 XML 편집기에서 매니페스트를 편집** 링크를 선택한 다음 **예** 버튼을 선택합니다.  
  
     템플릿이 현재 패키징된 매니페스트 파일로 업데이트됩니다.  
  
## 패키지 디자이너 사용  
 패키지 디자이너를 다시 사용하도록 설정하여 manifest.xml 파일을 사용자 지정할 수 있습니다.  
  
#### 디자이너를 다시 사용하도록 설정하려면  
  
1.  **패키지 디자이너** 에서, **매니페스트 편집 내용을 버리고 디자이너를 다시 사용** 링크를 선택한 다음 **예** 버튼을 선택합니다.  
  
     템플릿이 원래 텍스트로 새로 고쳐지고 XML 변경 내용은 모두 손실됩니다.  
  
## 참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  