---
title: "방법: MSBuild 대상을 사용하여 SharePoint 솔루션 패키지 사용자 지정 | Microsoft Docs"
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
  - "Visual Studio에서 SharePoint 개발, 패키지"
ms.assetid: 7fa6a276-04c8-463e-be95-57c2c6240d76
caps.latest.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# 방법: MSBuild 대상을 사용하여 SharePoint 솔루션 패키지 사용자 지정
  명령줄 MSBuild 대상을 사용하여 Visual Studio에서 SharePoint 패키지 파일\(.wsp\)을 만드는 방법을 사용자 지정할 수 있습니다.  예를 들어 MSBuild 속성을 사용자 지정 하여 패키징 중간 디렉터리로 변경하거나 파일을 지정하는 MSBuild 항목 그룹을 사용자 지정할 수 있습니다.  
  
## MSBuild 대상 사용자 지정 및 실행  
 BeforeLayout 및 AfterLayout 대상 사용자를 지정 하면, 추가, 제거 또는 파일 수정과 같이 패키지 될 패키지 레이아웃 이전에 작업을 수행할 수 있습니다.  
  
#### BeforeLayout 대상을 사용자 지정하려면  
  
1.  메모장 등의 편집기를 열고 다음 코드를 추가 합니다.  
  
    ```  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <Target Name="BeforeLayout">  
        <Message Importance="high" Text="In the BeforeLayout Target"></Message>  
      </Target>  
    </Project>  
    ```  
  
     이 예제는 이 대상을 패키징 하기 전에 메시지를 표시합니다.  
  
2.  파일을 **CustomLayout.SharePoint.targets** 로 명명한 다음 SharePoint 프로젝트 폴더에 저장합니다.  
  
3.  프로젝트 바로 가기 메뉴를 연 다음 **프로젝트 언로드** 를 선택합니다.  
  
4.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **편집** *ProjectName***.vbproj** 또는 **편집** *ProjectName***.csproj** 을 선택합니다.  
  
5.  프로젝트 파일의 끝 부분에 있는 `Import` 줄 다음에 다음 줄을 추가 합니다.  
  
    ```  
    <Import Project="CustomLayout.SharePoint.targets" />  
    ```  
  
6.  프로젝트 파일을 저장하고 닫습니다.  
  
7.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **프로젝트 재로드**를 선택합니다.  
  
 프로젝트를 게시 할 때 포장을 시작되기 전에 메시지가 출력됩니다.  
  
#### AfterLayout 대상을 사용자 지정하려면  
  
1.  메뉴 모음에서 **파일**, **열기**, **파일**을 선택합니다.  
  
2.  **파일 열기** 대화 상자에서, 프로젝트 폴더를 탐색하고, CustomLayout.target 파일을 선택한 다음, **열려** 버튼을 선택합니다.  
  
3.  `</Project>` 태그 바로 앞에 다음 코드를 추가합니다.  
  
    ```  
    <Target Name="AfterLayout">  
      <Message Importance="high" Text="In the AfterLayout Target"></Message>  
    </Target>  
    ```  
  
     이 예제는 이 대상이 패키지 된 후 메시지를 표시합니다.  
  
4.  대상 파일을 저장한 후 닫습니다.  
  
5.  Visual Studio를 다시 시작한 다음 프로젝트를 엽니다.  
  
 프로젝트를 게시하면 패키징이 시작되기 전에 BeforeLayout 메시지가 나타나고 패키징 완료 후 AfterLayout 메시지가 나타납니다.  
  
## 참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  