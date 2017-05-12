---
title: "방법: 기능 종속성 추가 및 제거"
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
  - "MICROSOFT.VISUALSTUDIO.SHAREPOINT.DESIGNERS.CUSTOMDEPENDENCYWINDOW"
  - "VS.SHAREPOINTTOOLS.RAD.FEATUREDESIGNERDEPENDENCY"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 기능"
ms.assetid: 2b34c8d9-c975-4fe9-b8e0-52db4a6014ea
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# 방법: 기능 종속성 추가 및 제거
  SharePoint 기능이 작동하거나 필요한 데이터를 얻기 위해 다른 기능을 사용할 수 있습니다.  이 경우 다른 기능을 해당 기능의 종속성으로 표시할 수 있습니다.  이렇게 하면 기능이 활성화되기 전에 SharePoint 서버에서 종속된 기능을 활성화합니다.  
  
## 종속성 추가  
 솔루션의 다른 기능을 종속성으로 추가할 수 있습니다.  이렇게 하면 기능이 설치되기 전에 필요한 기능이 설치 및 활성화됩니다.  
  
#### 솔루션의 기능에 대한 종속성을 추가하려면  
  
1.  기능 디자이너를 열고 **기능 활성화 종속성** 노드를 확장한 다음 **추가** 버튼을 선택합니다.  
  
2.  **기능 활성화 종속성 추가** 대화 상자에서 **솔루션의 기능에 대한 종속성 추가** 옵션 버튼을 선택하고, 종속성으로 추가하고 싶은 기능의 제목을 추가한 다음, **추가** 버튼을 선택합니다.  
  
     Ctrl 키를 누르는 동안 제목을 여러개 선택하여 하나 이상의 피쳐를 추가할 수 있습니다.  
  
## 사용자 지정 종속성 추가  
 SharePoint 서버에 이미 배포된 기능을 종속성으로 추가할 수 있습니다.  이렇게 하면 기능이 설치되기 전에 SharePoint 활성화 프로세스에서 종속된 기능을 모두 활성화합니다.  
  
#### 기능 ID로 종속성을 추가하려면  
  
1.  기능 디자이너를 열고 **기능 활성화 종속성** 노드를 확장한 다음 **추가** 버튼을 선택합니다.  
  
2.  **기능 활성화 종속성 추가** 대화 상자에서 **사용자 지정 종속성 추가** 옵션 버튼을 선택합니다.  
  
3.  **기능 ID** 텍스트 상자에서, 활성화 종속성으로 표시할 기능의 GUID를 입력한 다음, **추가** 버튼을 선택합니다.  
  
## 사용자 지정 종속성 편집  
 이전에 추가한 사용자 지정 종속성을 편집할 수 있습니다.  하지만 솔루션에 있는 종속된 기능은 제거할 수만 있고 편집할 수는 없습니다.  
  
#### 솔루션의 기능에 대한 종속성을 변경하려면  
  
1.  기능 디자이너를 연 다음 **기능 활성화 종속성** 노드를 확장합니다.  
  
2.  편집하고 싶은 기능의 이름을 선택한 다음 **편집** 버튼을 선택합니다.  
  
3.  **사용자 지정 기능 활성화 종속성 편집** 대화 상자에서, 제목, 기능 ID, 또는 설명을 변경한 다음, **제출** 버튼을 선택합니다  
  
## 종속성 제거  
  
#### 솔루션의 기능에 대한 종속성을 제거하려면  
  
1.  기능 디자이너에서 **기능 활성화 종속성** 노드를 확장하고, 제거할 기능의 이름을 선택한 다음, **제거** 버튼을 선택합니다.  
  
## 참고 항목  
 [SharePoint 기능 만들기](../sharepoint/creating-sharepoint-features.md)   
 [방법: SharePoint 기능 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [방법: SharePoint 기능에 항목 추가 및 제거](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)  
  
  