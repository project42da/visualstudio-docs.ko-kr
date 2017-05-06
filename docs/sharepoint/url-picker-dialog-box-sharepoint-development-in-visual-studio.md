---
title: "URL 선택기 대화 상자(Visual Studio에서 SharePoint 개발)"
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
  - "VS.SharePointTools.VWD.URLPicker"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 디자이너"
  - "Visual Studio에서 SharePoint 개발, URL 선택기"
ms.assetid: 33f8f521-e1f8-4242-a580-8a4bd9cb5ddc
caps.latest.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# URL 선택기 대화 상자(Visual Studio에서 SharePoint 개발)
  URL 선택기 대화 상자에서, 프로젝트에 있거나 SharePoint를 실행하는 로컬 서버에 있는 마스터 페이지 파일 또는 이미지 파일 같은 파일을 선택할 수 있습니다.  
  
 속성 설정을 위해 파일을 선택할 수 있는 옵션이 있는 경우에 이 대화 상자가 표시됩니다.  이 대화 상자는 **속성** 창의 여러 속성 옆에 있는 줄임표 단추\(![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.png "ASP.NET 모바일 디자이너 줄임표")\)를 선택하여 열 수 있습니다.  줄임표 단추는 디자이너의 **소스** 뷰에서 특정 특성에 값을 할당하면 IntelliSense 프롬프트로 나타나기도 합니다.  
  
## UI 요소 목록  
 **프로젝트 폴더**  
 프로젝트 또는 SharePoint를 실행하는 로컬 서버에 정의되어 있는 폴더 목록을 표시합니다.  하위 폴더를 표시하려면 확장 단추를 선택합니다.  
  
 **프로젝트** 노드를 확장해서 프로젝트의 파일을 선택합니다.  대화 상자에서 선택 가능한 파일로 나타나려면 프로젝트의 파일이 다음 조건을 충족해야 합니다.  
  
-   파일은 매핑된 폴더에 포함되어야 합니다.  
  
-   파일은 솔루션 패키지에 추가되어야 합니다.  
  
-   파일은 다른 프로젝트에 있을 수 없습니다.  
  
 이러한 조건을 충족하지 못하는 파일을 참조하려면 해당 파일의 경로를 직접 입력해야 합니다.  
  
 **서버** 노드를 확장하여 SharePoint를 실행하는 로컬 서버에 있는 파일을 선택합니다.  대화 상자에서 선택 가능한 파일로 나타나려면 파일이 다음 조건을 충족해야 합니다.  
  
-   파일은 매핑된 폴더, 즉 **Images**, **Layouts** 또는 **ControlTemplates** 중 한 폴더에 있어야 합니다.  
  
-   파일은 SharePoint 콘텐츠 데이터베이스에 있을 수 없습니다.  
  
 이러한 조건을 충족하지 못하는 파일을 참조하려면 해당 파일의 경로를 직접 입력해야 합니다.  
  
 **폴더 내용**  
 선택한 폴더에 있는 파일 목록을 표시합니다.  파일을 선택하고 **OK** 버튼을 선택하여 대화 상자를 닫고 호출한 프로세스에 선택 항목을 전송합니다.  
  
 **파일 형식**  
 수행하고 있는 작업에 적합한 파일 목록에서 선택할 수 있습니다.  
  
## 참고 항목  
 [SharePoint를 위한 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)   
 [Visual Studio Web Development Content Map](http://msdn.microsoft.com/ko-kr/9c31f93b-c8fb-4599-9b14-6194ec8c7539)  
  
  