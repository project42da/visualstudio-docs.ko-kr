---
title: "방법: MSBuild 작업을 사용하여 SharePoint 솔루션 패키지 만들기 | Microsoft Docs"
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
ms.assetid: c3880bdd-f0a1-4d53-9a97-5767cb3f7b8e
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 16
---
# 방법: MSBuild 작업을 사용하여 SharePoint 솔루션 패키지 만들기
  개발 컴퓨터에서 명령줄 MSBuild 작업을 사용하여 SharePoint 패키지\(.wsp\)를 빌드 및 정리하고 유효성을 검사할 수 있습니다.  빌드 컴퓨터에서 Team Foundation Server를 사용하면 이러한 명령을 통해 빌드 프로세스를 자동화할 수도 있습니다.  
  
## SharePoint 패키지 빌드  
  
#### SharePoint 패키지를 빌드하려면  
  
1.  Windows **시작** 메뉴에서 **모든 프로그램**, **보조 프로그램**, **명령 프롬프트** 를 선택합니다.  
  
2.  SharePoint 프로젝트가 있는 디렉터리로 이동합니다.  
  
3.  다음 명령을 입력하여 프로젝트에 대한 패키지를 만듭니다.  *ProjectFileName* 을 팀 프로젝트의 이름으로 바꿉니다.  
  
    ```  
    msbuild /t:Package ProjectFileName  
    ```  
  
     예를 들어 다음 명령 중 하나를 실행하여 ListDefinition1이라는 SharePoint 프로젝트를 패키징할 수 있습니다.  
  
    ```  
    msbuild /t:Package ListDefinition1.vbproj  
    msbuild /t:Package ListDefinition1.csproj  
    ```  
  
## SharePoint 패키지 정리  
  
#### SharePoint 패키지를 정리하려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  SharePoint 프로젝트가 있는 디렉터리로 이동합니다.  
  
3.  다음 명령을 입력하여 프로젝트에 대한 패키지를 정리합니다.  *ProjectFileName* 을 팀 프로젝트의 이름으로 바꿉니다.  
  
    ```  
    msbuild /t:CleanPackage ProjectFileName  
    ```  
  
     예를 들어 다음 명령 중 하나를 실행하여 ListDefinition1이라는 SharePoint 프로젝트를 정리할 수 있습니다.  
  
    ```  
    msbuild /t:CleanPackage ListDefinition1.vbproj  
    msbuild /t:CleanPackage ListDefinition1.csproj  
    ```  
  
## SharePoint 패키지 유효성 검사  
  
#### SharePoint 패키지의 유효성을 검사하려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  SharePoint 프로젝트가 있는 디렉터리로 이동합니다.  
  
3.  다음 명령을 입력하여 프로젝트에 대한 패키지의 유효성을 검사합니다.  *ProjectFileName* 을 팀 프로젝트의 이름으로 바꿉니다.  
  
    ```  
    msbuild /t:ValidatePackage ProjectFileName  
    ```  
  
     예를 들어 다음 명령 중 하나를 실행하여 ListDefinition1이라는 SharePoint 프로젝트의 유효성을 검사할 수 있습니다.  
  
    ```  
    msbuild /t:ValidatePackage ListDefinition1.vbproj  
    msbuild /t:ValidatePackage ListDefinition1.csproj  
    ```  
  
## SharePoint 패키지의 속성 설정  
  
#### SharePoint 패키지의 속성을 설정하려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  SharePoint 프로젝트가 있는 디렉터리로 이동합니다.  
  
3.  다음 명령을 입력하여 프로젝트에 대한 패키지의 속성을 설정합니다.  *PropertyName* 을 설정 하려는 속성으로 바꿉니다.  
  
    ```  
    msbuild /property:PropertyName=Value  
    ```  
  
     예를 들어 다음 명령을 실행하여 경고 수준을 설정할 수 있습니다.  
  
    ```  
    msbuild /property:WarningLevel = 2  
    ```  
  
## 참고 항목  
 [SharePoint 기능 만들기](../sharepoint/creating-sharepoint-features.md)   
 [방법: SharePoint 기능 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [방법: SharePoint 기능에 항목 추가 및 제거](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)  
  
  