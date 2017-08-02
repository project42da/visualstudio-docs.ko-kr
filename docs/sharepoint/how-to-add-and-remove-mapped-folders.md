---
title: "방법: 매핑된 폴더 추가 및 제거"
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
  - "VS.SharePointTools.Project.MappedFolder"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "매핑된 폴더[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 매핑된 폴더"
ms.assetid: 115c8b00-7d4c-4fbe-b42c-e82dca944504
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# 방법: 매핑된 폴더 추가 및 제거
  SharePoint에서 자주 사용되는 Images, Layouts 등의 폴더는 파일 계층 구조에 깊이 포함되어 있습니다.  이러한 폴더에 보다 쉽게 액세스할 수 있도록 폴더를 SharePoint 프로젝트에 매핑할 수 있습니다.  매핑된 폴더는 SharePoint Server 설치의 실제 파일 위치에 해당하는 SharePoint 프로젝트의 폴더입니다.  
  
 SharePoint 응용 프로그램을 배포하면 매핑된 폴더 및 모든 하위 폴더의 내용이 솔루션 패키지\(.wsp\)를 통해 SharePoint 서버의 SharePoint 폴더 트리에서 지정한 위치에 복사됩니다.  이 위치는 매핑된 폴더로 설정된 **Deployment Location** 속성에 의해 결정됩니다.  매핑된 폴더의 모든 하위 폴더는 매핑된 폴더의 **Deployment Location**에 대한 상대 경로입니다.  항목이 배포되는 위치는 매핑된 폴더의 이름이 아니라 **Deployment Location** 속성에 의해서만 결정됩니다.  
  
 프로젝트의 메뉴 표시줄 또는 바로 가기 메뉴의 명령을 사용하여 매핑된 폴더를 프로젝트에 추가할 수 있습니다.  **SharePoint "이미지" 매핑된 폴더 추가** 및 **SharePoint "레이아웃" 폴더 추가** 명령을 사용하여 가장 자주 사용 되는 매핑된 폴더를 추가합니다.  바로 가기 메뉴에서 **SharePoint 매핑된 폴더 추가** 명령을 사용한 다음 **SharePoint 매핑된 폴더 추가** 대화 상자에서 폴더를 지정하여 사용할 수 있는 다른 SharePoint 폴더를 프로젝트에 매핑할 수 있습니다..  
  
## 프로젝트에 매핑된 폴더 추가  
 다음 절차에서는 비주얼 웹 파트 프로젝트에 두 개의 매핑된 폴더를 추가하는 방법에 대해 설명합니다.  시작하려면 비주얼 웹 파트 프로젝트를 만듭니다.  
  
#### 프로젝트에 매핑된 폴더를 추가하려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
2.  **새 프로젝트** 대화 상자의 **Visual C\#** 또는 **Visual Basic** 에서 **Office\/SharePoint** 노드를 확장하고 나서 **SharePoint 솔루션** 노드를 선택합니다.  
  
3.  프로젝트 템플릿 목록에서 **SharePoint 2013 Visual 웹 파트** 템플릿을 선택합니다.  
  
4.  **이름** 상자에 TestProject1을 입력한 다음 **확인** 버튼을 선택합니다.  
  
5.  **SharePoint 사용자 지정 마법사** 에서, **완료** 버튼을 선택하여 기본 설정을 유지합니다.  
  
6.  **솔루션 탐색기**에서 프로젝트 노드를 선택한 다음, 메뉴 표시줄에서 **프로젝트**, **SharePoint "이미지" 매핑된 폴더 추가** 를 선택합니다.  
  
     **이미지** 라는 폴더는 프로젝트에 표시되고 TestProject1 라는 하위 폴더를 포함합니다.  이 매핑된 폴더는 비주얼 웹 파트 프로젝트에 대한 이미지를 포함합니다.  
  
7.  **솔루션 탐색기**에서 프로젝트 노드를 선택한 다음, 메뉴 표시줄에서 **프로젝트**, **SharePoint 매핑된 폴더** 를 선택하여 **SharePoint 매핑된 폴더 추가** 대화 상자를 표시합니다.  
  
8.  매핑에 사용할 수 있는 폴더들의 트리 뷰에서, **리소스** 폴더를 선택한 다음, **확인** 버튼을 선택합니다.  
  
     **리소스** 라는 폴더가 프로젝트에 나타납니다.  이 폴더에는 문자열 리소스 파일과 같은 항목이 저장될 수 있습니다.  하위 폴더는 매핑된 폴더의 내용을 구성하는 데 유용할 수 있지만 **SharePoint 매핑된 폴더 추가** 명령을 사용하여 매핑된 폴더를 추가할 때 자동으로 만들어지지 않습니다.  하위 폴더를 추가 하려면 **리소스** 폴더를 선택한 다음, 메뉴 표시줄 **프로젝트**, **새 폴더** 를 선택합니다.  
  
## 매핑된 폴더의 배포 위치 변경  
 기본적으로, 매핑된 폴더는 {SharePointRoot}\)로 표시되는 SharePoint 루트 설치와 연관된 특정 위치에 추가됩니다.  하지만 매핑된 폴더의 **Deployment location** 속성을 변경하여 이 위치를 변경할 수 있습니다.  각 매핑된 폴더에는 해당 **Deployment location** 속성이 있습니다.  
  
#### 매핑된 폴더의 배포 위치를 변경하려면  
  
1.  앞에서 만든 프로젝트에서 매핑된 폴더를 선택합니다.  
  
2.  **속성** 창에서 **Deployment location** 속성에 있는 줄임표 \(![ASP.NET 모바일 디자이너 줄임표](~/sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")\) 버튼을 선택합니다.  
  
3.  **SharePoint 매핑된 폴더 추가** 대화 상자에서 매핑된 폴더가 가리킬 폴더를 찾습니다.  
  
4.  노드를 선택한 후 **확인** 버튼을 선택합니다.  
  
## 매핑된 폴더 이름 바꾸기 또는 제거  
  
#### 매핑된 폴더의 이름을 바꾸거나 제거하려면  
  
1.  앞에서 만든 프로젝트에서 매핑된 폴더를 선택합니다.  
  
2.  매핑된 폴더의 이름을 바꾸려면, 바로 가기 메뉴에서 **이름 바꾸기**를 선택하고, 새 이름을 입력한 다음, Enter 키를 누릅니다.  
  
     이 방법 말고도, 이름을 바꿀 매핑된 폴더를 선택하여 **속성** 창에서 **Folder name** 속성값을 새 이름으로 설정할 수 있습니다.  
  
3.  프로젝트에서 매핑된 폴더를 제거하려면, 바로 가기 메뉴에서 **삭제**를 선택한 다음, 대화 상자에서 **확인** 버튼을 선택하여 제거를 확인합니다.  
  
## 참고 항목  
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  